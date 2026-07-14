---
type: Reference
title: Tokenomics — Where Tokens Are Used in Agentic SE
tags: [tokens, cost-management, agents, multi-agent, software-engineering, research, sdlc]
timestamp: 2026-07-14
source: https://arxiv.org/abs/2601.14470
---

# Tokenomics — Where Tokens Are Used in Agentic SE

A research paper (Salim, Latendresse, Khatoonabadi, Shihab) that asks a question
most teams answer only by watching the bill: **when a multi-agent system does
software engineering, where do the tokens actually go?** It's the empirical
complement to the *"human attention, not tokens, is the bottleneck"* claim from
[Extreme Harness Engineering for Token Billionaires](extreme-harness-engineering-token-billionaires.md)
and directly feeds [cost management](cost-management.md).

## The problem

LLM-based **multi-agent (LLM-MA)** systems are increasingly used to automate
software tasks — requirements, code generation, testing — but their **operational
efficiency and resource consumption are poorly understood.** Unpredictable cost
and environmental impact are a real barrier to adoption; you can't budget or
optimize what you can't attribute.

## The study

The authors analyze **execution traces from 30 software-development tasks** run
by the **ChatDev** multi-agent framework on a **GPT-5 reasoning model**, mapping
ChatDev's internal phases onto stages of the Software Development Life Cycle:
**Design → Coding → Code Completion → Code Review** (and further SDLC activities).
The goal is a token *breakdown* — quantifying which development activities consume
the tokens, rather than reporting a single opaque total.

The takeaway for practitioners: **token spend is not uniform across the SDLC**, so
cost optimization should target the phases that actually dominate consumption
rather than trimming everywhere equally. Treat this note as a pointer to the
paper; the specific per-phase percentages live in the PDF.

## References
- [Tokenomics: Quantifying Where Tokens Are Used in Agentic Software Engineering — arXiv 2601.14470](https://arxiv.org/abs/2601.14470)
