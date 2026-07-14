---
type: Image
title: 26 Claude Code Commands (Cheat Sheet)
tags: [claude-code, cli, cheatsheet, commands, agents, skills, mcp]
timestamp: 2026-07-14
---

# 26 Claude Code Commands (Cheat Sheet)

A Claude Code CLI slash-command reference (dustinhauer) — terminal commands, not
claude.ai chat.

- **Session control:** `/clear` (clear history), `/resume` (previous session),
  `/branch` (new conversation from current point), `/rewind` (go back to a point),
  `/rename`, `/export`.
- **Model & usage:** `/model`, `/cost` (session cost), `/usage` (model & cost summary),
  `/extra-usage` (detailed breakdown).
- **Project setup:** `/init`, `/memory` (project memory), `/add-dir` (index more dirs),
  `/config`.
- **Code operations:** `/diff` (changes vs codebase), `/security-review` (security
  analysis), `/plan` (project/task plan), `/permissions` (file r/w), `/compact`
  (compress context).
- **Agent layer:** `/agents` (list specialized agents), `/skills` (view/manage skills),
  `/plugin` (manage plugins), `/reload-plugins`, `/mcp` (Model Context Protocol).
- **Interface:** `/theme`, `/color`.

## Cross-links

Overlaps [21 Claude Code Commands](claude-code-commands-21.md) (adds `/branch`,
`/rewind`, `/agents`, `/skills`, `/plugin`, `/security-review`, `/plan`). `/agents` and
`/skills` are the mechanisms in [The Double Dovetail](double-dovetail.md) and
[Engineer the Loop](engineer-the-loop.md).
