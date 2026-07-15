---
type: Reference
title: How Claude Code Works in Large Codebases
tags: [claude-code, large-codebases, harness, agentic-search, adoption, subagents, claude-md]
timestamp: 2026-07-14
source: https://claude.com/blog/how-claude-code-works-in-large-codebases-best-practices-and-where-to-start
---

# How Claude Code Works in Large Codebases

Anthropic's field guide for running Claude Code on codebases too big to hold in one
context window. Two ideas anchor it: navigation is *agentic* (not index-based), and the
*harness* — not the model — is what determines performance at scale.

## Agentic search, not RAG

Claude Code navigates like an engineer: traverse the filesystem, read files, grep for
what it needs, follow references across the tree. It works from the **live** codebase on
the developer's machine — nothing to embed, index, upload, or keep in sync.

RAG-based coding tools embed the whole repo and retrieve chunks at query time. At scale
this fails silently: embedding pipelines can't keep up with thousands of active
engineers, so retrieval returns a function renamed two weeks ago or a deleted module with
no signal that it's stale. Agentic search sidesteps this — but its tradeoff is that it
needs enough *starting context* to know where to look. Ask for a vague pattern across a
billion-line repo and you hit the context-window limit before the work begins. Quality of
navigation is therefore shaped by how well the codebase is set up.

## The harness matters as much as the model

Five extension points, layered in order — each builds on the last:

1. **CLAUDE.md files** first — the codebase knowledge Claude reads every session.
2. **Hooks** — most valuable as a *self-improving* loop (a stop hook reflects on a session
   and updates config), not just as guardrails.
3. **Skills** — packaged, on-demand expertise.
4. **Plugins** — distribute the above across a team.
5. **MCP servers** — extend reach to internal tools; the best teams expose structured
   search as a callable tool.

Two more capabilities round it out: **LSP integrations** give symbol-level precision
("go to definition", "find all references") so Claude follows real symbols instead of
pattern-matching text — one of the highest-value investments for large multi-language
repos; and **subagents** split exploration from editing (a read-only subagent maps a
subsystem to a file, the main agent then edits from that summary).

## Three configuration patterns from real deployments

- **Layer context with CLAUDE.md + skills** matched to how the codebase is structured.
- **Actively maintain CLAUDE.md as models evolve.** Instructions written for today's model
  can *constrain* a future one — e.g. a rule forcing single-file refactors would block a
  newer model's coordinated cross-file edits. Hooks/skills that compensated for old
  limitations become dead overhead. Plan a config review every 3–6 months, and whenever
  performance plateaus after a major model release.
- **Assign ownership.** The fastest rollouts had infrastructure wired up *before* broad
  access — a small team (sometimes one person) built plugins and MCPs so day-one use was
  productive. The emerging role is an **agent manager** (hybrid PM/engineer owning the
  Claude Code ecosystem); the minimum viable version is a **DRI** with authority over
  settings, permissions, the plugin marketplace, and CLAUDE.md content.

## Related notes

- [Claude Code documentation](claude-code-documentation.md)
- [Harness engineering](../harness-engineering/harness-engineering.md)
- [Self-improving harness loop](../harness-engineering/self-improving-harness-loop.md)
- [Context engineering](../harness-engineering/context-engineering.md)
- [Aider repository map](aider-repository-map.md)
- [AI adoption at org scale](../ai-org/ai-adoption-at-org-scale.md)

## References

- [How Claude Code works in large codebases](https://claude.com/blog/how-claude-code-works-in-large-codebases-best-practices-and-where-to-start)
