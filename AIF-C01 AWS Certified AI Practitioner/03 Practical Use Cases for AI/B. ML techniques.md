### Machine-Learning Techniques — Concise Notes

---

#### 1. Regression (supervised)

Predict **numeric values** by modelling relationships between variables.

|Variant|Core Idea|Typical Example|
|---|---|---|
|**Linear Regression**|Straight-line fit between one dependent and one+ independent variables|Predict a person’s **weight** from **height**|
|**Multiple Linear Regression**|Same as above but with **multiple** predictors|Estimate **house price** from square footage, location, etc.|
|**Polynomial Regression**|Fits an _n_-degree curve for non-linear trends|Model a ball’s **trajectory** (height vs. time)|
|**Logistic Regression**|Outputs probability of a **binary** outcome|Classify an email as **spam / not-spam**|

---

#### 2. Classification (supervised)

Assign each input to a **discrete class/label**.

- Goal: learn a decision boundary that generalises to unseen data.
    
- Common uses:
    
    - Spam filtering
        
    - Image recognition
        
    - Sentiment analysis
        
    - Medical diagnosis
        
    - Credit-risk scoring
        

---

#### 3. Clustering (unsupervised)

Group **unlabelled** data points by similarity.

|Method|How It Clusters|Typical Use Case|
|---|---|---|
|**k-Means**|Partitions data into _k_ centroids (spherical clusters)|Customer segmentation by purchasing behaviour|
|**Hierarchical**|Builds a tree/dendrogram of nested clusters|Document grouping by text similarity|
|**DBSCAN**|Forms dense regions, flags sparse points as outliers|**Anomaly detection** in spatial or sensor data|

---

**Key distinctions**

- **Regression** → Predict **continuous** values.
    
- **Classification** → Predict **categorical** labels.
    
- **Clustering** → Discover **structure** in unlabelled data.