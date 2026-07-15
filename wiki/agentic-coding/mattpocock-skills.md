---
type: Reference
title: "mattpocock/skills: Skills for Real Engineers"
tags: [skills, claude-code, agent-skills, spec-driven-development, workflow, ai-assisted-development]
timestamp: 2026-07-14
source: https://github.com/mattpocock/skills
---

# mattpocock/skills — Skills for Real Engineers

Matt Pocock's `.claude` directory, published as a set of composable **skills** — the
lightweight end of the spec-driven spectrum, where a "spec" is just a few lines of
intent and steps in a versioned, shareable `SKILL.md`. Contrast the heavy pipelines of
[BMAD](bmad-method.md) and [spec-kit](github-spec-kit.md); same move, far less ceremony.
See [spec-driven development](spec-driven-development.md).

## Two ways to install, two philosophies

- **skills.sh** copies the skills *into* your project so you can hack on them and make
  them your own (works with Codex and other Agent-Skills-standard harnesses too).
- **Claude Code plugin** (`/plugin marketplace add mattpocock/skills`) installs them as
  a read-only, always-current managed bundle you subscribe to rather than fork.

Run `/setup-matt-pocock-skills` once per repo.

## Selected skills

**Engineering** (user-invoked)
- **ask-matt** — a router that tells you which skill/flow fits your situation.
- **grill-with-docs** — a grilling session that also builds your domain model,
  sharpening terminology and updating `CONTEXT.md` and ADRs inline.
- **to-spec** — turn the current conversation into a spec and publish it (no interview,
  just synthesis).
- **to-tickets** — break work into tickets.
- **improve-codebase-architecture** — scan for deepening opportunities, present a visual
  report, then grill through the one you pick.
- **triage** — move issues through a state machine of triage roles.

**Productivity**
- **grill-me** (user-invoked) — get relentlessly interviewed about a plan or design
  until every branch of the decision tree is resolved.
- **grilling** (model-invoked) — the reusable interview loop behind `grill-me` and
  `grill-with-docs`.
- **handoff** — compact the conversation into a handoff doc for another agent.
- **teach** — teach a concept across multiple sessions, using the directory as a
  stateful workspace.
- **writing-great-skills** — the vocabulary and principles that make a skill
  predictable.

## Why it matters

The **grill-me / grilling** skills isolate the single most valuable SDD move —
*interrogate the request before writing the spec* — as a standalone, composable step.
It's the same idea as spec-kit's [`/clarify`](github-spec-kit.md), stripped to its
essence. This is [context engineering](../harness-engineering/context-engineering.md) applied to your own
`.claude` directory: reusable, shareable skill files that shape how the agent works.

## References
- [mattpocock/skills — GitHub](https://github.com/mattpocock/skills)
