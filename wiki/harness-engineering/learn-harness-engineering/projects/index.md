---
type: Index
title: Learn Harness Engineering — Practice Projects
tags: [harness-engineering, projects, hands-on, electron]
timestamp: 2026-07-17
source: https://walkinglabs.github.io/learn-harness-engineering/en/projects/
---

# Learn Harness Engineering — Practice Projects

Seven checked-in, code-along exercises that build one product — a local **Electron knowledge-base
app** (document list, Q&A panel, local data) — while adding one harness mechanism per project.
Each ships a `starter/` (weak/partial harness) and a `solution/` (full harness artifacts) so you
run the *same* task both ways and compare. They pair 1:1 with the [13
lectures](../index.md).

| Project | Adds | Lectures |
|---|---|---|
| [01 Baseline vs Minimal Harness](project-01-baseline-vs-minimal-harness.md) | AGENTS.md + init.sh + feature_list.json | [01](../why-capable-agents-still-fail.md), [02](../what-a-harness-actually-is.md) |
| [02 Agent-Readable Workspace](project-02-agent-readable-workspace.md) | ARCHITECTURE/PRODUCT docs + session-handoff | [03](../repository-as-system-of-record.md), [04](../split-instructions-across-files.md) |
| [03 Multi-Session Continuity](project-03-multi-session-continuity.md) | progress log + one-feature-at-a-time gates | [05](../context-across-sessions.md), [06](../initialization-as-its-own-phase.md) |
| [04 Runtime Feedback](project-04-runtime-feedback.md) | structured logs + architecture guard + seeded bug | [07](../task-boundaries-and-overreach.md), [08](../feature-lists-as-harness-primitives.md) |
| [05 Grounded QA Verification](project-05-grounded-qa-verification.md) | planner/generator/evaluator roles | [09](../declaring-victory-too-early.md), [10](../end-to-end-testing-changes-results.md) |
| [06 Complete Harness (Capstone)](project-06-complete-harness-capstone.md) | benchmark + cleanup + ablation study | [11](../observability-inside-the-harness.md), [12](../clean-state-every-session.md) |
| [07 Build Your First Loop](project-07-build-your-first-loop.md) | /goal, /loop, maker-checker | [13](../from-manual-prompting-to-autonomous-loops.md) |

## References
- [Projects](https://walkinglabs.github.io/learn-harness-engineering/en/projects/)
