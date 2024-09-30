|#|Disadvantage|What Can Go Wrong|Practical Implications|
|---|---|---|---|
|**1**|**Regulatory & Compliance Violations**|Models may output misleading medical/financial advice or copyrighted content.|Requires human review, legal vetting, content filters.|
|**2**|**Social Risks (Deepfakes & Disinformation)**|Synthetic images/audio/video can erode public trust, fuel polarization.|Need provenance tools, watermarking, policy controls.|
|**3**|**Data Security & Privacy Leakage**|Model can “spill” sensitive training data via prompt-hacking or inadvertent recall.|Adopt data-minimisation, confidential finetuning, red-teaming.|
|**4**|**Toxic or Harmful Content**|Offensive language, hate speech, self-harm instructions may slip through.|Implement toxicity classifiers, human moderation, RLHF safety tuning.|
|**5**|**Hallucinations**|Model confidently fabricates facts or citations.|Must add fact-checking layers, retrieval-augmented generation, disclaimers.|
|**6**|**Low Interpretability**|Hard to trace why a particular token or image pixel was generated.|Limits auditability; complicates bias or error analysis.|
|**7**|**Non-Determinism**|Same prompt can yield different outputs; difficult to reproduce bugs.|Seed-locking and temperature control help but rarely guarantee identical results.|

---

**Bottom line:** While generative AI unlocks novel capabilities, these seven pitfalls—legal, social, security, safety, factual, transparency, and determinism—demand robust guardrails, monitoring, and human oversight before deploying in critical workflows.