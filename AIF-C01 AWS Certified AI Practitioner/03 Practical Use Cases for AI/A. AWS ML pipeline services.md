### AWS SageMaker — End-to-End ML Pipeline Cheat-Sheet

---

#### 1. Data Preparation

|SageMaker Feature|Purpose|Key Capabilities|
|---|---|---|
|**Data Wrangler / Canvas**|Low-/no-code data prep in the browser|- Import from many sources - Clean, join, transform, visualize|
|**Feature Store**|Central feature catalog|- Online/offline stores - “Time-travel” queries - Share features across teams|

---

#### 2. Training & Experimentation

|Feature|Purpose|Highlights|
|---|---|---|
|**Training**|Scalable model training|- Built-in & custom algorithms - Automatic resource provisioning|
|**Experiments (MLflow)**|Track & compare runs|- Log hyper-params + metrics - Fine-tune foundation models|
|**Processing**|Managed batch jobs & notebooks|- Data transforms - Model evaluation scripts|

---

#### 3. Model Registration

|Feature|Purpose|Highlights|
|---|---|---|
|**Model Registry**|Source-of-truth for trained models|- Versioning - Approval workflow - Links to artifacts|

---

#### 4. Deployment

|Feature|Purpose|Notes|
|---|---|---|
|**Deployment**|Serve models for inference|Choose optimal instance type; reduces MLOps overhead|

---

#### 5. Post-Deployment Monitoring

|Feature|Purpose|Highlights|
|---|---|---|
|**Model Monitor**|Continuous quality checks|- Real-time or batch drift detection - Schedules & alerts|

---

#### 6. Orchestration

|Feature|Purpose|Highlights|
|---|---|---|
|**SageMaker Pipelines**|Automate & link every step|- DAG-based workflow - Scales across all SageMaker features|

---

### Typical SageMaker Pipeline Flow

1. **Prepare Data** → _Data Wrangler / Canvas_
    
2. **Curate Features** → _Feature Store_
    
3. **Train Model** → _Training_
    
4. **Track Experiments** → _Experiments (MLflow)_
    
5. **Evaluate** → _Processing job_
    
6. **Register Model** → _Model Registry_
    
7. **Deploy** → _Deployment_
    
8. **Monitor** → _Model Monitor_
    
9. **Automate** → Pipeline orchestrated by _SageMaker Pipelines_
    

This modular stack lets you build, deploy, and maintain ML solutions entirely within AWS SageMaker while following MLOps best practices.