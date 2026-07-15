---
type: Reference
title: Gas Town, Claude, and the Rise of AI Factories (Steve Yegge)
tags: [ai-factory, orchestration, agents, beads, memory, gastown, steve-yegge, video]
timestamp: 2026-07-14
source: https://www.youtube.com/watch?v=l7PB_ovm8A4
---

# Gas Town, Claude, and the Rise of AI Factories (Steve Yegge)

Steve Yegge (author of the leaked 2011 Google platforms rant; co-author with Gene
Kim of a book on building production software with coding agents, foreword by
Dario Amodei) on **Gas Town** — his project for orchestrating many coding agents
as a team. Interview on TWiT's *Intelligent Machines*.

## What Gas Town is

**Claude Code running Claude Code** — agents running agents, which turns the setup
into a **factory** where you *manage a team* rather than write code. Yegge calls
2026 "the year of orchestrating": lots of orchestrators will appear, all with
roughly the same footprint — an agent you work with that spawns others to get work
done. All the code is AI-written and *not looked at*, which is why it's powerful,
fast, and genuinely unsafe right now (he tells people not to use it).

Gas Town is a themed hierarchy (Mad Max / Waterworld / Vonnegut references): a
human **overseer** above a **mayor** (Claude, like a Kubernetes control plane),
with **crew/pole-cats** doing design, coding, debugging, reviewing. Many of the
roles exist purely to **supervise and push the agents along** — workarounds for
the fact that Opus 4.5 "was never trained to be a factory worker." As models
improve, half those roles will "evaporate." His personal workflow: a mayor plus
two crew, with two crew designated as "sheriffs" that wake up and triage the ~50
AI-generated PRs/day he gets. Terminals are multiplexed with **tmux**.

## The real durable idea: Beads (memory)

The context window is **a cache that resets, not a memory** — clear it and the
agent asks "now what?" Yegge's answer is **Beads**: an issue tracker for agents
that gives them a **memory**. It turns all work into a small **knowledge graph** of
issues (open/closed, future/present, plus a ledger of finished work), which is
then **federatable** — work you can ship between agents. Anthropic later shipped
"tasks," said to be inspired by Beads, taking the **task-graph** idea (not Yegge's
"janky" JSON-in-SQLite implementation; he's migrating it to Dolt, a git database).

> "When you said they're lacking a memory, that is the core problem — and Beads
> solves that, because that becomes their memory."

This is [memory engineering](memory-engineering.md) in the wild: durable state
(episodic + procedural work history) lives **outside the model** so it survives
context resets — the same constraint [loop engineering](loop-engineering.md) keeps
hitting.

## Notes on practice

- Models: 4.5 was an "event horizon" — the first model that could reliably make a
  pinpoint edit in a 1000-line file (the 4o-era breakthrough) *and* reason through
  complex situations. Gas Town was written for a hypothetical "Opus 5" and
  back-ported to 4.5 with hacks; it dissolves on open-weight models.
- Two phases of software: **construction** (writing code — now cheap) vs
  **engineering** (the hard, higher-level thinking — now *more* taxing, since you're
  stuck on hard problems all day). "You just code faster… like a junior teammate
  working really fast that you're reviewing."
- Treat every glitch as a "four-alarm research project"; keep a full mental model
  of the system; throw failed runs away and restart (it's cheap).
- A cautionary thread on **burnout** and value capture: hyper-productivity pushes
  bottlenecks downstream and lets employers extract 100% of the gains — his advice
  is to slow down and keep some of the value for yourself.

## Related

- [Memory Engineering](memory-engineering.md) — Beads is durable agent memory outside the window.
- [Loop Engineering](loop-engineering.md) — the reset-cache constraint Beads addresses.
- [Dark Factory](dark-factory.md) / [The Five Levels](five-levels-spicy-autocomplete-to-dark-factory.md) — Gas Town as a coding-agent factory.
- [AI Factory Stack](../ai-platform/ai-factory-stack.md) — the broader factory architecture.
- [From Coder to Orchestrator](../ai-org/from-coder-to-orchestrator.md) — the overseer/mayor/crew shift in role.

## References
- [Gas Town, Claude, and the Rise of AI Factories with Steve Yegge — TWiT, Intelligent Machines](https://www.youtube.com/watch?v=l7PB_ovm8A4)
