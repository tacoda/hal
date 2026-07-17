---
type: Reference
title: "Project 01: Baseline vs Minimal Harness"
tags: [harness-engineering, project, electron, agents-md]
timestamp: 2026-07-17
source: https://walkinglabs.github.io/learn-harness-engineering/en/projects/project-01-baseline-vs-minimal-harness/
---

# Project 01: Baseline vs Minimal Harness

**Build:** a minimal Electron knowledge-base app shell — window, document list (left), Q&A panel
(right), local data directory. The task is easy; getting the agent to finish it reliably is not.

**The experiment:** run the same build **twice** with the same agent (Claude Code *or* Codex, one
choice for both runs):

1. **Weak harness** — `starter/`, only `task-prompt.md`, no AGENTS.md or feature_list.json.
   Measure what the agent completes with zero structure.
2. **Minimal harness** — `solution/`, with `AGENTS.md`, `CLAUDE.md`, `init.sh`,
   `feature_list.json`, `claude-progress.md` pre-placed. Same task, made concrete through rules
   and verification evidence.

Four concrete features to check: window launch, document list, question panel, local data
directory creation. `solution/feature_list.json` holds the expected evidence per feature.

Demonstrates [Lecture 01](../why-capable-agents-still-fail.md) (harness makes unreliable →
reliable) and [Lecture 02](../what-a-harness-actually-is.md) (the five subsystems). Repo path:
`projects/project-01/`.

## References
- [Project 01: Baseline vs Minimal Harness](https://walkinglabs.github.io/learn-harness-engineering/en/projects/project-01-baseline-vs-minimal-harness/)
