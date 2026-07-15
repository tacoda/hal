---
type: Index
title: Agentic Coding
timestamp: 2026-07-14
---

# Agentic Coding

Using coding agents day to day — Claude Code, skills, spec-driven and vibe workflows.

- [A Practical Guide to Building Agents (OpenAI)](a-practical-guide-to-building-agents.md) — when to build an agent, the model/tools/instructions triad, single vs multi-agent, layered guardrails
- [Agent Patterns Quick Reference](agent-patterns-quick-reference.md) — RALPH loop, beads, multi-phase, subagents, swarms
- [Agentic Engineering Core](agentic-engineering-core.md) — sequential + parallel multi-agent core behind guardrails
- [Agentic Engineering Stack for Developers](agentic-engineering-stack.md) — 6-layer stack from dev interface down to infra
- [Aider Repository Map](aider-repository-map.md) — tree-sitter + graph-ranking token-budgeted map, no embeddings
- [Anatomy of the .claude/ Folder](anatomy-of-the-claude-folder.md) — the .claude/ control center: CLAUDE.md, commands, skills, subagents, settings/permissions
- [AutoGen](autogen.md) — Microsoft's layered multi-agent framework where behavior emerges from conversations between agents
- [Automated QA](automated-qa.md) — agents test at the pace agents code; the running-software quality control; SWT-Bench shows writing a catching test is its own hard problem
- [BMAD Method](bmad-method.md) — the heavy end: a pipeline of role-played agents before any code
- [How to Build Your Claude "Clone"](build-your-claude-clone.md) — input→output recipe for a personal AI in your voice
- [Build Your First Claude Automation](build-your-first-claude-automation.md) — same skill: manual → scheduled → cloud-autonomous
- [Building Effective Agents](building-effective-agents.md) — Anthropic: workflows vs agents, the 5 building blocks, ACI advice
- [Chamber of Tech Secrets #54: Spec-Driven Development](chamber-of-tech-secrets-spec-driven-development.md) — keeping AI dev reliable and still vibey via lightweight specs
- [21 Claude Code Commands](claude-code-commands-21.md) — slash-command cheat sheet + CLAUDE.md hierarchy & CLI modes
- [26 Claude Code Commands](claude-code-commands-26.md) — CLI slash-command cheat sheet incl. agents/skills/plugins
- [Claude Code documentation](claude-code-documentation.md) — Anthropic's agentic coding tool and its harness: CLAUDE.md, settings, hooks, skills, subagents, plugins, MCP
- [Claude Code One-Day Training Workbook](claude-code-one-day-training-workbook.md) — Closedloop.ai intensive: primitives, planning, review, workflows, tokens
- [Claude Code Pro Tips](claude-code-pro-tips.md) — CLAUDE.md/AGENTS.md structure, hooks, models, sessions
- [Choose a Claude Code Sandbox Environment](claude-code-sandbox-environments.md) — the isolation ladder from Bash sandbox to VM; filesystem and network isolation together or neither
- [Claude Skills (Willison)](claude-skills-willison.md) — Skills = folder + SKILL.md; simpler than MCP, progressive disclosure, portable
- [Coding Interfaces](coding-interfaces.md) — the AI-driving surface adapts as autonomy rises; the frontier is review, not the IDE's death
- [Collaborating with Agents](collaborating-with-agents.md) — the per-task dial: clarity × risk routes each task to in-loop pairing or hand-off autonomy
- [CrewAI](crewai.md) — role-playing agent orchestration: a crew with roles/goals, tasks under a process, autonomy dialed between Crews and Flows
- [Delete 90% of Your Prompt](delete-90-percent-of-your-prompt.md) — modern models make prompt boilerplate unnecessary
- [Four Files to Save You Two Hours a Day](four-files-ai-workflow.md) — Agents/Context/Memory/Skills.md as a self-improving loop
- [GitHub Spec Kit](github-spec-kit.md) — CLI slash-commands (constitution/specify/plan/tasks/implement) for spec-driven dev
- [Don't Get One-Shotted: An AI-Native Outer Loop (Graphite)](graphite-ai-outer-loop.md) — writing code sped up; review/merge/deploy is now the bottleneck
- [How Claude Code Works in Large Codebases](how-claude-code-works-large-codebases.md) — agentic search over RAG, the harness beats the model, deployment patterns for scale
- [How I Use AI to Code (Parsons)](how-i-use-ai-to-code-parsons.md) — shipping production code AI-first (not vibe coding): build the system, run loops, invest in verification
- [LangChain vs LangGraph](langchain-vs-langgraph.md) — workflow automation vs goal-achieving agentic AI
- [LangGraph](langgraph.md) — orchestration that models an agent's control flow as an explicit typed graph of nodes, edges, shared state
- [LLM Powered Autonomous Agents](llm-powered-autonomous-agents.md) — Lilian Weng's foundational map: LLM as brain plus planning, memory, tool use
- [mattpocock/skills](mattpocock-skills.md) — the light end: composable SKILL.md files; grill-me
- [mini-SWE-agent](mini-swe-agent.md) — 100-line, bash-only, stateless agent scoring >74% on SWE-bench Verified
- [My AI Adoption Journey (Hashimoto)](my-ai-adoption-journey.md) — six steps to agents-always-running; step 5 = engineer the harness
- [Open SWE (LangChain)](open-swe-langchain.md) — coding-agent framework on Deep Agents; per-task isolated cloud sandboxes, parallel runs
- [OpenAI Swarm](openai-swarm.md) — experimental stateless multi-agent lib on two primitives (Agents + handoffs); superseded by the Agents SDK
- [Principles of Agentic Development](principles-of-agentic-development.md) — agents build code, humans direct the system; specs endure, code is ephemeral
- [The Rise of AGENTS.md](rise-of-agents-md.md) — vendor-neutral instruction file; broad support, Claude Code the notable holdout
- [Skills Are Claude Code's Secret Weapon (Parsons)](skills-are-claude-codes-secret-weapon.md) — skills as curated reusable prompts loaded on demand
- [The Mess of Managing Skills Without a Package Manager](skills-without-a-package-manager.md) — skills are reusable but have no distribution layer
- [Spec-Driven Development](spec-driven-development.md) — spec first as durable intent; the structured counterpart to vibe coding
- [The New Code: Specs as the Source of Truth](the-new-code-specs-as-source-of-truth.md) — Grove/OpenAI: spec is source, code the lossy compiled output
- [Understanding SDD: Kiro, spec-kit, Tessl](understanding-sdd-kiro-spec-kit-tessl.md) — Böckeler untangles SDD into three levels across three tools
- [Vibe Coding](vibe-coding.md) — let the model drive without reading the code; safe for throwaways, risky in production
- [Vibe Coding vs. Spec-Driven Development](vibe-coding-vs-spec-driven-development.md) — RedMonk: specs as source of intention, not truth; vibe vs spec is yes-and
- [Why Cursor Ditched Rules for Skills](why-cursor-ditched-rules-for-skills.md) — skills spread like MCP; context should be reusable
- [How to Write a Great agents.md](writing-a-great-agents-md.md) — six core areas; commands early, examples over prose, clear boundaries
- [XML Prompt Scaffold for Coding Agents](xml-prompt-scaffold.md) — context/tasks/rules/tests/review/output fenced in XML
- [You Don't Need Sub-Agents (Vinogradov)](you-dont-need-sub-agents.md) — multi-agent swarms recreate Brooks's coordination cost; a single loop wins
- [Your Agent Orchestrator Is Too Clever (Parsons)](your-agent-orchestrator-is-too-clever.md) — Sutton's bitter lesson: a bare Ralph loop + a good model beats elaborate state machines
- [Introducing Kiro](introducing-kiro.md) — AWS's spec-driven agentic IDE
- [Claude Code: Up and Running (Kousen)](claude-code-book.md) — hands-on O'Reilly onboarding to Claude Code: CLAUDE.md, MCP, permissions, slash commands, multi-agent workflows
- [Agentic Programming (Wilkerson)](agentic-programming-wilkerson.md) — the AI Fluency Ladder (five delegation levels) and building an agentic harness for reliable delegation
- [Build Your Own Coding Agent (Owen)](build-your-own-coding-agent.md) — build Nanocode from scratch in pure Python; "not magic, just a while loop"
