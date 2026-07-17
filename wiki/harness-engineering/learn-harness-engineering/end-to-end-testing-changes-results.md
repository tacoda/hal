---
type: Reference
title: "Lecture 10: Only a Full Pipeline Run Counts as Verification"
tags: [harness-engineering, e2e-testing, verification, testing-pyramid]
timestamp: 2026-07-17
source: https://walkinglabs.github.io/learn-harness-engineering/en/lectures/lecture-10-why-end-to-end-testing-changes-results/
---

# Lecture 10: Only a Full Pipeline Run Counts as Verification

An agent adds a file-export feature to an Electron app: renderer component, preload script,
service layer — every unit test passes, "done." You click export: wrong path format, dead
progress bar, memory leak on large files. Five component-boundary defects, zero caught by unit
tests. Each part is "correct" alone; problems surface the moment they're wired together.

## The blind spots of unit tests

Unit testing's design philosophy is **isolation** (mock dependencies, focus on the unit) — which
makes it fast and precise but creates systematic blind spots. Defects that only appear when
everything runs together:

- **Interface mismatch** — renderer passes a relative path, preload expects absolute; both
  mocked unit tests pass.
- **State propagation errors** — a migration changes the schema, the ORM cache still holds old
  entries; fresh mock environments never expose it.
- **Resource lifecycle issues** — file handles, DB connections, sockets span components; per-test
  setup/teardown never surfaces contention or leaks.
- **Environment dependency** — passes in the mocked test env, fails in the real one on config,
  latency, or unavailability.

Google's Testing Pyramid: a broad unit base is essential, but stopping there systematically
misses interaction defects. Worse for agents, which tend to run only the fastest tests then
declare done. **Only end-to-end testing can prove the absence of system-level defects.**

## E2E changes behavior, not just results

The subtle part: when an agent *knows* its work will be validated end-to-end, it works
differently — it stops optimizing for "looks correct in isolation" and starts building for the
integrated run. The verification method shapes the work, upstream of the result it produces.

Enforces the [termination check](declaring-victory-too-early.md) (Lecture 09). Related: [AI
Coding Sensors](../ai-coding-sensors.md), [Maintainability Sensors for Coding
Agents](../maintainability-sensors-for-coding-agents.md), [Automated Review &
Verification](../automated-review-verification.md).

## References
- [Lecture 10: Why End-to-End Testing Changes Results](https://walkinglabs.github.io/learn-harness-engineering/en/lectures/lecture-10-why-end-to-end-testing-changes-results/)
