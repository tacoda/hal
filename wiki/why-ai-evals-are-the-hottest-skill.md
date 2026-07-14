---
type: Reference
title: Why AI Evals Are the Hottest New Skill for Product Builders
tags: [evals, product, error-analysis, binary-evals, domain-expert, video]
timestamp: 2026-07-14
source: https://www.youtube.com/watch?v=BsWxPI9UM4c
---

# Why AI Evals Are the Hottest New Skill for Product Builders

Lenny's Podcast interview with **Hamel Husain and Shreya Shankar** — a
show-don't-tell walkthrough of building evals. The spoken companion to their two
written pieces: [LLM Evals FAQ](llm-evals-faq.md) and
[LLM-as-a-Judge — A Complete Guide](llm-as-a-judge-complete-guide.md).

## Why it matters now

The CPOs of both Anthropic and OpenAI have called evals the most important new
skill for product builders. Evals are "the highest-ROI activity you can engage
in" when building an AI product — and the payoff is durable: for most products
you do the heavy work **once**, then build on it. The goal is **not perfect
evals** — it's to *actionably improve the product*.

## The through-line

- **The AI cannot eval itself.** The top misconception. Put a human in the loop.
- **Benevolent dictator.** Appoint one trusted-taste domain expert — often the
  PM — to do open coding. A committee bogs the process down and makes it too
  expensive to actually run.
- **Binary judges.** Their example judge outputs `true`/`false` for a single
  failure mode (e.g. "should a handoff have happened here?"), not a 1–5 score.
- **Use the LLM to draft, but read and edit it.** Fine to have an LLM help write
  the judge prompt or axial codes — never blindly accept the output.

## The eval as spec

A recurring theme across AI builders: the validated eval becomes the product's
real specification. It's evidence the product works and "isn't just built on
vibes" — the same shift Ben Stein describes in
[Shipping Products When You Don't Know What They Can Do](shipping-products-you-dont-know.md).
Connects to [spec-driven development](spec-driven-development.md) and the
independent-verifier principle in [loop engineering](loop-engineering.md).

Shankar's framing: the aim isn't for a few people to win at evals — it's that
*everyone* can build reliable AI products from the same playbook.

## References
- [Why AI evals are the hottest new skill for product builders — Hamel Husain & Shreya Shankar, Lenny's Podcast](https://www.youtube.com/watch?v=BsWxPI9UM4c)
