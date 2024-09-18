### Question Breakdown — ML Techniques & Workflow Selection

---

#### **Part 1 – Choosing the Right ML Technique**

**Scenario**

> Predict house prices from features such as square footage, number of bathrooms, basement, etc.

|Option|Technique|Quick Definition|Fit?|
|---|---|---|---|
|**A. Clustering**|Unsupervised grouping by similarity|Good for customer segments / anomaly detection, **not** numeric price prediction|✗|
|**B. Classification**|Supervised assignment to discrete classes|Predicts labels (e.g., spam vs. ham), not continuous values|✗|
|**C. Regression**|Supervised modeling of variable relationships to output a **continuous**number|Matches need to predict a price|**✓ (Correct)**|
|**D. Unsupervised learning (generic)**|Uses un-labeled data for pattern discovery|Too broad; not focused on numeric prediction|✗|

**Correct Technique → Regression**

---

#### **Part 2 – Selecting AI/ML Workflow Steps (Choose 2)**

**Scenario**

> Equity-investment firm wants to apply AI/ML in its company-analysis workflow.

|Option|Task|AI/ML Suitability|Keep?|
|---|---|---|---|
|**A. Ingest quarterly CSV data**|Straightforward ETL|Rule-based; no ML needed|✗|
|**B. Perform financial-sentiment analysis on press releases**|Domain-specific NLP|Requires custom or fine-tuned NLP model|**✓**|
|**C. Summarize earnings-call transcripts**|Text summarization|Core LLM use-case|**✓**|
|**D. Calculate EBITDA from metrics**|Simple arithmetic formula|Deterministic; no ML benefit|✗|
|**E. Run keyword news search**|Basic search query|Can be done without ML (unless ranking relevance)|✗|

**Correct Workflow Steps → B and C**

---

##### Summary

- **Regression** is the appropriate technique for numeric house-price prediction.
    
- In investment due-diligence, AI adds value to **financial-sentiment analysis** (B) and **automated summarization of transcripts** (C); routine data ingestion or formula calculations do not require ML.