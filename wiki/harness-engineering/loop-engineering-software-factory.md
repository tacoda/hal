---
type: Reference
title: "Loop Engineering: The Breakthrough That Makes the Software Factory Real"
tags: [loop-engineering, software-factory, agents, autonomy, ralph, dark-factory]
timestamp: 2026-07-14
source: https://levelup.gitconnected.com/loop-engineering-the-breakthrough-that-makes-the-software-factory-real-d85826f072df
---

# Loop Engineering: The Breakthrough That Makes the Software Factory Real

Jazz Tong's essay — the **primary source** behind much of HAL's loop-engineering
material. Where [loop engineering](loop-engineering.md) is the Tessl framing and
[the Anthropic playbook](loop-engineering-playbook.md) is the generator/evaluator
view, this is the original narrative that named the shift and coined the five
ingredients those notes cite.

## The thesis

You stop prompting agents and start **engineering the loops that prompt them**.
Boris Cherny (creator of Claude Code): *"I don't prompt Claude anymore. I have
loops that are running. They're the ones prompting Claude and figuring out what
to do. My job is to write loops."* The loop itself is trivial — a few lines —
so the engineering is everything *around* it.

## Five things a production loop needs

1. **Goal** — written into files that outlive the session.
2. **Trigger** — something other than a keystroke (a schedule, a CI event).
3. **Fresh context** — each iteration (the window is a cache that resets).
4. **Verification** — that the agent cannot bypass.
5. **Stop condition** — a defined hand-back to a human.

This is the canonical list every downstream HAL note draws from — see
[loop engineering](loop-engineering.md) and [engineer the loop](engineer-the-loop.md).

## The evidence it's real now

- **Agent runtimes** already run loops for everyone: *"Codex runs coding tasks
  in cloud sandboxes, in parallel, off in the background, and comes back with
  pull requests"* — the platform counterpart in [agent runtime](../ai-platform/agent-runtime.md).
- **The capability trend** — task length a model can complete unattended is
  doubling ~every 7 months ([METR](measuring-ai-long-tasks.md)), moving work from
  supervised to autonomous with each step.
- **Existence proof** — Cursor's GPT-5.2 agent swarm built a web browser from
  scratch, running a week unattended
  ([Cursor's agent swarm](cursor-agent-swarm-browser.md)).

Pushed to its organizational end state this becomes the [dark factory](dark-factory.md):
many loops running with the lights off. The building blocks under it are
[harness engineering](harness-engineering.md) and
[context engineering](context-engineering.md); the inner cycle it wraps is the
one Anthropic describes in [building effective agents](../agentic-coding/building-effective-agents.md).

## References
- [Loop Engineering: The Breakthrough That Makes the Software Factory Real — Jazz Tong](https://levelup.gitconnected.com/loop-engineering-the-breakthrough-that-makes-the-software-factory-real-d85826f072df)
