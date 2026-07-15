---
type: Reference
title: Your Agent Orchestrator Is Too Clever (Chris MD Parsons)
tags: [orchestration, multi-agent, bitter-lesson, ralph-loop, simplicity, adoption]
timestamp: 2026-07-14
source: https://chrismdp.com/your-agent-orchestrator-is-too-clever/
---

# Your Agent Orchestrator Is Too Clever (Chris MD Parsons)

January 2026. The argument: the elaborate multi-agent orchestration systems teams are
building — specialised roles, complex handoffs, sophisticated state machines — are mostly
encoding *distrust of the model* rather than a real requirement, and a bare loop with a good
model will beat them. The foil is Steve Yegge's Gas Town, a multi-agent "factory"
coordinating dozens of Claude Code instances (see [Gastown: Rise of AI Factories](../harness-engineering/gastown-rise-of-ai-factories.md)).

## The bitter lesson strikes again

Parsons frames this through Richard Sutton's *bitter lesson*: general methods that scale
with computation beat specialised approaches that hand-encode human knowledge. AI history is
"littered with clever systems that were eventually surpassed by dumber methods running on
better hardware" — chess, image recognition, language models. The same pattern is now
playing out in orchestration. Every specialised role and hand-crafted handoff is human
knowledge baked into the harness; as models improve, that scaffolding becomes dead weight the
model has to work *around*.

## Bare loops beat state machines

The counter-model is the Ralph loop: a bash loop, a prompt file, and a good model, each
iteration starting from a fresh context and reading prior state off the filesystem. It is
monolithic rather than microservice-like — one process doing one thing per loop — which
sidesteps the non-deterministic coordination overhead of many agents talking to each other.
See [Ralph Wiggum, Software Engineer](../harness-engineering/ralph-wiggum-software-engineer.md),
[Everything Is a Ralph Loop](../harness-engineering/everything-is-a-ralph-loop.md), and
[Loop Engineering](../harness-engineering/loop-engineering.md). "A bash loop, a prompt file, and a good model will
let you ship code while you sleep."

## What this means

- **Building orchestration?** Ask what assumptions your system encodes. Are you adding
  complexity because the models *need* it, or because you do not *trust* them? Better model
  plus simpler architecture is often the real answer.
- **Leading AI adoption?** Reconsider coordination overhead. Winners move fast enough to
  exploit what simple loops already enable — smaller teams, radical transparency, willingness
  to let agents make decisions humans used to make. Connects to
  [Org Shape and Team Size](../ai-org/org-shape-team-size.md) and [From Coder to Orchestrator](../ai-org/from-coder-to-orchestrator.md).
- **Individual developer?** Ralph loops work today; you do not need Gas Town or any elaborate
  system.

The caution mirrors [The Law of Leaky Abstractions](../software-engineering/law-of-leaky-abstractions.md): the more
machinery you wrap around a capable model, the more of its capability you spend maintaining
the wrapper. Contrast the multi-agent framing in
[Building Effective Agents](building-effective-agents.md) and [LangGraph](langgraph.md).

## References

- [Your Agent Orchestrator Is Too Clever — Chris MD Parsons](https://chrismdp.com/your-agent-orchestrator-is-too-clever/)
