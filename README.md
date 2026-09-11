# TinyGPT

> **A minimal GPT-style language model built from scratch for understanding Transformer-based language modeling.**

TinyGPT is a compact implementation of a **decoder-only Transformer** that demonstrates the core building blocks behind GPT-style models — from tokenization and causal self-attention to training and autoregressive generation.

---

## Overview

| Component            | Implementation                     |
| -------------------- | ---------------------------------- |
| Architecture         | Decoder-only Transformer           |
| Learning Objective   | Next-token prediction              |
| Attention            | Causal multi-head self-attention   |
| Position Information | Positional embeddings              |
| Normalization        | Layer Normalization                |
| MLP                  | Feed-forward network               |
| Training             | Backpropagation + gradient descent |
| Generation           | Autoregressive decoding            |
| Framework            | PyTorch                            |

---

## Architecture

```text
Text
 │
 ▼
Tokenizer
 │
 ▼
Token IDs
 │
 ▼
Token + Position Embeddings
 │
 ▼
┌─────────────────────────────┐
│      Transformer Block      │
│                             │
│  LayerNorm                  │
│      ↓                      │
│  Causal Multi-Head Attention│
│      ↓                      │
│  Residual Connection        │
│      ↓                      │
│  LayerNorm                  │
│      ↓                      │
│  Feed-Forward Network       │
│      ↓                      │
│  Residual Connection        │
└─────────────────────────────┘
 │
 ▼
Language Model Head
 │
 ▼
Logits
 │
 ▼
Next Token
```

---

## Core Components

| Component            | Purpose                                         |
| -------------------- | ----------------------------------------------- |
| Tokenization         | Converts text into model-readable tokens        |
| Embeddings           | Represents tokens as dense vectors              |
| Positional Encoding  | Provides sequence-order information             |
| Self-Attention       | Learns relationships between tokens             |
| Causal Masking       | Prevents access to future tokens                |
| Multi-Head Attention | Learns multiple attention patterns              |
| Feed-Forward Network | Non-linear feature transformation               |
| Residual Connections | Improves information and gradient flow          |
| LayerNorm            | Stabilizes Transformer activations              |
| LM Head              | Converts hidden states into token probabilities |

---

## Training

TinyGPT learns through **next-token prediction**:

```text
Input:   The model learns
Target:       model learns ...
```

The model minimizes **cross-entropy loss** between predicted and target tokens.

```text
Dataset
   ↓
Tokenization
   ↓
Context / Target Pairs
   ↓
Forward Pass
   ↓
Cross-Entropy Loss
   ↓
Backpropagation
   ↓
Parameter Update
   ↓
Repeat
```

---

## Generation

TinyGPT generates text autoregressively:

```text
Prompt
  ↓
Predict token
  ↓
Append token
  ↓
Predict next token
  ↓
Repeat
```

Each generated token becomes part of the context used to predict the next token.

<!-- ---

## Project Structure

```text
TinyGPT/
├── data/
├── model/
├── tokenizer/
├── train.py
├── generate.py
├── config.py
├── requirements.txt
└── README.md
```

--- -->

<!-- ## Quick Start

```bash
git clone <repository-url>
cd TinyGPT

python -m venv .venv
source .venv/bin/activate

pip install -r requirements.txt
```

### Train

```bash
python train.py
```

### Generate

```bash
python generate.py
```

> Replace commands above with the repository's actual entry points if they differ.

--- -->

## What This Project Demonstrates

| Area              | Concepts                               |
| ----------------- | -------------------------------------- |
| Transformers      | Attention, residuals, normalization    |
| LLM Fundamentals  | Tokenization, embeddings, logits       |
| Deep Learning     | Loss, backpropagation, optimization    |
| Language Modeling | Next-token prediction                  |
| Inference         | Autoregressive generation              |
| PyTorch           | Custom model implementation & training |

---

## Learning Progression

```text
Neural Networks
      ↓
Embeddings
      ↓
Attention
      ↓
Self-Attention
      ↓
Multi-Head Attention
      ↓
Transformer
      ↓
GPT
      ↓
Training
      ↓
Inference
```

---

## Scope

TinyGPT is intentionally designed for **clarity and experimentation**, not production-scale language modeling.

| TinyGPT                    | Production LLM              |
| -------------------------- | --------------------------- |
| Small model                | Billions+ parameters        |
| Educational                | Production-oriented         |
| Limited dataset            | Massive datasets            |
| Single-machine experiments | Distributed infrastructure  |
| Architecture-focused       | Performance + scale focused |

---

## Future Work

* [ ] Improved tokenizer
* [ ] Larger training corpus
* [ ] Better sampling strategies
* [ ] Top-k / Top-p decoding
* [ ] Temperature control
* [ ] KV caching
* [ ] Mixed-precision training
* [ ] Model checkpointing
* [ ] Evaluation benchmarks
* [ ] Quantization

---

## Key Takeaway

**TinyGPT turns the GPT architecture from a black box into an inspectable system.**

> **Small model. Core Transformer mechanics. End-to-end implementation.**

---

## License

See [`LICENSE`](LICENSE.md) for details.

