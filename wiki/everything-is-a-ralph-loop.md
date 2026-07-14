---
type: Reference
title: Everything Is a Ralph Loop
tags: [ralph, loop-engineering, agents, autonomy, self-healing, software-factory]
timestamp: 2026-07-14
source: https://ghuntley.com/loop/
---

# Everything Is a Ralph Loop

Geoffrey Huntley's short manifesto companion to
[Ralph Wiggum as a Software Engineer](ralph-wiggum-software-engineer.md). The
claim: how he builds software is *fundamentally* different from three years ago —
not just "faster with AI," but a different **approach**. Give the machine a goal,
then loop the goal.

## Give it a goal, then loop the goal

Standard practice builds software vertically, brick by brick, with humans doing
the planning, discussion, and verification. Huntley's inversion: express the
**goal**, wrap it in a Ralph loop, and let iteration close the gap while you walk
away — "programming the new computer" AFK.

He describes putting a system under *"the mother of all ralph loops"* to perform
verification automatically: what used to be days of planning and weeks of
verification runs unattended, and any fault becomes just another forward loop to
fix. He reports what he calls a first **evolutionary software auto-heal** — a
loop identified a broken feature, studied the codebase, fixed it, deployed it,
and verified it worked, with no human in the path.

## The stance

> *"What if the models don't stop getting good?"*

The bet is directional: model capability keeps climbing
([METR's doubling trend](measuring-ai-long-tasks.md)), so anyone still hand-
stacking "jenga" will fall behind those building **automated software
factories**. This is the individual-practitioner version of the same end state
as [loop engineering](loop-engineering.md) and the
[dark factory](dark-factory.md) — the [self-improving harness loop](self-improving-harness-loop.md)
run for real, on production systems.

## References
- [everything is a ralph loop — Geoffrey Huntley](https://ghuntley.com/loop/)
