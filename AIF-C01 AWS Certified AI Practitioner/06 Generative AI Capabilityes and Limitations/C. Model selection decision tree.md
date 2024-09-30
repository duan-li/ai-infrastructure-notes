```
                    ┌───────────────────────────┐
                    │  What content to generate?│
                    └────────────┬──────────────┘
                                 │
 ┌─────────────── Text ──────────┴───────────────┐
 │                                                │
 │  ■ Creative / conversational → Use a **general-purpose LLM** (zero-shot)          │
 │  ■ Legal / financial / compliance  → **Fine-tuned LLM** on domain corpus          │
 │  ■ Technical / scientific logic    → **Custom-trained domain model**              │
 │
 ├────────────── Images ──────────►  Diffusion / GAN                                  │
 │       (pick size vs. realism vs. cost)                                             │
 │
 ├────────────── Audio ───────────►  Diffusion / Transformer TTS / MusicLM-style      │
 │       (speech, music, sound design)                                                │
 │
 ├────────────── Video ───────────►  Diffusion-based or GAN-video                     │
 │       (highest compute/storage demand)                                             │
 │
 └───────────── Multimodal ───────►  Large multimodal transformers (e.g., PaLM-E)      │
         (cross-media input & output)                                                 

```

#### Cross-Cutting Selection Factors

| Factor                                 | Guiding Question                                    | Trade-off / Impact                                                  |
| -------------------------------------- | --------------------------------------------------- | ------------------------------------------------------------------- |
| **Performance vs. Latency**            | Need _speed_ (chat) or _accuracy/detail_(analysis)? | Small model = fast but less accurate; large = slow but precise.     |
| **Customization Level**                | Fine-tune or train from scratch?                    | Increases cost, data, MLOps complexity.                             |
| **Compute / Cost Limits**              | GPU budget, memory, on-device constraints?          | May force distilled or quantized models.                            |
| **Governance, Risk, Compliance (GRC)** | Data-sovereignty, auditing, privacy?                | Might require on-prem or VPC-isolated hosting; stricter guardrails. |

---

#### Quick Selection Cheat-Sheet

|Goal|Recommended Starting Point|
|---|---|
|Blog copy, customer chat|Open-weight GPT-class LLM|
|Legal clause drafting|Base LLM fine-tuned on legal corpus|
|Photoreal marketing imagery|High-resolution diffusion (e.g., Stable Diffusion XL)|
|Lo-fi music beds|Music-focused diffusion / Transformer TTS|
|Short explainer videos|Video diffusion with strong hardware budget|
|Cross-modal caption & Q&A|Multimodal foundation (e.g., CLIP + LLM wrapper)|

Use the decision tree for **mode selection**, then refine choice with **performance, customization, budget, and compliance**considerations.


