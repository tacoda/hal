---
type: Reference
title: "Lecture 11: Make the Agent's Runtime Observable"
tags: [harness-engineering, observability, traces, evaluation]
timestamp: 2026-07-17
source: https://walkinglabs.github.io/learn-harness-engineering/en/lectures/lecture-11-why-observability-belongs-inside-the-harness/
---

# Lecture 11: Make the Agent's Runtime Observable

An agent runs 20 minutes, touches many files, then: "done, but two tests are failing." Why? "Not
sure, might be a timing issue." Which critical paths changed? "Let me look at the code..." The
root cause isn't capability — it's the harness lacking **observability**. Without visibility into
actual runtime state, every decision is a guess.

## The four costs of missing observability

- **Can't distinguish "correct" from "looks correct"** — code review shows *what was written*;
  runtime traces show *what actually ran*. A function can look right and still take a wrong
  execution path on a boundary condition. You need both.
- **Evaluation becomes mysticism** — with no rubrics or acceptance criteria, evaluators (human or
  agent) rely on implicit assumptions; the same output gets wildly different scores.
  Non-reproducible.
- **Retries become blind guesses** — not knowing *why* something failed, the agent retries in a
  random direction, burning tokens fixing unrelated paths.
- **Session-handoff information cliff** — without traces, the next session re-diagnoses from
  scratch. Anthropic: this redundant diagnosis eats **30–50%** of total session time.

Both OpenAI and Anthropic frame reliability as an **evidence problem**: the harness must expose
runtime behavior and evaluation signals in a form that can guide the next decision.

## What to expose

Structured runtime signals — logs, metrics, traces of the actual execution path, plus explicit
scoring rubrics — turned into repo-visible evidence the planner/generator/evaluator loop can act
on. Related: [Observability (Hightower)](../hightower-observability.md), [AI Coding
Sensors](../ai-coding-sensors.md), [Harness Engineering (Sensors &
Simulators)](../harness-engineering.md). Verified work then needs a [clean
handoff](clean-state-every-session.md) (Lecture 12).

## References
- [Lecture 11: Why Observability Belongs Inside the Harness](https://walkinglabs.github.io/learn-harness-engineering/en/lectures/lecture-11-why-observability-belongs-inside-the-harness/)
