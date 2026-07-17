---
type: Reference
title: "Project 02: Agent-Readable Workspace"
tags: [harness-engineering, project, documentation, session-handoff]
timestamp: 2026-07-17
source: https://walkinglabs.github.io/learn-harness-engineering/en/projects/project-02-agent-readable-workspace/
---

# Project 02: Agent-Readable Workspace

**Build:** add *readability* to the repo so a fresh agent can grasp the structure, know progress,
and resume. Implement document import, document detail view, and local persistence — **across two
sessions.**

**The experiment:** run twice from the checked-in dirs:

1. **starter/** — Project 01 code + incomplete import/detail/persistence; docs intentionally
   thinner, **no `session-handoff.md`.** Measure how much a second session re-discovers.
2. **solution/** — same slice completed, with expanded `ARCHITECTURE.md`, `PRODUCT.md`,
   `feature_list.json`, and `session-handoff.md`. Test whether a fresh session resumes from repo
   state alone, no oral context.

Product features: document import, full detail/content loading, persistence across restart. The
harness feature is the handoff-readable workspace itself.

Demonstrates [Lecture 03](../repository-as-system-of-record.md) (repo as single source of truth,
the fresh-session test) and [Lecture 04](../split-instructions-across-files.md) (split
instructions across files). Repo path: `projects/project-02/`.

## References
- [Project 02: Agent-Readable Workspace](https://walkinglabs.github.io/learn-harness-engineering/en/projects/project-02-agent-readable-workspace/)
