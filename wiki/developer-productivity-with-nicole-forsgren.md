---
type: Reference
title: Developer Productivity with Nicole Forsgren
tags: [developer-productivity, metrics, dora, space, measurement, engineering-management]
timestamp: 2026-07-14
source: https://www.youtube.com/watch?v=WufjP_WRnPM
---

# Developer Productivity with Nicole Forsgren

A Pragmatic Engineer podcast conversation with **Nicole Forsgren** — co-creator
of the **DORA** and **SPACE** frameworks and lead author of *Accelerate*. She
began as a software engineer at IBM, watched developers burn out under
deadlines set by managers who didn't understand the work, and has spent her
career since on how to measure developer productivity honestly.

## "PRs and diffs are good signals and are terrible signals"

Her signature line, unpacked: PR count and diff size are **both** — they carry
real information *and* mislead. The trap is that leadership hears "productivity"
and reaches for the **economic definition** — rate of output per input — which
**does not map to software**. Code volume is a weak proxy for value, and it's
worse now that agents can emit it on command. A crucial caveat she stresses:
**many senior engineers have low PR/commit output** — that's unsurprising to
anyone who's been in the field, because their leverage isn't in lines shipped.
Judge output by "what gets done through the current system and processes," not
by raw counts.

## No single metric

The throughline of both her frameworks: **there is no one number.** Any single
metric gets gamed and hides tradeoffs. The fix is a **balanced set** across
dimensions — and pairing the **what** (tool/system data) with the **why**
(self-reported developer signal). Self-report is imperfect but often "the best
proxy you can get" — so collect it, listen to it, and stay curious about it.

## The frameworks

- **DORA** — the four delivery metrics (deployment frequency, lead time for
  changes, change failure rate, time to recover) as a signal of *process
  maturity*, not individual output.
- **SPACE** — a deliberately multi-dimensional model: **S**atisfaction,
  **P**erformance, **A**ctivity, **C**ommunication/collaboration, and
  **E**fficiency/flow. The point of five axes is to stop any one number from
  standing in for "productivity" — efficiency and flow, for example, surface
  friction that activity counts miss.

## Why it matters

Forsgren's "good signals and terrible signals" is a load-bearing citation in
HAL's [rethinking performance](rethinking-performance.md) note: once agents
inflate PR and commit volume, output metrics measure the wrong thing, and the
reframe is toward outcomes and leverage. Her multi-dimensional stance is the
antidote to the [metrics AI broke](software-engineering-metrics-ai-broke.md) —
and SPACE's own dimensions bend under AI too (activity balloons, satisfaction
and flow can mask a hollowing-out), which is exactly the [comprehension debt](comprehension-debt.md)
problem in measurement form.

## References
- [Developer productivity with Nicole Forsgren (the creator of DORA) — The Pragmatic Engineer](https://www.youtube.com/watch?v=WufjP_WRnPM)
