---
type: Reference
title: "Lecture 03: The Repository as Single Source of Truth"
tags: [harness-engineering, repo-as-spec, context, documentation]
timestamp: 2026-07-17
source: https://walkinglabs.github.io/learn-harness-engineering/en/lectures/lecture-03-why-the-repository-must-become-the-system-of-record/
---

# Lecture 03: The Repository as Single Source of Truth

Your architecture decisions live scattered across Confluence, Slack, Jira, and a few senior
engineers' heads. For humans that barely works — you can ask a colleague or corner someone in
the break room. **For an agent, information not in the repository simply does not exist.**

## Three inputs, that's all

An agent sees exactly three sources: system prompt + task description, file contents from the
repo, and tool execution output. Not your Slack history, not the Jira ticket, not the decision
you hashed out Friday afternoon. It can't "go ask." Its entire working world *is* the repo.

OpenAI states it plainly: **information that doesn't exist in the repo doesn't exist for the
agent** — the "repo as spec" principle, the repository as highest-authority spec document.
Anthropic echoes it: persistent, repo-resident state is a necessary condition for long-task
continuity.

## Proximity beats length

> A 50-line `ARCHITECTURE.md` in `src/api/` beats a 500-page Confluence doc nobody maintains.

This is a *placement* problem, not a "write more docs" problem. Information is only useful when
it's at hand the moment it's needed.

## The fresh-session test

To check whether your map is good enough: open a brand-new agent session, give it only the
repository, and see if it can figure out how to build, test, and where things stand. If it
can't, the knowledge isn't visible — write it down where the agent will find it.

Related: [Context Engineering](../context-engineering.md), [Memory
Engineering](../memory-engineering.md), [Harness Engineering with Codex
(OpenAI)](../harness-engineering-openai-codex.md).

## References
- [Lecture 03: Why the Repository Must Become the System of Record](https://walkinglabs.github.io/learn-harness-engineering/en/lectures/lecture-03-why-the-repository-must-become-the-system-of-record/)
