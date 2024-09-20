When building ML solutions, especially on platforms like **AWS SageMaker**, you have several options for sourcing models:

### **1. Open-Source Pre-Trained Models**

- Provided by popular ML communities and libraries:
    
    - **Meta**
        
    - **Hugging Face**
        
    - **TensorFlow**
        
- Useful for jumpstarting projects with minimal training effort.
    

### **2. Custom Models**

- Built using SageMaker’s integrated tools.
    
- You choose the algorithm and training dataset to suit your specific use case.
    

#### **Supported Algorithm Categories:**

- **Supervised Learning**
    
    - Example: **Regression** (predicting numeric values)
        
- **Unsupervised Learning**
    
    - Example: **Clustering**, **pattern recognition** (no labeled data)
        
- **Image Processing**
    
    - Use cases: **Object detection**, **computer vision**
        
- **Text Analysis (NLP)**
    
    - Use cases:
        
        - **Document summarization**
            
        - **Language transcription**
            
        - **Translation**
            

---

## **ML Model Deployment Options**

Once a model is trained, it needs to be deployed so it can be used by applications. Two common deployment approaches in AWS:

---

### **1. Self-Hosted API Deployment**

#### **Architecture Flow:**

- Client sends request to **API Gateway**
    
- Traffic goes to **Application Load Balancer (ALB)**
    
- ALB routes to a compute resource (e.g.):
    
    - **EC2 instance** (in an auto-scaling group)
        
    - **Container service (ECS/EKS)**
        
- The compute resource hosts a **local copy of the model** for inference
    

#### **Key Traits:**

- More **control** over infrastructure
    
- Requires **management** of model hosting and scaling
    

---

### **2. Managed API with Inference Endpoint**

#### **Architecture Flow:**

- Starts same as above: client → **API Gateway** → **ALB** → compute resource
    
- Instead of local inference, the request is:
    
    - **Privately forwarded** to a **SageMaker inference endpoint**
        
- SageMaker runs the model and returns the **inference result** to the client
    

#### **Key Traits:**

- **Serverless-like experience**
    
- AWS handles model **scaling, availability, and optimization**
    

---

## **Conclusion**

AWS SageMaker supports a variety of **model sources** (open-source, pre-trained, custom-built) and **flexible deployment options**, enabling teams to choose the setup that best matches their performance, control, and scalability needs.