---
type: Reference
title: Vibe Coding vs. Spec-Driven Development
tags: [spec-driven-development, vibe-coding, ai-assisted-development, intent, workflow]
timestamp: 2026-07-14
source: https://redmonk.com/rstephens/2025/07/31/spec-vs-vibes/
---

# Vibe Coding vs. Spec-Driven Development

Rachel Stephens (RedMonk) argues these are **not opposing camps** but tools for
different stages of the creative process. It's "not an either/or but a yes and."

## Two modes

- **Vibe coding is speculative** — fast, fluid, exploratory. You reason abstractly
  about what *might* work and let AI play the idea out in code. Improvisational and
  powerful, but not always production-ready. See [vibe coding](vibe-coding.md).
- **Spec-driven development is structured** — a methodology that prioritizes
  *intentionality and alignment*. It slows a team down just enough to think clearly
  about what they're building and why. See
  [spec-driven development](spec-driven-development.md).

## The lone developer vs. the team

Vibe coding de facto favors the **lone developer**: the collaboration point is between
the AI assistant and the one builder. A teammate picking the project up later can only
scroll the chat history (if it survives) or dive into the raw source.

Spec-driven development produces **human-readable artifacts** that share design and
intent. Specs document the *why*, not just the *how* — and they outlive both the
developer's memory and the AI's token window.

## "Source of intention," not "source of truth"

Stephens pushes back on the popular claim that "the spec is the source of truth." Her
position: **the source of truth is what builds — the code.** A spec captures *intent*,
filling software's long-standing cultural deficit at explaining its own history (code
comments, reviews, oral tradition). AI vendors have a north star where natural language
supersedes code, and specs could *eventually* become the source of truth — but the
industry is "far from being there in terms of functionality and reliability." For now,
she prefers **source of intention**. (Contrast Sean Grove's stronger
[spec-as-source-of-truth](the-new-code-specs-as-source-of-truth.md) claim.)

## Takeaway

Vibe coding unlocks momentum — the spark to get unstuck or test an idea. Spec-driven
development front-loads clarity and leaves artifacts behind. Match the mode to the
stakes.

## References
- [Vibe Coding vs. Spec-Driven Development — Rachel Stephens, RedMonk](https://redmonk.com/rstephens/2025/07/31/spec-vs-vibes/)
