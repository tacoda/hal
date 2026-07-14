---
type: Reference
title: Shipping Products When You Don't Know What They Can Do
tags: [product, agents, evals, probabilistic-software, vibe-coding, video]
timestamp: 2026-07-14
source: https://www.youtube.com/watch?v=PthmdT92qNg
---

# Shipping Products When You Don't Know What They Can Do

Ben Stein (co-founder, **Teammates**) at the AI Engineer conference, wearing his
product-manager hat. Teammates builds a platform for designing and managing a
digital workforce — agents given real identity (Gmail, Slack accounts,
personalities). The talk is about the disorientation of doing product work when
the product's behavior is *probabilistic* and even the builder can't say exactly
what it will do.

## The core problem

Classic product discipline assumes you know what the software does. With agents
you often don't. A customer asked "can I tag my teammate in a Google Doc
comment?" and Stein realized he genuinely didn't know what would happen — of
course you *can* tag it; what it *does* is unknown until you try. The old tools —
Figma mockups, a PRD written up front — break down because agent UX is
**visceral and felt**, not something you can imagine on a blank page.

## What changes

- **Bugs vs. features blur.** "She used too many emojis" — is that a bug? Only if
  the spec said so. When behavior is probabilistically generated you need new
  triage categories; "closed: LLM being crazy" becomes a real state.
- **The eval becomes the specification.** Instead of arguing whether a fuzzy
  behavior is a bug, you set a threshold: *"never give a refund without proof of
  purchase — must pass 100%"*, *"this eval passing 90% is a go; below 90% is
  red, don't ship."* The eval is the durable, checkable contract — the same
  eval-as-spec idea Hamel & Shreya push in
  [Why AI Evals Are the Hottest New Skill](why-ai-evals-are-the-hottest-skill.md).
  Product people reading evals is the new specification work.
- **Vibe coding for agent UX is hard.** You can't spec agent feel in advance —
  Stein wrote "the teammate should ask lots of clarifying questions," shipped it,
  and users hated it. You only learn by feeling it. (See [vibe coding](vibe-coding.md).)
- **The sales problem.** He can't play "visionary" (sounds like witchcraft) or
  "honest broker" (he doesn't know how it works either). His 2025 answer:
  "we're inventing the future together."
- **Models silently improve underneath you.** After a model upgrade, teammates
  started verifying their own DB inserts unprompted — capability arriving without
  a code change, the [METR long-task trend](measuring-ai-long-tasks.md) felt from
  the product seat.

The takeaway: keep the timeless product instincts (listen to customers, solve
real problems) but expect the tools and techniques to be upended — faster than
expected. Ties into [from coder to orchestrator](from-coder-to-orchestrator.md)
and [collaborating with agents](collaborating-with-agents.md).

## References
- [Shipping Products When You Don't Know What They Can Do — Ben Stein, Teammates (AI Engineer)](https://www.youtube.com/watch?v=PthmdT92qNg)
