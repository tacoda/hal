---
type: Reference
title: "Claude Code: Up and Running (Kousen)"
tags: [claude-code, agentic-coding, mcp, cli, onboarding, book]
timestamp: 2026-07-14
source: https://www.oreilly.com/library/view/claude-code-up/0642572388782/
---

# Claude Code: Up and Running (Kousen)

An O'Reilly book by **Ken Kousen** (educator, Java Champion) that serves as a hands-on
onboarding guide to Anthropic's Claude Code — the terminal-based agentic coding tool.
The framing is explicit: Claude Code is an *autonomous agent*, not a suggestion engine.
It reads files, writes code across many files, runs shell commands, works with Git, and
reaches external services through the [Model Context Protocol](../ai-platform/model-context-protocol.md).
The book targets developers comfortable in the terminal but new to agentic AI tools.

## What it covers

The pitch is that it teaches "what the documentation doesn't" — the operational
knowledge you accumulate by using the tool rather than reading the man page:

- Where Claude Code looks for `CLAUDE.md` files and how project-specific behavior is
  configured (see [Anatomy of the .claude/ folder](anatomy-of-the-claude-folder.md)).
- How skill path resolution works, and when headless mode beats an interactive session.
- Permissions, trust levels, and context windows — the controls that decide what runs
  and what gets prompted.
- MCP integrations to connect external services.
- Model switching, custom slash commands, and multi-agent workflows.
- Running Claude Code across terminal, IDE, and CI/CD environments.

Stated learning outcomes include installing and authenticating within 15 minutes,
configuring `CLAUDE.md`, wiring MCP integrations, and operating the permission/trust/
context-window model. A companion GitHub repository ships `CLAUDE.md` templates, hooks,
and MCP snippets.

## Where it sits

This is an introductory, practitioner-facing tour of one specific tool — narrower than
the [official Claude Code documentation](claude-code-documentation.md) is exhaustive, and
much lighter than the loop-design theory in
[harness engineering](../harness-engineering/harness-engineering.md). It pairs well with
the applied workflow captured in [how I use AI to code (Parsons)](how-i-use-ai-to-code-parsons.md)
and the model-selection guidance in [models](../ai-platform/models.md).

## References

- [Claude Code: Up and Running (O'Reilly)](https://www.oreilly.com/library/view/claude-code-up/0642572388782/)
