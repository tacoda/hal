---
type: Reference
title: "Project 06: Complete Harness (Capstone)"
tags: [harness-engineering, project, capstone, ablation, benchmark]
timestamp: 2026-07-17
source: https://walkinglabs.github.io/learn-harness-engineering/en/projects/project-06-runtime-observability-and-debugging/
---

# Project 06: Complete Harness (Capstone)

**The capstone.** Assemble everything from Projects 01–05, run a full benchmark, then a cleanup
pass to verify quality is maintainable. Fixed multi-feature task set covering the whole product
slice: document import, indexing, citation Q&A, runtime observability, and a readable/restartable
repo.

**The experiment:** three runs then an ablation:

1. Weak-harness baseline.
2. Your strongest harness.
3. Cleanup and re-run.
4. **Ablation** — remove one harness component at a time and see which actually matter.

Compare checked-in dirs:

- **starter/** — mostly complete product code, intentionally weak harness: basic `AGENTS.md`, no
  `feature_list.json`, no `session-handoff.md`, no clean-state checklist. No benchmark scripts.
- **solution/** — full harness surface (`AGENTS.md`, `CLAUDE.md`, `feature_list.json`, `init.sh`,
  `session-handoff.md`, `clean-state-checklist.md`, quality/evaluator docs) plus
  `scripts/benchmark.sh` and `scripts/cleanup-scanner.sh`.

Unlike earlier projects, the gap here isn't missing *features* — it's the operating harness
around the app.

Demonstrates [Lecture 11](../observability-inside-the-harness.md) (make the runtime observable)
and [Lecture 12](../clean-state-every-session.md) (clean handoff every session). Repo path:
`projects/project-06/`.

## References
- [Project 06: Runtime Observability and Debugging](https://walkinglabs.github.io/learn-harness-engineering/en/projects/project-06-runtime-observability-and-debugging/)
