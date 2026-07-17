---
type: Reference
title: "Project 04: Runtime Feedback (Incremental Indexing)"
tags: [harness-engineering, project, observability, architecture-guard]
timestamp: 2026-07-17
source: https://walkinglabs.github.io/learn-harness-engineering/en/projects/project-04-incremental-indexing/
---

# Project 04: Runtime Feedback (Incremental Indexing)

**Build:** add runtime observability (startup logs, import/indexing logs, error states) and
architecture constraints that block cross-layer violations. **Plant a runtime bug** for the agent
to fix.

**The experiment:** compare checked-in starter vs solution:

1. **starter/** — Project 03 code with weak diagnostics. A seeded indexing defect makes
   large-file chunking fail; **no architecture-check script.** Measure how long the agent takes
   to find root cause without runtime signals.
2. **solution/** — structured logger, architecture boundary docs + guard script, fixed chunking
   logic, `clean-state-checklist.md`. See whether logs and boundary checks make the fix faster
   and less invasive.

Files to inspect: `solution/src/services/logger.ts`, `solution/scripts/check-architecture.sh`,
`solution/docs/ARCHITECTURE.md`, `solution/src/services/indexing-service.ts`.

Demonstrates [Lecture 07](../task-boundaries-and-overreach.md) (scope control, WIP=1) and
[Lecture 08](../feature-lists-as-harness-primitives.md) (feature lists constrain what the agent
does). Repo path: `projects/project-04/`.

## References
- [Project 04: Incremental Indexing](https://walkinglabs.github.io/learn-harness-engineering/en/projects/project-04-incremental-indexing/)
