---
type: Image
title: 21 Claude Code Commands (Cheat Sheet)
tags: [claude-code, cli, cheatsheet, commands, mcp]
timestamp: 2026-07-14
---

# 21 Claude Code Commands (Cheat Sheet)

A Claude Code slash-command reference (@VamsiPenmetsa).

- **Session:** `/init` (generate CLAUDE.md), `/compact` (compress → save tokens),
  `/clear` (reset conversation), `/cost` (usage & cost), `/status` (model & session),
  `/diff` (all file changes), `/undo` (revert last edit), `/review` (PR code review).
- **Config:** `/model` (switch model), `/config` (settings), `/permissions` (tool
  allow/deny), `/approved-tools` (list permitted), `/mcp` (MCP servers), `/memory`
  (edit CLAUDE.md), `/vim` (vim mode), `/terminal-setup` (shell setup).
- **Auth:** `/login`, `/logout`, `/doctor` (fix problems), `/bug` (report), `/help`.

Side panels:
- **CLAUDE.md hierarchy** (merged additively): `~/.claude/CLAUDE.md` (global) →
  `<project>/CLAUDE.md` → `.claude/CLAUDE.md` (alt path) → `<cwd>/CLAUDE.md` (subdir).
- **CLI modes:** `claude` (REPL), `claude "do X"` (one-shot), `claude -p "…"` (stdout
  for CI/CD), `claude -c` (continue), `--max-turns N`, `--model name`,
  `--output-format json|stream-json`, `claude mcp add`, `claude update`.
- **CLAUDE.md must-haves:** build & test commands, architecture decisions, key file
  paths & structure, code style conventions, PR review workflow.

## Cross-links

A different, overlapping cheat sheet: [26 Claude Code Commands](claude-code-commands-26.md).
`-p` / `--max-turns` power the loops in
[Engineer the Loop, Not the Prompt](engineer-the-loop.md).
