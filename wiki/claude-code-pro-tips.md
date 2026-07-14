---
type: Reference
title: "Claude Code Pro Tips Reference (Addy Osmani)"
tags: [claude-code, claude-md, agents-md, hooks, workflow, mcp]
timestamp: 2026-07-14
source: "LinkedIn Learning — Mastering AI-Assisted Development with Addy Osmani"
---

# Claude Code Pro Tips Reference (Addy Osmani)

Workflow-optimization reference for Claude Code (from *Mastering AI-Assisted
Development*, LinkedIn Learning).

- **CLAUDE.md structure:** overview, objectives, context, success criteria, constraints
  & boundaries (what Claude cannot do), file structure.
- **AGENTS.md:** documents agent definitions — name, system prompt, capabilities,
  available hooks, required tools/permissions, example workflows.
- **Hooks:** *PreToolUse* fires before a tool runs (e.g. validate inputs / check a file
  exists before editing); *PostToolUse* fires after (e.g. verify test results, handle
  errors).
- **Custom slash commands:** reusable workflows defined in AGENTS.md, invoked as
  `/command-name`, shared across a team by committing the file.
- **Model switching:** Haiku (fast — quick tasks, debugging, review), Sonnet (balanced —
  default coding), Opus (powerful — architecture decisions, multi-file refactors).
- **Settings:** permissions, allowed tools, hooks, default model, custom rules.
- **Parallel sessions:** run multiple Claude Code sessions with a separate CLAUDE.md per
  session for context isolation; use git worktrees for isolated feature branches.
- **Shortcuts / CLI flags:** toggle fast mode, start a new session, skip pre-commit hooks,
  preview changes without applying, override the default model.

## Cross-links

Overlaps the command cheat sheets [21](claude-code-commands-21.md) /
[26 Claude Code Commands](claude-code-commands-26.md) and the agent-context files in
[Four Files to Save You Two Hours a Day](four-files-ai-workflow.md); worktrees +
sessions are the isolation mechanism in the [Loop Engineering Playbook](loop-engineering-playbook.md).

## References

- Course handout from *Mastering AI-Assisted Development* with Addy Osmani, on [LinkedIn Learning](https://www.linkedin.com/learning/) (paid course; PDF not stored — copyrighted material).
