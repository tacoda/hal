---
type: Reference
title: "Project 03: Multi-Session Continuity"
tags: [harness-engineering, project, state, verification-gates]
timestamp: 2026-07-17
source: https://walkinglabs.github.io/learn-harness-engineering/en/projects/project-03-multi-session-continuity/
---

# Project 03: Multi-Session Continuity

**Build:** add scope control and verification gates. Implement document chunking, metadata
extraction, indexing-progress display, and citation-based Q&A. Track status in
`feature_list.json` — **one feature at a time, never mark "pass" without verification evidence.**

**The experiment:** compare checked-in starter vs solution:

1. **starter/** — Project 02 code, indexing + grounded QA unfinished; has a starter
   `feature_list.json` but lacks the restart/handoff artifacts. Watch whether the agent drifts
   across features or loses state after a restart.
2. **solution/** — completed chunking, metadata, index status, citation QA, plus `init.sh`,
   `session-handoff.md`, `claude-progress.md`, and `clean-state-checklist.md`. Check that each
   feature has concrete evidence before being marked passing.

Four specific product features: document chunking, metadata extraction, indexing status UI,
grounded Q&A with citations.

Demonstrates [Lecture 05](../context-across-sessions.md) (state persistence across sessions) and
[Lecture 06](../initialization-as-its-own-phase.md) (initialize before every session). Repo path:
`projects/project-03/`.

## References
- [Project 03: Multi-Session Continuity](https://walkinglabs.github.io/learn-harness-engineering/en/projects/project-03-multi-session-continuity/)
