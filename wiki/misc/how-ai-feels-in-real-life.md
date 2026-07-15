---
type: Image
title: "How AI Is Explained vs How It Feels in Real Life"
tags: [ai-engineering, agents, humor, failure-modes, rag]
timestamp: 2026-07-14
---

# How AI Is Explained vs How It Feels in Real Life

A humorous illustration (Raghavendra Ragahni) contrasting the marketing pitch of AI with
the day-to-day engineering reality.

- **How AI is explained:** a tidy stroll — "add AI" → "give AI a prompt" → smart app,
  automation & insights.
- **How it feels in real life:** a treacherous obstacle course. Pick a model → prompt
  tweaks → API key? → rate limit → hallucination → bad RAG → chunking → embedding
  mismatch → context window exceeded → GPU OOM → broken JSON → guardrails → latency →
  tool call failed → eval failed → "finally works" → *never touch again*.

Punchline: **AI is not magic; it's engineering, iteration, and understanding the edge
cases.**

## Cross-links

The lived-experience companion to the systematic
[Six Friction Clusters When Building Agent Harnesses](../harness-engineering/agent-harness-friction-clusters.md)
— nearly every gag (RAG, chunking, JSON, guardrails, latency, evals) is one of the
failure modes the harness in [Agent Harness Engineering](../harness-engineering/agent-harness-engineering.md)
exists to catch.
