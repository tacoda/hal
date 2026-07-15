---
type: Reference
title: How to Build and Fine-Tune a Small Language Model
tags: [small-language-models, fine-tuning, transformers, gpt, dpo, deployment, ai-platform]
timestamp: 2026-07-14
source: https://leanpub.com/howtobuildandfine-tuneasmalllanguagemodel
---

# How to Build and Fine-Tune a Small Language Model

A practical, hands-on book by J. Paul Liu (2025, ~485 pp.) whose thesis is that
you do not need billion-dollar infrastructure to build a working language model —
a laptop and the right roadmap are enough. It is framed as a builder's manual, not
a research monograph, aimed at beginners, researchers, and non-programmers who want
to bring AI to their own domain. It grew out of graduate courses, research workshops,
and industry bootcamps.

## Scope

The book walks the full lifecycle of a **small** language model (roughly 125M–350M
parameters — see [models.md](models.md) on model size trade-offs) end to end:

- **Build** — transformer architecture explained step by step, culminating in
  constructing a working GPT from scratch in Chapter 2 (tokenization, self-attention,
  a transformer block, the full model, and training). This is the same architecture
  family covered in [../ai/large-language-models.md](../ai/large-language-models.md)
  and grounded in [../ai/deep-learning.md](../ai/deep-learning.md).
- **Pretrain** — training a small model on your own data.
- **Fine-tune** — adapting the pretrained model to a domain.
- **Align** — preference alignment via **DPO** (Direct Preference Optimization).
- **Deploy** — running the finished model on consumer hardware.

All code ships as Google Colab notebooks, so readers can run everything without local
installation or expensive GPUs.

## Why small models

The book's central argument is a size/cost trade-off: small, domain-tuned models are
cheap to train and to run, and for a bounded task they are often good enough or better
than a giant general model. Worked examples come from real professional use cases —
geohazard analysis, legal document processing, historical text analysis, and
multilingual customer support — reflecting how the material was used in workshops and
production settings. This is the same self-host / small-model motivation that makes
open-weight serving practical (see
[serving-llms-vllm-skypilot.md](serving-llms-vllm-skypilot.md)); once several such
models exist, a [model-router.md](model-router.md) can dispatch each request to the
smallest model that can handle it.

## Where it sits relative to other HAL references

This is a **from-scratch, model-building** book — it complements the systems-level
treatments in HAL rather than overlapping them. For the surrounding production
engineering (data, evaluation, deployment as a discipline) see
[ai-engineering-huyen.md](ai-engineering-huyen.md) and
[designing-machine-learning-systems.md](designing-machine-learning-systems.md);
this book is the piece that teaches you to build and tune the model those systems
would then serve.

## References

- [How to Build and Fine-Tune a Small Language Model — Leanpub](https://leanpub.com/howtobuildandfine-tuneasmalllanguagemodel)
