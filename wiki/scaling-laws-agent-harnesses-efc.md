---
type: Reference
title: "Scaling Laws for Agent Harnesses via Effective Feedback Compute (EFC)"
tags: [harness-engineering, agents, scaling-laws, verification, feedback, evaluation]
timestamp: 2026-07-14
source: https://arxiv.org/abs/2605.29682
---

# Scaling Laws for Agent Harnesses via Effective Feedback Compute (EFC)

A preprint (Zhang, Wang, Xu, Zhu, Che — Harbin Institute of Technology) arguing that
**agent-harness performance is governed less by how much compute is spent than by how
efficiently raw budget is converted into durable, task-sufficient feedback.**

## The problem

Test-time scaling analyses usually parameterize an agent by *raw expenditure* — tokens,
tool calls, operations, wall time, cost. That doesn't distinguish useful feedback from
redundant or unstable interaction, so raw compute predicts success poorly.

## Effective Feedback Compute (EFC)

A trace-level scaling coordinate that **credits a feedback event only when it is
informative, valid, non-redundant, and retained.** Each event carries four bounded
factors in [0,1]:

- **Informativeness (Iₜ)** — reveals task-relevant information (a new constraint, reduced
  uncertainty, a diagnosed failure, measurable subgoal progress).
- **Validity (Vₜ)** — supported by reliable evidence, not noise.
- **Non-redundancy (Rₜ)** — adds something not already known.
- **Retention (Mₜ)** — is kept and used for subsequent decisions (memory).

EFC accumulates these credited events; **normalizing by task demand (D_task)** allows
comparison across tasks with different feedback requirements.

## Key results

- Predicting failure rate: raw tokens R²=0.33, raw tool calls 0.42; a strong multivariate
  baseline (SAS) 0.88; Oracle-EFC and Estimated-EFC 0.94; **Oracle-EFC/D_task 0.99.**
- **Matched-budget intervention:** improving *feedback quality* raised success from 0.27
  to 0.90 with raw cost and tool calls held fixed.
- On mixed real traces, NRS-EFC/D_task reached R²=0.92 (raw compute near-zero/negative);
  prospective holdout R²=0.85.

EFC decomposes into **harness efficiency** (raw-to-EFC conversion, localized to specific
modules by ablation) and **task demand** (the required EFC scale).

## Cross-links

Quantitative backbone for [Agent Harness Engineering](agent-harness-engineering.md): its
"verification" layer is exactly what raises Iₜ/Vₜ, "context management" is Rₜ/Mₜ, and the
"token blowout"/redundant-work failures in the [Loop Engineering Playbook](loop-engineering-playbook.md)
are raw compute that never becomes EFC. Complements [COMPILOT](compilot-llm-loop-optimization.md),
where compiler feedback is the informative/valid signal, and [CRESS](cress-context-checklist.md)
(Refutable/Empirical/Small ≈ informative/valid/non-redundant context).

## References

- [Scaling Laws for Agent Harnesses via Effective Feedback Compute (arXiv 2605.29682)](https://arxiv.org/abs/2605.29682)
