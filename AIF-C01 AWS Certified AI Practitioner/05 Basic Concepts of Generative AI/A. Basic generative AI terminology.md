#### 1. Transformer-Based Large Language Models (LLMs)

- **Definition:** Neural networks (e.g., GPT) that learn patterns in massive text corpora to generate human-like language.
    
- **Key trait:** Built on the _transformer_ architecture, enabling long-range context handling.
    

---

#### 2. Tokens

- **What they are:** The smallest text units a model processes—can be a word, sub-word, character, or punctuation mark, depending on the tokenizer.
    

---

#### 3. Chunking

- **Purpose:** Split long documents into **chunks** (measured in tokens) so they fit model or vector-DB limits.
    
- **Note:** Easy to do poorly; _optimal_ chunk size heavily influences retrieval quality.
    

---

#### 4. Vectors

- **Concept:** Ordered lists of numbers that encode features of data (text, image, audio, etc.).
    
- **Use:** Enable similarity math (dot product, cosine) for search or clustering.
    

---

#### 5. Embeddings

- **Definition:** _Dense_ vector representations produced by an encoder model.
    
- **Why they matter:** Capture semantic meaning; vector databases index embeddings for rapid similarity search.
    

---

## Foundation-Model Families for Generative AI

|Model Type|Core Idea|Typical Use Cases|
|---|---|---|
|**LLM (Large Language Model)**|Text-only transformer trained on billions of tokens|Text generation, translation, summarization|
|**Diffusion Model**|Start from noise and iteratively refine toward data distribution|Image & audio synthesis, in-painting|
|**Multimodal Model**|Trained jointly on **text + other media** (images, audio, video)|Captioning, visual Q&A, cross-modal generation|
|**GAN (Generative Adversarial Network)**|Generator vs. Discriminator in a two-network “game” until outputs look real|Photo-realistic imagery, style transfer|
|**VAE (Variational Autoencoder)**|Combines autoencoding with probabilistic latent space|Anomaly detection, data compression, latent-space interpolation|

---

### Quick Relationships

- **Embeddings → Vectors:** Every embedding _is_ a vector but tuned for semantic meaning.
    
- **Chunks → Tokens:** Chunk size is counted in tokens; too large or too small harms retrieval.
    
- **LLMs, GANs, Diffusion, VAEs, Multimodal models** are all **foundation models**—large pretrained networks you can adapt or prompt for downstream generative tasks.
    

Use this glossary as a launch point before diving deeper into generative-AI workflows and architectures.