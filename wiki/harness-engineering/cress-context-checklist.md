---
type: Image
title: "CRESS: A Context-Quality Checklist"
tags: [context-engineering, prompting, harness, agents, checklist]
timestamp: 2026-07-14
---

# CRESS: A Context-Quality Checklist

A mnemonic — "Better Contexts. Better Outputs." — for what a high-quality context should
do. "Good context isn't more. It's CRESS."

| Letter | Property | The context should… | Example |
|---|---|---|---|
| **C** | Current | contain up-to-date information | latest code, logs, docs, environment state |
| **R** | Refutable | contain tests that show with high confidence when the output doesn't satisfy the intent | unit tests, assertions, acceptance criteria that fail if the output is wrong |
| **E** | Empirical | contain information from the real world, not model-generated | real code, real errors, real measurements, real user feedback — no assumptions |
| **S** | Small | contain the least amount of information needed | remove fluff, repetition, irrelevant history |
| **S** | Specific | be unambiguously scoped to one problem | state the exact goal, constraints, inputs, expected output |

## Cross-links

An actionable checklist for the **context management** layer of
[Agent Harness Engineering](agent-harness-engineering.md) — "Refutable" is its verifier
(tests that fail when the output is wrong), "Small" is compaction, "Current/Empirical"
guard against stale or hallucinated context. Complements
[Delete 90% of Your Prompt](../agentic-coding/delete-90-percent-of-your-prompt.md) (keep only what the
model can't infer).
