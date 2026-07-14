---
type: Reference
title: How AI Assistance Impacts the Formation of Coding Skills
tags: [anthropic, skill-formation, cognitive-offloading, rct, learning, research]
timestamp: 2026-07-14
source: https://www.anthropic.com/research/AI-assistance-coding-skills
---

# How AI Assistance Impacts the Formation of Coding Skills

Anthropic's **randomized controlled trial** (52 mostly-junior engineers) testing whether
the productivity of AI assistance comes at the cost of *learning*. The tension it probes:
as coding automates, humans still need the skills to catch errors, guide output, and
provide oversight — so does AI shortcut *both* skill and speed, or does speed undermine
skill?

## Design

Participants (weekly Python users, unfamiliar with the **Trio** async library) did a
warm-up, then coded two features using Trio, then took a comprehension quiz. One group
had an AI assistant in the sidebar that could produce correct code on request; the
control coded by hand. The quiz drew on four skill types from CS-education research:
**debugging**, **code reading**, **code writing**, and **conceptual** understanding —
weighted toward the first three as most important for *overseeing* AI-generated code.

## Results

- **The AI group scored 17% lower** on the quiz — 50% vs. 67% for the hand-coding group,
  roughly two letter grades (Cohen's *d* = 0.738, *p* = 0.01).
- The **largest gap was on debugging** — the ability to tell when code is wrong and why,
  which is exactly what oversight of AI-generated code requires.
- AI sped up the task by ~2 minutes, but **not** to statistical significance — several
  participants spent up to 11 minutes (30% of allotted time) composing up to 15 queries.
- **How you use AI decides the outcome.** Grouping by interaction mode:

| Pattern | Behavior | Quiz score |
|---|---|---|
| AI delegation | Wholly relied on AI to write code; fastest, fewest errors | < 40% |
| Progressive AI reliance | Started asking, then delegated all writing | < 40% |
| Iterative AI debugging | Leaned on AI to debug/verify, not to understand | < 40% |
| Generation-then-comprehension | Generated code, then asked follow-up questions | 65%+ |

The control group hit more Trio errors — and likely *learned debugging by resolving them
independently.* **Passive "just make it work" delegation impairs skill development far
more than active, question-driven use.**

## Caveat and connection

Anthropic notes this setup differs from agentic products like Claude Code, where effects
on skill development are likely **more pronounced**. The study is the empirical backbone
cited by [comprehension debt](comprehension-debt.md) and
[Osmani's essay](comprehension-debt-osmani.md); its active-vs-passive lesson is the same
antidote — read, question, keep judgment trained — that [learning the craft](learning-the-craft.md)
depends on.

## Related

- [Comprehension Debt](comprehension-debt.md) — the concept this RCT quantifies.
- [Comprehension Debt (Osmani)](comprehension-debt-osmani.md) — cites the 17% / 40% / 65%
  figures.
- [Learning the Craft](learning-the-craft.md) — active use as the way to keep skills.

## References
- [How AI assistance impacts the formation of coding skills — Anthropic](https://www.anthropic.com/research/AI-assistance-coding-skills)
