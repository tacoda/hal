---
type: Reference
title: "AI Engineering: Building Applications with Foundation Models"
tags: [ai-engineering, foundation-models, evaluation, prompt-engineering, rag, observability, llm]
timestamp: 2026-07-14
source: https://www.oreilly.com/library/view/ai-engineering/9781098166298/
---

# AI Engineering: Building Applications with Foundation Models

Chip Huyen's 2024 book is the foundation-model successor to
[Designing Machine Learning Systems](designing-machine-learning-systems.md). The premise:
foundation models have collapsed the cost of *getting* a capable model to near zero, so the
engineering work has shifted from training models to *building reliable applications on top of
models you did not train*. AI engineering is that discipline — and it is different enough from
classic ML engineering to deserve its own name, a distinction the field has been drawing (see
[the rise of the AI engineer](rise-of-the-ai-engineer.md)).

## What changed from ML engineering

In traditional ML you own the model and the data; your hard problem is training. In AI
engineering you adapt a model you do not control, through prompting, context, and light
finetuning; your hard problems move to **evaluation, adaptation, and operating the system in
production**. Huyen structures the book around that shift.

## Evaluation is the hard part — and the book's center of gravity

The book treats evaluation as the defining challenge of AI engineering. Open-ended,
generative outputs have no single correct answer, so you cannot lean on accuracy the way you
could with a classifier. Huyen surveys the evaluation toolkit: exact and functional checks
where they apply, similarity and embedding-based comparison, and
**[AI as a judge](evals-llm-as-a-judge.md)** — using a strong model to score another model's
output — along with its biases and how to calibrate against human labels. The recurring
lesson matches the wider field: your eval suite is the asset, and building it is the work
(compare [your AI product needs evals](your-ai-product-needs-evals.md)).

## Adaptation as a ladder of increasing cost

Huyen frames model adaptation as a progression you climb only as far as you need:

```mermaid
flowchart LR
    A[Prompt engineering] --> B[Context / RAG]
    B --> C[Finetuning]
    C --> D[Custom / heavier training]
```

Start with prompt engineering (cheapest, fastest to iterate). Add context and retrieval (RAG)
when the model needs knowledge it does not have. Reach for finetuning only when prompting and
context plateau. The discipline is knowing when to stop climbing — most applications never
need finetuning, and prompt discipline (compare [delete 90% of your prompt](delete-90-percent-of-your-prompt.md))
often beats it.

## Prompt management as engineering, not craft

Prompts are treated as versioned, tested, evaluated artifacts — not strings pasted into code.
Huyen covers prompt organization, defensive prompting against injection and jailbreaks, and
the guardrails (input and output) that a production system needs. This is the same
platform-level thinking as her essay *Building a Generative AI Platform*, which lays out the
production stack step by step: enhance context (RAG), add guardrails, add a model router and
gateway, reduce latency with caching (prompt, exact, semantic), then complex logic and write
actions.

## Observability for LLM applications

Because outputs are probabilistic and failures are subtle, Huyen insists on observability:
metrics, structured logs, and traces that capture the full request path (retrieval, prompt,
model call, tool use, response). You instrument to catch quality regressions, cost blowups,
and latency spikes that no single request reveals. This is the LLM-specific practice covered
in [agent observability](agent-observability.md) and
[Honeycomb's observability for LLMs](honeycomb-observability-for-llms.md).

## Why it belongs on the shelf

*AI Engineering* is the connective tissue between production ML discipline and the LLM-app
era: same systems mindset, new primitives. It anchors the
[AI engineering bookshelf](ai-engineering-bookshelf.md) and reads as the applied companion to
the [common-sense guide to AI engineering](common-sense-guide-to-ai-engineering.md).

## References

- [AI Engineering — O'Reilly](https://www.oreilly.com/library/view/ai-engineering/9781098166298/)
- [Chip Huyen — Building a Generative AI Platform](https://huyenchip.com/2024/07/25/genai-platform.html)
