---
type: Reference
title: "Lecture 06: Initialization as Its Own Phase"
tags: [harness-engineering, initialization, setup, workflow]
timestamp: 2026-07-17
source: https://walkinglabs.github.io/learn-harness-engineering/en/lectures/lecture-06-why-initialization-needs-its-own-phase/
---

# Lecture 06: Initialization as Its Own Phase

You start a session and say "add a search feature." The agent jumps straight to coding, then
discovers the test framework isn't configured (10 min to fix), then the migration format is
wrong (more fiddling). The feature lands, but most of the session went to *figuring out how the
project works* rather than building the feature.

## Two fundamentally different jobs

Initialization and implementation optimize for opposite things:

| Phase | Optimization target |
|---|---|
| **Initialization** | reliability + efficiency of *all subsequent* implementation |
| **Implementation** | quantity + quality of verified features *now* |

Mix them and the agent faces a multi-objective problem: build infrastructure *and* write
feature code at once. With no explicit priority, it gravitates to code (directly visible output)
and sacrifices infrastructure (value only shows up later). Result: infrastructure isn't solid,
and the feature code's reliability suffers too.

## The hidden cost: unverified accumulation

Feature code written *before* the test framework is properly configured piles up unverified. The
defects don't show in session 1 (the agent still remembers what it did) — they surface in
session 2, when a fresh agent doesn't know how to run, test, or where things stand.

## The fix: a dedicated init phase

Before any feature work, run a separate phase that gets the base environment ready, **runs the
verification commands through once**, and maps the project structure — leaving a known-good,
reproducible starting point. Pairs naturally with the [fresh-session
test](repository-as-system-of-record.md) and [state
files](context-across-sessions.md). Related: [No Vibes Allowed (Dex
Horthy)](../no-vibes-allowed-dex-horthy.md) on separating research/plan/implement phases.

## References
- [Lecture 06: Why Initialization Needs Its Own Phase](https://walkinglabs.github.io/learn-harness-engineering/en/lectures/lecture-06-why-initialization-needs-its-own-phase/)
