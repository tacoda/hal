---
type: Reference
title: "Project 07: Build Your First Automated Loop"
tags: [harness-engineering, project, loop-engineering, goal-command, maker-checker]
timestamp: 2026-07-17
source: https://walkinglabs.github.io/learn-harness-engineering/en/projects/project-07-loop-engineering-first-loop/
---

# Project 07: Build Your First Automated Loop

The transition project from **Harness** to **Loop**: take the complete harness (Project 06 final
state) and turn it into something that runs on its own. Three progressive experiments across three
branches (`p07-goal-loop`, `p07-timer-loop`, `p07-maker-checker`).

Pick a medium target task with clear completion criteria (e.g. "add unit tests to all modules,
reach 80% coverage"; "add input validation to all API endpoints").

## The three loops

1. **Goal loop** — write `goal.md` with the four parts of a loop: **goal** (what counts as done),
   **verification** (run tests / lint / coverage), **stop condition** (max turns / time / budget),
   **constraints** (what not to touch). Run manually first to record baseline turns/interventions,
   then hand it to `/goal` and let it run unattended.
2. **Timer loop** — turn a monitoring task into a `/loop` on a timer.
3. **Maker-checker loop** — a full generator/verifier loop; experience stepping *outside* the loop.

Uses a terminal multiplexer (tmux/screen) to observe long-running loops; optionally GitHub
Actions or cron for scheduled/event-driven variants. `solution/` has all three loop
implementations plus loop-state files and verification scripts.

Demonstrates [Lecture 13](../from-manual-prompting-to-autonomous-loops.md) (`/goal` = goal +
verification + stop). Connects to the hub's [Loop Engineering](../../loop-engineering.md) and
[Engineer the Loop, Not the Prompt](../../engineer-the-loop.md). Repo path: `projects/project-07/`.

## References
- [Project 07: Build Your First Automated Loop](https://walkinglabs.github.io/learn-harness-engineering/en/projects/project-07-loop-engineering-first-loop/)
