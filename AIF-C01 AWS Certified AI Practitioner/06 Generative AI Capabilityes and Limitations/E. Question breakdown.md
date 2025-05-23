### Question 1

**Correct choice:** **B. Hallucinations**

**Why?**

- The problem reported is **inaccurate or fabricated diagnoses** in the autogenerated medical reports.
    
- Hallucinations are exactly this failure mode: the model invents plausible-sounding but false information and presents it as fact.
    
- The other options do not align with the symptom described:
    
    - **Toxicity** → deals with offensive or harmful language, not factual accuracy.
        
    - **Interpretability** → relates to understanding _how_ the model reached an answer, not whether the answer is correct.
        
    - **Non-determinism** → means the same prompt can yield different outputs, but that does not necessarily imply wrong outputs.
        

---

### Question 2

**Correct choice:** **A. A small, domain-specific model fine-tuned on customer-support queries**

**Why?**

- **Low latency (< 2 s)**: a compact model returns responses faster than a large general-purpose LLM.
    
- **Domain accuracy**: fine-tuning on the company’s own support data captures both common and highly technical questions.
    
- **Compliance**: hosting the model privately (on-prem or in a restricted VPC) simplifies meeting stringent data-privacy rules.
    

**Why the other options fall short**

|Option|Drawback|
|---|---|
|**B. Large general-purpose model via public API**|Potentially higher latency and less control over data residency/compliance.|
|**C. Large general-purpose model hosted on-prem**|Solves compliance, but large size still risks exceeding the two-second SLA and demands significant on-prem GPU capacity.|
|**D. Multimodal text–image–audio model**|Adds complexity and compute overhead while the use-case needs text only, harming latency and cost efficiency.|

---

These selections best satisfy the specific accuracy, speed, and regulatory requirements in each scenario.