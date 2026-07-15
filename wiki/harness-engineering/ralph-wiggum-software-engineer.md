---
type: Reference
title: Ralph Wiggum as a Software Engineer
tags: [ralph, loop-engineering, agents, autonomy, eventual-consistency, subagents]
timestamp: 2026-07-14
source: https://ghuntley.com/ralph/
---

# Ralph Wiggum as a Software Engineer

Geoffrey Huntley's deep dive on **Ralph** — the technique behind the canonical
loop cited in [loop engineering](loop-engineering.md) and
[the software-factory essay](loop-engineering-software-factory.md). Ralph is how
Huntley builds **CURSED**, a full programming language + LLVM compiler + stdlib,
largely unattended.

## The technique in one line

```bash
while :; do cat PROMPT.md | claude-code; done
```

Put the goal in a file, loop it, one increment per pass. Named after Ralph
Wiggum because it is gloriously dumb — *"the technique is deterministically bad
in an undeterministic world."* It works not because any single run is right, but
on **eventual consistency**: most mistakes are fixed by *more* loops, and the
engineering effort goes into **tuning the loop** where it drifts, not perfecting
a prompt.

## Why there is no perfect prompt

*"There is no such thing as a perfect prompt."* Huntley's CURSED prompt evolved
by sitting and **watching the stream** for patterns of bad behavior and tuning
against them. Taking his prompt verbatim won't reproduce his results — the value
is in the observation-and-tuning discipline, not the text.

## What a real Ralph prompt actually does

The CURSED build prompt is a stack of instructions, roughly:

- **Study first** — read `specs/*` and `fix_plan.md`; search the codebase with
  subagents before assuming something is unimplemented.
- **Fan out** — up to *500 parallel subagents* for search/analysis, but **only
  one** for Rust build/tests (serialize the shared resource).
- **Pick the top N** — do the most important ~10 items from `fix_plan.md` per pass.
- **Verify** — run the tests for the unit changed; fix unrelated failing tests too.
- **Persist state outside the model** — keep `fix_plan.md` and `AGENT.md`
  continuously updated with learnings (via subagents); commit, push, and git-tag
  every green build. State lives in files and git, not the context window.
- **Single source of truth** — no migrations/adapters; delete Rust stdlib in
  favor of the self-hosted implementation.

## The TODO list is the steering wheel

`fix_plan.md` is what Huntley watches "like a hawk" and **throws out often**.
When Ralph runs out of work or goes off the rails (it's Ralph, after all), you
regenerate the plan with a separate planning loop that re-studies specs and
source. The plan, not the model, is where taste and control live — the
[self-improving harness loop](self-improving-harness-loop.md) applied to a plan file.

Companion piece: [everything is a ralph loop](everything-is-a-ralph-loop.md).
Related patterns: [agent patterns quick reference](../agentic-coding/agent-patterns-quick-reference.md),
[execution sandboxing](../ai-platform/execution-sandboxing.md), [dark factory](dark-factory.md).

## References
- [Ralph Wiggum as a "software engineer" — Geoffrey Huntley](https://ghuntley.com/ralph/)
