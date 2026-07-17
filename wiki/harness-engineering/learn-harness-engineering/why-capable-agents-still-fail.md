---
type: Reference
title: "Lecture 01: Why Capable Agents Still Fail"
tags: [harness-engineering, reliability, agents, swe-bench]
timestamp: 2026-07-17
source: https://walkinglabs.github.io/learn-harness-engineering/en/lectures/lecture-01-why-capable-agents-still-fail/
---

# Lecture 01: Why Capable Agents Still Fail

The strongest 2025 coding agents pass only ~50–60% on SWE-bench Verified — and those are
curated tasks with clear issues and ready-made tests. On everyday work (vague specs, no
tests, implicit rules scattered across the codebase) the rate drops further. The reflex when
an agent runs 20 minutes, says "done," and broke the tests is *reach for a more expensive
model*. Usually the model isn't the problem.

## Same horse, different fates

Anthropic ran the controlled experiment that makes the point: **same prompt** ("build a 2D
retro game editor"), **same model** (Opus 4.5), two runs.

- Bare, no support → 20 min, $9, core features didn't work.
- Full harness (planner + generator + evaluator) → 6 hrs, $200, fully playable game.

The model never changed. What changed was the scaffolding. OpenAI puts it more bluntly: Codex
in a well-harnessed repo goes from *unreliable* straight to *reliable* — a qualitative leap,
not "a bit better." **Harness = all the engineering infrastructure beyond the model weights.**

## Where agents actually get stuck

A handful of recurring failure modes, all fixable outside the model:

- **Vague requirements** — "add a search feature" says almost nothing; a correct guess is luck,
  a wrong one costs several times the rework.
- **Implicit conventions not written down** — the team uses SQLAlchemy 2.0, OAuth on every
  endpoint; unwritten, the agent can't comply.
- **No verification path** — it can't tell whether it succeeded.
- **Lost continuity** — long tasks exhaust context and the thread is dropped.

Each is a *harness* gap, not a capability gap. The rest of the course closes them one at a time.

See also [What Is Agent Harness Engineering?](../agent-harness-engineering.md),
[What Is Harness Engineering? (Hightower)](../hightower-what-is-harness-engineering.md), and
[Measuring AI Ability to Complete Long Tasks](../measuring-ai-long-tasks.md).

## References
- [Lecture 01: Why Capable Agents Still Fail](https://walkinglabs.github.io/learn-harness-engineering/en/lectures/lecture-01-why-capable-agents-still-fail/)
