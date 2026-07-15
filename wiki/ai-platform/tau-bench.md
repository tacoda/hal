---
type: Reference
title: "τ-bench: A Benchmark for Tool-Agent-User Interaction in Real-World Domains (Yao et al., Sierra, 2024)"
tags: [benchmarks, agents, tool-use, evaluation, reliability, multi-turn]
timestamp: 2026-07-14
source: https://arxiv.org/abs/2406.12045
---

# τ-bench (TAU-bench)

A benchmark from Shunyu Yao, Noah Shinn, Pedram Razavi, and Karthik Narasimhan (Sierra, 2024) built to measure something most agent benchmarks ignore: whether a language agent can hold a real conversation with a user *and* obey domain-specific rules. Both are prerequisites for deploying agents in the real world, and both are absent from benchmarks that score a single-shot task in isolation.

## What it tests

τ-bench emulates a dynamic conversation between:

- a **user**, simulated by a language model, who reveals needs over multiple turns; and
- a **language agent**, given a set of domain-specific **API tools** and a set of **policy guidelines** it must follow.

The agent has to gather intent through dialogue, take the right tool actions, and stay within policy — across domains like retail and airline customer service.

## How it scores

Evaluation is objective and state-based: at the end of a conversation, τ-bench compares the **actual database state** against an **annotated goal state**. Either the world ended up correct or it did not — no rubric grading of the transcript.

Its headline contribution is a reliability metric, **pass^k**: the probability that the agent succeeds on *all* k independent trials of the same task. Unlike pass@k (success on *any* of k tries), pass^k punishes inconsistency — an agent that solves a task sometimes but not reliably scores poorly.

## Findings

Even strong function-calling agents (e.g., gpt-4o) succeed on **fewer than 50%** of tasks, and are strikingly inconsistent: **pass^8 < 25% in the retail domain**. The takeaway is that raw capability is not the bottleneck — *consistency and reliable rule-following* are. This motivates methods that make agents act dependably across repeated trials.

## Why it matters here

τ-bench sits alongside HAL's other evaluation notes — [public benchmarks](public-benchmarks.md), [SWE-bench leaderboard](swe-bench-leaderboard.md), [evals: LLM as a judge](evals-llm-as-a-judge.md) — but its distinctive lens is *reliability over repeated runs*, which speaks directly to [agent observability](agent-observability.md) and to designing a dependable loop as in [engineer the loop](../harness-engineering/engineer-the-loop.md). The pass^k idea is a concrete, optimizable target for systems like [DSPy](dspy.md) and a useful counterweight to single-shot "it worked once" evaluation.

## References

- [τ-bench: A Benchmark for Tool-Agent-User Interaction in Real-World Domains (arXiv:2406.12045)](https://arxiv.org/abs/2406.12045)
