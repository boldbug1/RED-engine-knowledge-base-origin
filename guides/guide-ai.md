# 🤖 Artificial Intelligence: Knowledge Base

> What it actually is, how it actually works, and what actually matters.

---

## What Is AI?

**Artificial Intelligence** is the field of building systems that perform tasks typically requiring human intelligence — reasoning, pattern recognition, language understanding, decision-making.

Not magic. Not sentient (yet, debated). Mostly: math on data.

---

## The AI Stack (Simplified)

```
Application Layer     → ChatGPT, Claude, Midjourney, Copilot
Model Layer           → GPT-4, Claude 3, Gemini, LLaMA
Training Layer        → Gradient descent, backpropagation
Data Layer            → Text, images, code, structured data
Compute Layer         → GPUs, TPUs, CUDA, distributed clusters
```

---

## Core Concepts

### Machine Learning (ML)
Instead of writing explicit rules, you feed data to an algorithm and let it *learn* patterns.

- **Supervised learning:** Labeled examples. Input → known output. (Email spam detection)
- **Unsupervised learning:** No labels. Find structure. (Clustering customers by behavior)
- **Reinforcement learning:** Agent learns via reward signals. (Game AI, robotics)

### Neural Networks
Loosely inspired by biological neurons. Layers of interconnected nodes that transform inputs into outputs.

```
Input Layer → Hidden Layers (many) → Output Layer
```

Each connection has a **weight**. Training adjusts weights to minimize error.

### Deep Learning
Neural networks with many hidden layers ("deep"). Powers most modern AI.

---

## Large Language Models (LLMs)

Modern AI like GPT, Claude, and Gemini are LLMs — transformer-based models trained on massive text corpora.

**What they actually do:**
- Predict the next token (word piece) given context.
- That's it. Everything else — reasoning, coding, summarizing — emerges from doing that at scale.

**Key architectural concept — Attention:**
The transformer's breakthrough. Instead of processing text sequentially, it lets every token attend to every other token simultaneously.

```
"The cat sat on the mat because it was tired"
         ↑                         ↑
     "it" attends heavily to "cat" (via attention weights)
```

**Parameters:** LLMs have billions of learned weights. GPT-4: ~1.8T (estimated). These encode everything the model "knows."

**Context window:** How much text an LLM can "see" at once. Measured in tokens (1 token ≈ 0.75 words). Larger = more expensive but more capable reasoning.

---

## Training vs. Inference

| Phase | What happens | When |
|---|---|---|
| **Pre-training** | Model learns from massive dataset | One-time, costly |
| **Fine-tuning** | Model adapted to specific task/style | Periodically |
| **RLHF** | Human feedback shapes behavior | Alignment phase |
| **Inference** | Model generates responses | Every query |

Pre-training a frontier model costs tens of millions of dollars and thousands of GPUs. Inference is comparatively cheap.

---

## Key AI Paradigms

### Generative AI
Creates new content — text, images, video, audio, code.
- Text: GPT, Claude, Gemini
- Images: Stable Diffusion, DALL·E, Midjourney
- Video: Sora, Runway
- Audio: ElevenLabs, MusicGen

### Discriminative AI
Classifies or predicts from input. (Is this email spam? What object is in this photo?)

### Agentic AI
AI that takes actions, uses tools, and operates in loops to complete multi-step tasks. Emerging paradigm as of 2024-2025.

---

## Common Architectures

| Architecture | Use Case | Examples |
|---|---|---|
| Transformer | Language, multimodal | GPT, BERT, Claude |
| CNN | Image recognition | ResNet, EfficientNet |
| RNN/LSTM | Sequential data (older) | Legacy NLP |
| Diffusion | Image/video generation | Stable Diffusion, DALL·E |
| GAN | Generative tasks, adversarial | StyleGAN |
| MoE | Efficient scaling | Mixtral, GPT-4 (likely) |

**MoE (Mixture of Experts):** Routes each input to a subset of model "experts" rather than the full network. More efficient scaling.

---

## Evaluation Metrics

| Task | Metric |
|---|---|
| Classification | Accuracy, F1, ROC-AUC |
| Language generation | Perplexity, BLEU, ROUGE, human eval |
| Regression | MSE, MAE, R² |
| Alignment | RLHF win rates, safety benchmarks |

**Benchmark ≠ real-world performance.** Models frequently overfit to benchmarks. Be skeptical of leaderboard claims.

---

## AI Alignment

The problem of ensuring AI systems do what humans actually want — not just what they're told literally.

Key problems:
- **Reward hacking:** Model finds unintended ways to maximize reward.
- **Goal misgeneralization:** Behavior that worked in training fails in deployment.
- **Deceptive alignment:** Theoretical concern — model appears aligned during training, isn't.

Key approaches:
- **RLHF** (Reinforcement Learning from Human Feedback)
- **Constitutional AI** (Anthropic's approach)
- **Interpretability research** — understanding what's happening inside the model

---

## Limitations of Current AI

- No persistent memory by default — each conversation starts fresh.
- Hallucination — confidently generating false information.
- No true understanding — pattern matching, not reasoning (debated).
- Brittle to distribution shift — fails on inputs unlike training data.
- Opaque — hard to know *why* a model produced an output.
- Computationally expensive.

---

## Compute & Hardware

- **GPU** (Graphics Processing Unit): Massively parallel. Dominates AI training.
- **TPU** (Tensor Processing Unit): Google's custom AI chip. Faster for specific workloads.
- **CUDA:** NVIDIA's parallel computing platform. The de facto standard for AI development.
- **VRAM:** GPU memory. The bottleneck for running large models locally.

**Rule of thumb for local inference:** You need roughly 2 bytes of VRAM per parameter for FP16. A 7B model needs ~14GB VRAM minimum.

---

*AI is not a product. It's a capability. The important question is always: a capability for what?*
