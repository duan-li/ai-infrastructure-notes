#### 1. High-Level Goals

|Requirement|Architectural Choice|
|---|---|
|**Managed foundation model**|Amazon **Bedrock** (image model)|
|**Resilient but not serverless infra**|Two-AZ **VPC** with ALB + EC2 Auto Scaling|
|**Managed storage / CDN / DNS / metadata**|**S3 + CloudFront + Route 53 + DynamoDB**|

---

#### 2. Network & Compute Layer

```
VPC (10.x/16)
├─ Public Subnet  (AZ-A) ──► ALB ◄── Public Subnet (AZ-B)
│                         ▲
│                         │
├─ Private Subnet (AZ-A) ─┴─ EC2 (Node.js app, IAM role)
└─ Private Subnet (AZ-B) ─── EC2 (scale-out)

```

---

#### 3. Edge, Security & DNS

| Component                       | Purpose                                                       |
| ------------------------------- | ------------------------------------------------------------- |
| **CloudFront** (wild-card cert) | Global CDN; one origin = ALB (API) + one origin = S3 (images) |
| **WAF ACL**                     | Basic OWASP protections, throttling                           |
| **Route 53**                    | DNS, alias to CloudFront, health checks if desired            |

---

#### 4. Managed AI & Data Services

|Service|Role|
|---|---|
|**Amazon Bedrock**|Invoke managed diffusion model for image generation|
|**Amazon S3**|Store & serve generated images (static origin for CloudFront)|
|**Amazon DynamoDB**|Persist image metadata (prompt, user ID, timestamp, S3 key, etc.)|

---

#### 5. Request / Data Flow

1. **User→DNS** – Route 53 returns CloudFront URL.
    
2. **User→CloudFront** – Request hits nearest edge, WAF checks.
    
3. **CloudFront→ALB** – For API calls (image-generate).
    
4. **ALB→EC2** – Node.js app receives prompt.
    
5. **EC2→Bedrock** – Call via NAT GW → Bedrock endpoint; returns base-64 image.
    
6. **EC2**
    
    - Decodes & uploads PNG/JPEG to **S3** (`PUT` via VPC endpoint).
        
    - Records metadata to **DynamoDB** (`PutItem`).
        
7. **EC2→Client** – Responds with CloudFront image URL.
    
8. **Client→CloudFront→S3** – Image served from edge cache; future hits served at CDN edge.
    

---

#### 6. Well-Architected Alignment (Key Pillars)

|Pillar|How Addressed|
|---|---|
|**Reliability**|Multi-AZ ALB & EC2, health checks, Auto Scaling|
|**Performance**|CloudFront caching; Bedrock offloads heavy GPU inference|
|**Security**|IAM role-based access, VPC endpoints (no public S3/DynamoDB), WAF|
|**Operational Excellence**|Managed services (Bedrock, DynamoDB), IaC possible (CDK/CloudFormation)|
|**Cost Optimization**|Spot EC2 or Graviton2 instances, CloudFront caching, Bedrock pay-per-request|
|**Sustainability**|Managed, shared-responsibility services reduce undifferentiated heavy lifting|

---

#### 7. Possible Enhancements

- **Step Functions** to orchestrate async generation & thumbnailing.
    
- **Amazon EventBridge** + **SNS** for notifications on image-ready events.
    
- **S3 Object Lambda / S3 Access Points** for fine-grained access control.
    
- Swap EC2 for **ECS/Fargate** to reduce patching if moving toward containerization.
    

---

This architecture meets the stated constraints: it keeps model hosting fully managed (Bedrock), stays highly available across AZs, and offloads persistence, caching, and DNS to AWS managed services—all while aligning with the AWS Well-Architected Framework.