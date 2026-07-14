---
type: Reference
title: Claude Skills (Willison)
tags: [skills, harness-engineering, context-engineering, agents, mcp, progressive-disclosure]
timestamp: 2026-07-14
source: https://simonwillison.net/2025/Oct/16/claude-skills/
---

# Claude Skills (Willison)

Simon Willison's argument that **Claude Skills may be a bigger deal than MCP** —
and that their power is precisely their *simplicity*. A skill is little more than
a folder with a `SKILL.md`: some Markdown, a tiny bit of YAML metadata, and
optionally a few executable scripts. That's the whole feature.

This note sits at the intersection of two threads in the wiki: skills are a
**feed-forward** element of the harness (see
[Harness Engineering (Sensors & Simulators)](harness-engineering.md)) *and* a
[context engineering](context-engineering.md) technique — a way to keep the right
instructions available without bloating the prompt.

## Why simplicity is the point

Willison contrasts the two designs directly:

- **MCP** is a full **protocol specification** — hosts, clients, servers,
  resources, prompts, tools, sampling, roots, elicitation, and three transports
  (stdio, streamable HTTP, SSE). Heavy, precise, a lot to implement.
- **Skills** are just *"throw in some text and let the model figure it out."*
  They **outsource the hard parts to the LLM harness and the computer
  environment** — which, given what LLMs have proven they can do with tools, is a
  sensible bet.

The pushback ("it's just a Markdown file you tell the agent to read") is *the
point*, not a weakness. The [`AGENTS.md`](agent-harness-engineering.md) pattern
already showed instructions-in-a-file works; skills systematize it.

## Progressive disclosure

The design that makes skills scale: a **short `SKILL.md` header** is what the
agent sees first, and it only loads the fuller body/scripts when the task
actually calls for them. That keeps token cost low until a skill is needed —
progressive disclosure, the same principle behind `index.md` catalogs and
[context engineering](context-engineering.md) generally.

## Portable across models

Because a skill is just files, **nothing ties it to Claude.** You can point Codex
CLI or Gemini CLI at a skills folder — *"read pdf/SKILL.md and create a PDF"* —
and it works, despite those tools having no built-in skills system. Willison
expects a *"Cambrian explosion"* in skills that makes the MCP rush look
pedestrian. Skills as model-legible capabilities are exactly the enabler
Lopopolo cites in [Extreme Harness Engineering for Token Billionaires](extreme-harness-engineering-token-billionaires.md).

## References
- [Claude Skills are awesome, maybe a bigger deal than MCP — Simon Willison](https://simonwillison.net/2025/Oct/16/claude-skills/)
