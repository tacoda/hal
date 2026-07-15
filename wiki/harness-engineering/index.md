---
type: Index
title: Harness Engineering
timestamp: 2026-07-14
---

# Harness Engineering

The harness/loop/sensor layer around the model — context, memory, feedback loops.

- [2025 Was Agents, 2026 Is Agent Harnesses](2025-agents-2026-agent-harnesses.md) — the model is commodity; the harness is the moat
- [What Is Agent Harness Engineering?](agent-harness-engineering.md) — the 5-layer scaffolding around a model does 80% of the work
- [Agent Harness Engineering (Osmani)](agent-harness-engineering-osmani.md) — model+scaffolding; harness accumulates from failure history; HaaS
- [Six Friction Clusters When Building Agent Harnesses](agent-harness-friction-clusters.md) — where harness builds break, across the lifecycle
- [Agent Memory Systems and Knowledge Graphs](agent-memory-systems-knowledge-graphs.md) — Letta/Mem0/Graphiti/Cognee compared at code level
- [The AI Codebase Maturity Model (ACMM)](ai-codebase-maturity-model.md) — CMMI-inspired levels gated by feedback-loop topology; intelligence in the harness
- [AI Coding Sensors (Böckeler)](ai-coding-sensors.md) — feed-forward vs feedback; sensors let an agent raise its own quality
- [AI Harness Architecture](ai-harness-architecture.md) — the harness as an "AI Operating System"
- [Architecting Agent Memory](architecting-agent-memory.md) — Alake: memory = organizing the window; generate→store→retrieve→update→forget
- [Automated Review & Verification](automated-review-verification.md) — machine-checked diffs; verification asymmetry, adversarial reviewers; catches only what you specified
- [The Autonomy Ladder](autonomy-ladder.md) — 5 rungs of how much "what to do next" leaves your hands
- [Best AI Agent Memory 2026](best-ai-agent-memory-2026.md) — decision tree: pick by the shape of your memory problem
- [Harness Engineering for Coding Agent Users (Böckeler)](bockeler-harness-engineering.md) — guides vs sensors, computational vs inferential, harnesses-within-harnesses
- [Managing Context on the Claude Platform](claude-context-management.md) — context editing (~84% fewer tokens) + file-based memory tool
- [Agentic Auto-Scheduling: COMPILOT](compilot-llm-loop-optimization.md) — off-the-shelf LLM + compiler feedback loop for loop optimization
- [Context Engineering](context-engineering.md) — smallest set of high-signal tokens; fight context rot with progressive disclosure + compaction
- [CRESS: A Context-Quality Checklist](cress-context-checklist.md) — Current/Refutable/Empirical/Small/Specific
- [Cursor's Agent Swarm Built a Browser](cursor-agent-swarm-browser.md) — GPT-5.2 swarm built a browser unattended across millions of LOC
- [Dark Factory](dark-factory.md) — the end state of loop engineering; agents build/test/ship with the lights off, humans define intent + review outcomes
- [A Developer's Day With the Harness](developer-day-with-the-harness.md) — before/after: constant approvals vs review-plan-then-output
- [The Double Dovetail](double-dovetail.md) — determinism and AI-agency nested inside each other
- [Effective Context Engineering for AI Agents (Anthropic)](effective-context-engineering-anthropic.md) — smallest high-signal token set; JIT retrieval, compaction, memory
- [Engineer the Loop, Not the Prompt](engineer-the-loop.md) — define done once; act → verify → refine until true (/goal, /loop)
- [Everything Is a Ralph Loop](everything-is-a-ralph-loop.md) — Huntley manifesto: give it a goal then loop the goal; AFK auto-heal
- [Extreme Harness Engineering for Token Billionaires](extreme-harness-engineering-token-billionaires.md) — 0% human review, >1B tokens/day, attention is the bottleneck
- [Feedback Is the New Bottleneck (Parsons)](feedback-is-the-new-bottleneck.md) — the constraint shifts from generation to verification; build review surfaces, not prompts
- [The Five Levels: Spicy Autocomplete to Dark Factory](five-levels-spicy-autocomplete-to-dark-factory.md) — driving levels mapped to AI coding autonomy
- [Gas Town and the Rise of AI Factories](gastown-rise-of-ai-factories.md) — Yegge: Claude Code running Claude Code; Beads gives agents durable memory
- [Harness Engineering (Sensors & Simulators)](harness-engineering.md) — inner vs outer harness; feed-forward context + feedback sensors/simulators that accumulate from failures
- [Harness Engineering Beyond Skills (Böckeler talk)](harness-engineering-beyond-skills.md) — stop piling up markdown guides; engineer feedback sensors the agent can self-correct against
- [Harness Engineering with Codex (OpenAI)](harness-engineering-openai-codex.md) — 1M LOC in 5 months, 0 hand-written; humans move up a layer
- [The Allergy Was in the Vector Store (Hightower)](hightower-allergy-vector-store.md) — three memory tiers; safety-critical facts load by identity, not similarity
- [Context Assembly (Hightower)](hightower-context-assembly.md) — the window is RAM, not memory; select/compress/isolate/write, and why order matters
- [Human-in-the-Loop (Hightower)](hightower-human-in-the-loop.md) — gate only the irreversible/high-stakes/intent-contradicting slice; silence means denial
- [Multi-Agent Orchestration (Hightower)](hightower-multi-agent-orchestration.md) — the 15x token tax, the three-condition split gate, hub-and-spoke context isolation
- [Observability (Hightower)](hightower-observability.md) — server metrics can't see agent decisions; OpenTelemetry gen_ai.* conventions, drift, promotion gate
- [The Naked Agent (Hightower)](hightower-the-naked-agent.md) — frameworks give a loop, not a harness; it breaks three ways (runaway loop, context rot, silent tool failure)
- [The Retry That Booked Marta's Flight Twice (Hightower)](hightower-the-retry.md) — idempotency guards, intent-before-result checkpoints, durable state for at-most-once side effects
- [Tool Contracts and Validators (Hightower)](hightower-tool-contracts-and-validators.md) — instructions are followed most of the time, contracts every time; validators at the action boundary
- [What Is Harness Engineering? (Hightower)](hightower-what-is-harness-engineering.md) — Agent = Model + Harness; traced from the 1947 Fitts cockpit study to the 2026 vendor convergence
- [Humans and Agents in Software Engineering Loops (Morris)](humans-and-agents-morris.md) — the why-loop/how-loop model; "on the loop" vs "in the loop"
- [Loop Engineering](loop-engineering.md) — the layer above the harness; five loop ingredients + the Ralph pattern; you engineer the loop, not the prompt
- [Loop Engineering Is Just Software Engineering (Piccolo)](loop-engineering-is-just-software-engineering.md) — agent loops are distributed systems; Worker/State/Triggers primitives
- [Loop Engineering (Addy Osmani)](loop-engineering-osmani.md) — write loops not prompts; goal/trigger/fresh-context/verification/stop; worktrees for parallel
- [Loop Engineering: The Anthropic Playbook](loop-engineering-playbook.md) — 4th layer above the harness; 5 moves, 6 parts, generator/evaluator
- [Loop Engineering: The Software Factory](loop-engineering-software-factory.md) — Jazz Tong's primary source: engineer the loops that prompt agents (5 ingredients)
- [Maintainability Sensors for Coding Agents (Böckeler)](maintainability-sensors-for-coding-agents.md) — computational vs inferential sensors; AI modularity review catches design debt linters can't
- [Measuring AI Ability to Complete Long Tasks](measuring-ai-long-tasks.md) — METR: task-completion horizon doubling ~every 7 months
- [MemGPT](memgpt.md) — Packer et al. (Letta) manage the context window like OS virtual memory, paging main ↔ external context
- [Memory Engineering](memory-engineering.md) — the durable layer between runs; episodic/semantic/procedural; RAG → files → knowledge graphs
- [No Vibes Allowed (Dex Horthy)](no-vibes-allowed-dex-horthy.md) — intentional compaction + Research/Plan/Implement for brownfield agents
- [Ralph Wiggum as a Software Engineer](ralph-wiggum-software-engineer.md) — Huntley's while-loop: eventual consistency, tune the loop, state in files
- [Scaling Laws for Agent Harnesses (EFC)](scaling-laws-agent-harnesses-efc.md) — effective feedback compute predicts success better than raw compute
- [Self-Improving Harness Loop](self-improving-harness-loop.md) — weakness mining → propose → regression-test → update
- [The StrongDM Software Factory](strongdm-software-factory.md) — no human writes/reviews; validation vs a Digital Twin Universe replaces review
- [The Middle Loop (Vella)](the-middle-loop.md) — the supervisory layer between the agent's inner loop and the human's outer loop
- [Voyager — Open-Ended Embodied Agent](voyager-embodied-agent.md) — skill library of executable code → 3.3× discovery, 15.3× faster
- [Why Cline Doesn't Index Your Codebase](why-cline-doesnt-index-your-codebase.md) — RAG chunking tears code logic apart; discovery beats a stale index
- [Zep — Temporal Knowledge Graph for Agent Memory](zep-temporal-knowledge-graph.md) — Graphiti's bi-temporal graph; invalidates facts instead of deleting
