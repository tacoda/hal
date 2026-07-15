---
type: Reference
title: 2025 Was Agents, 2026 Is Agent Harnesses
tags: [harness-engineering, agents, ai-assisted-development, moats, harness-as-a-service]
timestamp: 2026-07-14
source: https://aakashgupta.medium.com/2025-was-agents-2026-is-agent-harnesses-heres-why-that-changes-everything-073e9877655e
---

# 2025 Was Agents, 2026 Is Agent Harnesses

Aakash Gupta's market-level thesis: **2025 proved agents *could* work; 2026 is
about making them work *reliably*.** The reliability lives in the harness, not
the model.

The argument in one line: **the model is a commodity.** Claude, GPT, and Gemini
now perform similarly on agentic tasks, so the model is no longer the
differentiator — *the harness determines whether an agent succeeds or fails.*
This is the same claim Addy Osmani makes from the builder's side (see
[Agent Harness Engineering (Osmani)](agent-harness-engineering-osmani.md)) and
that the [sensors & simulators](harness-engineering.md) framing formalizes.

## What a great harness does

A good harness manages the things a raw model can't:

- **Human approvals** — gates on risky actions.
- **Filesystem and tool access** — scoped, not unbounded.
- **Tool orchestration and sub-agents** — routing work across specialists.
- **Prompts and lifecycle** — the loop the agent runs inside.

The design goal is *minimal intervention, maximal safety*: intervene as little
as possible while preventing catastrophic failure.

## Why it's a moat

Manus, LangChain, and Vercel have each poured thousands of engineering hours into
harnesses — and **that investment is a moat model improvements can't erase.**
Because the model floor keeps rising for everyone, the durable competitive edge
comes from *infrastructure, not intelligence*. Gupta's blunt takeaway: **stop
optimizing models, start building harnesses.**

This is the demand-side pressure behind
[Harness-as-a-Service](agent-harness-engineering-osmani.md) — SDKs that let teams
*configure* a well-factored harness instead of building one, and the extreme end
of the trend appears in [Extreme Harness Engineering for Token Billionaires](extreme-harness-engineering-token-billionaires.md).

## References
- [2025 Was Agents. 2026 Is Agent Harnesses. — Aakash Gupta](https://aakashgupta.medium.com/2025-was-agents-2026-is-agent-harnesses-heres-why-that-changes-everything-073e9877655e)
