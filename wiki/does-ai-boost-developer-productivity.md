---
type: Reference
title: Does AI Actually Boost Developer Productivity? (100k Devs Study)
tags: [developer-productivity, metrics, ai-assisted-development, measurement, research]
timestamp: 2026-07-14
source: https://www.youtube.com/watch?v=tbDDYKRFjhk
---

# Does AI Actually Boost Developer Productivity? (100k Devs Study)

A talk by **Yegor Denisov-Blanch** (Stanford) at the AI Engineer conference,
presenting one of the larger ongoing studies of software engineering
productivity. The framing: after Mark Zuckerberg said AI would replace
mid-level engineers, every CEO asked their CTO "where are we on that?" — the
honest answer being *not far, and we're not sure we want to*. His measured
position: AI is **not one-size-fits-all** — it raises productivity in some
cases and **decreases** it in others, and there are cases where it shouldn't be
used at all.

## The study

Three years of data, run two ways:

- **Time series** — even for participants who joined in 2025, they pull the
  full git history, so they can see trends across COVID, the arrival of AI,
  etc.
- **Cross-sectional** — 600+ companies (enterprise, mid-size, startups),
  **100,000+ engineers**, tens of millions of commits, billions of lines of
  code.

Crucially, most data is from **private repositories**. Public repos are a bad
measurement basis because they aren't self-contained (people contribute on
weekends, irregularly); private repos make a team's or org's productivity far
easier to measure. (The same group earlier produced the controversial "ghost
engineers" finding.)

## The headline result: gross output overstates the gain

AI raises **measured productivity by roughly 15–20%** — but **gross output
looks far higher because much of the new volume is _rework_**: bug fixes to
code the agent just wrote. Counting commits or lines rewards exactly that
churn. This is why output-volume metrics mislead in the AI era, and it's the
central data point behind HAL's [rethinking performance](rethinking-performance.md)
note. It also rhymes with the METR finding that experienced developers *felt*
~20% faster while measured ~19% slower on their own codebases.

## The nuance: slice the data

The value of the study is that AI's impact is **not uniform** — it varies by
task and context (complexity, codebase maturity, developer experience,
language). A single company-wide "productivity number" hides this, mixing large
gains for some cohorts with losses for others. The actionable takeaway is to
**segment**: measure by task class and context against a human baseline rather
than trusting one blended figure.

## Why it matters

This is the empirical backbone for treating AI productivity claims skeptically.
It supports judging engineers on outcomes and leverage, not volume
([rethinking performance](rethinking-performance.md)), and it explains why the
[metrics AI broke](software-engineering-metrics-ai-broke.md) — lines of code,
lead time, deployment frequency — stop meaning what they used to. The rework
finding is the productivity-measurement face of [comprehension debt](comprehension-debt.md).

## References
- [Does AI Actually Boost Developer Productivity? (100k Devs Study) — Yegor Denisov-Blanch, Stanford (AI Engineer)](https://www.youtube.com/watch?v=tbDDYKRFjhk)
