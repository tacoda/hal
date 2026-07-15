---
type: Reference
title: Calculating ROI
tags: [ai-assisted-development, roi, metrics, measurement, cost, org]
timestamp: 2026-07-14
source: https://tessl.io/patterns/scaling-the-org/calculating-roi/
---

# Calculating ROI

Putting an **honest number** on whether AI-enabled engineering pays off — **net**
value after the cost of review, rework, training, and tokens, **not** the gross
speed-up of the first draft. The unit that travels: **outcome per merged,
shipped unit of work**, tracked by task class against a human baseline — not
anecdote, vibes, or lines of code.

## Credible measurements disagree — by task

- **METR:** experienced OSS devs ~**19% slower** with early-2025 AI on familiar
  codebases — even while *feeling* faster — because review/correction outweighed
  gains.
- **Google RCT (96 engineers):** task completion time **dropped ~21%.**

**Both can be true:** AI helps sharply on some task classes and hurts on others,
so a single org-wide "productivity number" is almost always misleading.

## The full cost stack

License fee is a fraction of it. Jellyfish estimates true cost typically lands
at **2–3× the subscription** once you add:

```mermaid
flowchart LR
    S[Subscription fee] --> T[+ usage / token fees]
    T --> A[+ training time]
    A --> D[+ adoption-phase productivity dip]
    D --> G[+ governance]
    G --> SP[+ tool sprawl]
    SP --> TC["≈ 2–3× the subscription<br/>(vendor estimate, directional)"]
```

LOC and velocity/story-point metrics are *too easy to game to mean anything.*

## Why it matters: perceived vs measured

The gap between **perceived** and **measured** gains is the core trap. METR's
devs felt faster while measuring slower; surveys amplify the bias. IBM: 66% of
EMEA leaders claim significant gains, 92% expect agentic ROI within two years —
but that's **self-reported executive sentiment, not measured delivery** (mood,
not evidence). ROI claims built on feeling are unreliable **in both directions.**

## What survives scrutiny

- **Team-level outcomes, not individual scores** (individual metrics get gamed
  instantly — see [rethinking performance](../ai-org/rethinking-performance.md)).
- **Use a control group** where you can (Jellyfish compared 133 Copilot users to
  750 non-users at the same firms).
- **Pair quantitative delivery metrics with qualitative feedback** — catch teams
  that look fast but are burning out untangling AI output.
- **Segment by cohort** — a 30% average can hide **juniors +70% while seniors
  −15%.**
- **Expect a 2–3 sprint lag** before delivery metrics move at all.

**Honest caveat:** some of the largest reported gains come from **changing how
the team works** (moving leverage upstream to specs and verification), *not* the
tool — which makes attribution genuinely hard. Measure net outcomes by task
class.

## Related

- [Rethinking Performance](../ai-org/rethinking-performance.md) — the individual-metric
  version of the same measurement trap.
- [Driving Adoption](../ai-org/driving-adoption.md) — the adoption-phase dip is a line item
  in the cost stack.
- [Before AI / After AI](../ai-org/before-and-after-ai-bottlenecks.md) — where the real
  gains (and bottlenecks) actually move.

## References
- [Calculating ROI — Tessl Patterns](https://tessl.io/patterns/scaling-the-org/calculating-roi/)
