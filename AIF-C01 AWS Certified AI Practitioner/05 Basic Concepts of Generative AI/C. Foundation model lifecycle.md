|Phase|Purpose|Key Points / Activities|
|---|---|---|
|**1. Data Selection**|Assemble the massive corpus that will “teach” the model.|• Can be **labeled / unlabeled**, **structured / unstructured**.  <br>• Modalities: text, images, audio, video, code, etc.  <br>• Quality & diversity drive downstream capability and bias profile.|
|**2. Model Selection**|Pick an architecture suited to the end task(s).|• Options: **LLM**, **Diffusion**, **Multimodal**, **GAN**, **VAE**, …  <br>• Choice depends on output type (text vs. image), latency needs, hardware budget.|
|**3. Pre-Training**|Self-supervised learning on the raw corpus.|• Learns general patterns, semantics, and context.  <br>• Requires large-scale compute (TPUs/GPUs, distributed training).|
|**4. Fine-Tuning / Alignment**|Adapt the pre-trained model for a specific domain or behaviour.|• Supervised or RLHF (Reinforcement Learning from Human Feedback).  <br>• Smaller, task-focused datasets; faster than pre-training.|
|**5. Evaluation**|Quantify quality before launch.|• Metrics: accuracy, perplexity, BLEU, FID, latency, etc.  <br>• Check bias, toxicity, and robustness.|
|**6. Deployment (MLOps)**|Integrate the model with products & APIs.|• Use DevOps-style CI/CD, infrastructure-as-code.  <br>• Options: fully managed endpoint, container on Kubernetes, edge devices, etc.|
|**7. Feedback & Monitoring**|Post-production health and improvement loop.|• Track drift, bias, performance regressions.  <br>• Collect user signals for future fine-tuning or prompt-engineering.|

**Cycle**: Data ⇢ Pre-train ⇢ Fine-tune ⇢ Evaluate ⇢ Deploy ⇢ Monitor ⇢ (back to Data/Fine-tune as needed). Continuous iteration keeps the foundation model accurate, safe, and aligned with business goals.
