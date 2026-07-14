---
type: Reference
title: "Agent Patterns Quick Reference (Addy Osmani)"
tags: [agents, patterns, subagents, orchestration, claude]
timestamp: 2026-07-14
source: "LinkedIn Learning — Mastering AI-Assisted Development with Addy Osmani"
---

# Agent Patterns Quick Reference (Addy Osmani)

Five patterns for building effective AI agents with Claude (from *Mastering AI-Assisted
Development*, LinkedIn Learning).

1. **RALPH Loop** — React, Act, Learn, Plan, Handle: a cyclical workflow for long-running
   tasks needing continuous adaptation. React to feedback → act on decisions → learn from
   outcomes → plan next iteration → handle errors. Pitfalls: infinite loops, poor learning
   signals, unclear decision criteria.
2. **Beads** — decompose a complex task into independent, sequential subtasks. Each bead
   has clear inputs/outputs, single responsibility, is independently testable; commit one
   bead at a time for clean history.
3. **Multi-Phase Planning** — Plan → Analyze → Design → Implement → Validate, reviewing at
   each phase boundary before proceeding.
4. **Subagents** — delegate specialized tasks to focused agents. Composition modes:
   *sequential* (pipe one's output into the next), *parallel* (run simultaneously, merge),
   *hierarchical* (parent orchestrates children). Be explicit about each subagent's scope,
   expectations, and success criteria.
5. **Agent Swarms** — multiple agents collaborate via shared files/context for large,
   multi-perspective work. Coordinate through shared config + log/state files and a
   message-queue pattern; a lead agent does final integration with version control for
   conflict resolution.

## Cross-links

The pattern vocabulary behind [Agent Harness Engineering](agent-harness-engineering.md)
and the [Loop Engineering Playbook](loop-engineering-playbook.md) (subagents = the
generator/evaluator split; swarms' shared files = the loop's persistence). Sequential/
parallel/hierarchical subagents also appear in [Agentic Engineering Core](agentic-engineering-core.md).

## References

- Course handout from *Mastering AI-Assisted Development* with Addy Osmani, on [LinkedIn Learning](https://www.linkedin.com/learning/) (paid course; PDF not stored — copyrighted material).
