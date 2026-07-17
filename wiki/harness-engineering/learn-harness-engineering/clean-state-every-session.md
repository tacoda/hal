---
type: Reference
title: "Lecture 12: Leave a Clean Handoff Every Session"
tags: [harness-engineering, session-hygiene, entropy, golden-rules]
timestamp: 2026-07-17
source: https://walkinglabs.github.io/learn-harness-engineering/en/lectures/lecture-12-why-every-session-must-leave-a-clean-state/
---

# Lecture 12: Leave a Clean Handoff Every Session

An agent runs all afternoon, modifies 20 files, commits, ends. The next session starts and finds
the build broken, tests red, temp debug files scattered, the feature list not updated, progress
opaque. Its first 30 minutes go entirely to *figuring out what the last session did*.

## Entropy growth is the default

Lehman's laws of software evolution: systems under continuous change grow more complex unless
actively managed. Doubly true for agents — every session introduces changes, and without cleanup
at exit, technical debt accumulates exponentially. During five months of Codex experiments,
OpenAI saw agents **copy existing patterns even when inconsistent or suboptimal**, so drift is
inevitable. (The coffee-cup effect: the first mess invites the second.)

## From manual scrubbing to systematic discipline

OpenAI initially spent **20% of every Friday** manually cleaning "AI slop" — which doesn't scale.
Their systematic solution:

- **Encode "golden rules" into the repo** — concrete, mechanical, auto-checkable ("prefer the
  shared utility package over ad-hoc helpers"; "don't YOLO-guess data structures — validate
  boundaries or depend on typed SDKs").
- **Periodic cleanup workflows** — a fleet of background Codex tasks that scan for deviations,
  update quality scores, and open targeted refactoring PRs, most auto-mergeable within a minute.
- **Capture human taste once, enforce it continuously** — turn review comments, refactoring PRs,
  and user-facing bugs into doc updates or, when docs aren't enough, promote the rule into code.

> Technical debt is a high-interest loan; pay it down in small increments each session.

Both OpenAI and Anthropic: long-term reliability depends on **operational discipline**, not just
single-run success. Exit-state quality directly determines the next session's efficiency — the
counterpart to [state persistence](context-across-sessions.md) (Lecture 05). Related: [The Retry
That Booked Marta's Flight Twice](../hightower-the-retry.md), [Dark Factory](../dark-factory.md).

## References
- [Lecture 12: Why Every Session Must Leave a Clean State](https://walkinglabs.github.io/learn-harness-engineering/en/lectures/lecture-12-why-every-session-must-leave-a-clean-state/)
