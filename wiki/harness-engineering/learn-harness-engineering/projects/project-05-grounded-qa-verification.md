---
type: Reference
title: "Project 05: Grounded QA Verification (Role Separation)"
tags: [harness-engineering, project, planner-generator-evaluator, self-verification]
timestamp: 2026-07-17
source: https://walkinglabs.github.io/learn-harness-engineering/en/projects/project-05-grounded-qa-verification/
---

# Project 05: Grounded QA Verification (Role Separation)

**Build:** implement **role separation** — a generator that implements, an evaluator that
reviews, optionally a planner. Pick one substantive upgrade (multi-turn conversation, citation
panel redesign, or document filtering) and keep it constant so role count is the only variable.

**The experiment:** run three variants; the checked-in evaluator rubric scores show the effect:

| Variant | Roles | Rubric score |
|---|---|---|
| `solution/single-role/` | one agent plans + implements + self-reviews | **1.6 / 5** |
| `solution/gen-eval/` | generator + evaluator (with revision evidence) | **3.3 / 5** |
| `solution/plan-gen-eval/` | planner + generator + evaluator (+ sprint contract) | **4.9 / 5** |

Checked-in feature held constant: multi-turn Q&A conversation history. Adding roles — especially
an independent evaluator — is what lifts the score.

Demonstrates [Lecture 09](../declaring-victory-too-early.md) (replace feelings with
execution-based verification) and [Lecture 10](../end-to-end-testing-changes-results.md)
(full-pipeline verification). Repo path: `projects/project-05/`.

## References
- [Project 05: Grounded QA Verification](https://walkinglabs.github.io/learn-harness-engineering/en/projects/project-05-grounded-qa-verification/)
