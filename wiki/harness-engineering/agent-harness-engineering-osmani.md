---
type: Reference
title: Agent Harness Engineering (Osmani)
tags: [harness-engineering, ai-assisted-development, agents, harness-as-a-service, skills]
timestamp: 2026-07-14
source: https://addyosmani.com/blog/agent-harness-engineering/
---

# Agent Harness Engineering (Osmani)

Addy Osmani's framing of the term the whole field now uses: **a coding agent is
the model plus everything you build around it, and harness engineering treats
that scaffolding as a real artifact.** The discipline is defined by a habit —
*anytime the agent makes a mistake, take the time to engineer a solution so it
never makes that mistake again.* A harness isn't downloaded; it accumulates from
your own failure history.

This is the source of the line quoted across the literature: *"A decent model
with a great harness beats a great model with a bad harness."* See
[Harness Engineering (Sensors & Simulators)](harness-engineering.md) for the
feed-forward/feedback decomposition and [What Is Agent Harness Engineering?](agent-harness-engineering.md)
for the layered view.

## Inner vs outer harness

- **Inner harness** — ships inside the coding agent: tool-use loop, context
  management, sub-agents, built-in prompts. You rarely control it.
- **Outer harness** — what *you* wrap around it: system prompts and `AGENTS.md`,
  skills, tools/MCP servers, sandboxes, hooks, observability. Your leverage lives
  here, because `coding agent = AI model(s) + harness` and if you're not the
  model provider, the harness is the only lever you own.

## Harness-as-a-Service (HaaS)

Osmani surfaces Viv Trivedy's **HaaS** framing: we are moving from building on
**LLM APIs** (which hand you a completion) to building on **harness APIs** (which
hand you a *runtime*). The Claude Agent SDK, Codex SDK, and OpenAI Agents SDK all
point the same way — you get the loop, tool-calling, context management, hooks,
and sandbox primitives out of the box and customize along four pillars: **system
prompt, tools, context, subagents**.

The consequence: agent failures become tractable *configuration* problems rather
than "rebuild the agent from scratch." Trivedy's argument for starting rough —
*"good agent building is an exercise in iteration; you can't do iterations if you
don't have a v0.1."* This is the practitioner-side complement to Aakash Gupta's
market thesis in [2025 Was Agents, 2026 Is Agent Harnesses](2025-agents-2026-agent-harnesses.md).

## References
- [Agent Harness Engineering — Addy Osmani](https://addyosmani.com/blog/agent-harness-engineering/)
