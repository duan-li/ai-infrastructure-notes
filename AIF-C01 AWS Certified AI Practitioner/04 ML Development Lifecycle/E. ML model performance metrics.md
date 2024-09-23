### Machine-Learning Model Performance Metrics — Quick Reference Notes

---

#### 1. Core Terminology

| Term                    | What It Measures                  | Formula (conceptual)                                | Key Point                                           |
| ----------------------- | --------------------------------- | --------------------------------------------------- | --------------------------------------------------- |
| **Accuracy**            | Overall correctness               | correct predictions ÷ total predictions             | Simple but can mislead when classes are imbalanced. |
| **Precision**           | Purity of **positive**predictions | true positives ÷ (true positives + false positives) | High precision ⇒ few **false alarms**.              |
| **Recall**(Sensitivity) | Ability to find **all**positives  | true positives ÷ (true positives + false negatives) | High recall ⇒ few **missed positives**.             |

---

#### 2. Classification-Focused Metrics

|Metric|How It’s Calculated|When to Use|
|---|---|---|
|**F1 Score**|Harmonic mean of Precision & Recall   <br>F1 = 2 × (Precision × Recall) / (Precision + Recall)|• Class imbalance (rare-event detection)   <br>• Different costs for FP vs FN   <br>• Need a single number that balances both errors|
|**AUC-ROC**  <br>(Area Under the Receiver-Operating-Characteristic Curve)|Plot TPR (Recall) vs FPR for different thresholds; AUC = area under that curve (0.5 = random, > 0.9 = excellent)|• Compare discriminatory power of different models   <br>• Evaluate trade-off between true- and false-positive rates|

_Quick thresholds_

- **0.50** → random guessing
    
- **0.67** → rough break-even
    
- **≥ 0.90** → high-quality classifier
    

---

#### 3. Regression-Focused Metrics

|Metric|Formula (conceptual)|Interpretation|
|---|---|---|
|**MSE / RMSE**  <br>(Mean-Squared-Error or its square root)|mean [(predicted – actual)²]|Penalises larger errors more strongly; **closer to 0 == better**.|
|**R² (Coefficient of Determination)**|1 – (Residual Sum of Squares ÷ Total Sum of Squares)|Fraction of variance in the target explained by the model; **1.0 = perfect fit**, 0 = no explanatory power.|

---

#### 4. Choosing the Right Metric

|Situation|Prefer…|Why|
|---|---|---|
|Highly imbalanced classes|**F1** or **AUC-PR** (precision-recall curve)|Accuracy hides minority-class performance.|
|False positives cost more (e.g., spam filters)|**High Precision**|Minimise unnecessary alerts.|
|False negatives cost more (e.g., cancer screening)|**High Recall**|Catch as many real cases as possible.|
|General classification with balanced classes|**Accuracy** or **AUC-ROC**|Simpler interpretation.|
|Continuous value prediction|**MSE/RMSE** or **R²**|Tailored to regression tasks.|

---

**Take-away:** No single metric fits all scenarios. Start by clarifying business impact of _false positives_ vs _false negatives_(classification) or acceptable error tolerance (regression), then pick the metric(s) that surface those trade-offs clearly.