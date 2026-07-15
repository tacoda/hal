---
type: Reference
title: "Systems Thinking for Agentic AI (Najim)"
tags: [agentic-ai, systems-thinking, architecture, llm, orchestration, guardrails, observability, reliability]
timestamp: 2026-07-14
source: https://www.amazon.com/Systems-Thinking-Agentic-AI-Architects/dp/B0H2QLW56D
---

# Systems Thinking for Agentic AI (Najim)

Ediz Najim — a software architect with roughly two decades in distributed systems,
microservices, and production backend platforms — argues that **an LLM alone is not a
system**. The book is written for backend engineers, tech leads, and architects (no ML
background assumed) who already think in APIs, distributed systems, and system design,
and who want to extend that skill set into AI-enabled software.

The through-line is *systems thinking*: prompts, retrieval, tools, memory, and
orchestration are only useful when they work together **inside clear engineering
boundaries** with guardrails, evaluation, observability, and runtime control wrapped
around them. This is the same premise HAL's [harness engineering](harness-engineering.md)
notes make — the leverage is in the scaffolding around the model, not the model itself.

## Scope

The book deliberately targets the production realities that appear *after* the demo works,
not the demo itself:

- **Model behaviour** — how LLMs process language through tokens, embeddings, and
  transformers; controlling output with prompting, structured output, and decoding
  strategies (temperature, top-k, top-p).
- **The moving parts of an agent** — retrieval, tools, memory, and orchestration composed
  into a coherent whole rather than bolted together.
- **Production concerns** — latency, cost, failure handling, tool execution, structured
  outputs, testing, tracing, safety controls, and maintainability.

## Why it belongs in HAL

The "system, not a demo" framing is a systems-thinking lens applied to agents: an agent is
a [complex adaptive system](../systems-thinking/complex-adaptive-systems.md) of interacting
parts whose reliability comes from the [feedback loops](../systems-thinking/feedback-loops.md)
and boundaries around it. That is exactly the argument behind
[loop engineering](loop-engineering.md) — treating the agent's work as a controlled,
observable loop rather than a one-shot generation. See the [AI field hub](../ai/index.md)
for the surrounding concepts (transformers, embeddings, generative models) the book builds on.

## References

- [Systems Thinking for Agentic AI (Amazon)](https://www.amazon.com/Systems-Thinking-Agentic-AI-Architects/dp/B0H2QLW56D)
