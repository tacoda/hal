---
type: Index
title: AI Platform
timestamp: 2026-07-14
---

# AI Platform

Infra for AI systems — MCP, gateways, sandboxing, model routing/serving, evals, observability.

- [Agent Observability](agent-observability.md) — traces of every step/tool-call/handoff; the eval substrate and the governance layer when review goes away
- [Agent Runtime](agent-runtime.md) — managed substrate that runs unattended loops; triggers, scheduler, sandboxed workers, lifecycle — a CI/CD runner farm for agents
- [AI Engineering (Chip Huyen)](ai-engineering-huyen.md) — from training models to building reliable apps on them: evaluation, the adaptation ladder, prompt management, observability
- [The AI Factory Stack](ai-factory-stack.md) — LLM/RAG/VectorDB/Agent/MCP/Guardrails/Evals, one role each
- [The AI SDLC](ai-sdlc.md) — the lifecycle as agent-native pipeline spine; spec in, tested software out; sprints give way to "bolts"
- [LLM Observability, Evaluation, Experimentation (Arize)](arize-observability-evals-experimentation.md) — the observe→eval→experiment cycle for non-deterministic systems
- [AWS Agent Registry](aws-agent-registry.md) — managed catalog/governance for agents: IAM, approval workflow, versioning, lifecycle
- [Amazon Bedrock AgentCore Code Interpreter](bedrock-agentcore-code-interpreter.md) — AWS managed isolated sandbox for agent-generated code, session isolation
- [Breaking AI to Fix It (Ian Webster)](breaking-ai-to-fix-it-ian-webster.md) — shipping AI to 200M Discord users birthed Promptfoo and its eval→security pivot
- [Bun as a Secure Sandbox Runtime (proposal)](bun-secure-sandbox-runtime-proposal.md) — request for a Deno-style --secure allow-list permission model
- [Coding Agents Are Hot — AI Engineer NYC](coding-agents-are-hot-ai-engineer-nyc.md) — the industry shifted from vector DBs to evals
- [A Common-Sense Guide to AI Engineering](common-sense-guide-to-ai-engineering.md) — Jay Wengrow book: foundations → chatbots → agents → production
- [Designing Machine Learning Systems](designing-machine-learning-systems.md) — Chip Huyen: in production ML, data/deployment/monitoring dominate; the model is the easy part
- [DSPy](dspy.md) — Khattab et al. replace hand-tuned prompt strings with declarative modules a compiler optimizes against a metric
- [The Enterprise AI Motherboard](enterprise-ai-motherboard.md) — agentic platform as a computer motherboard
- [Enterprise-Ready MCP (WorkOS)](enterprise-ready-mcp.md) — the auth/authz/scale gaps between MCP demos and production
- [Patterns for Building LLM-based Systems (Eugene Yan)](eugene-yan-llm-patterns.md) — seven production patterns mapped data-to-user
- [Evals & LLM-as-a-Judge](evals-llm-as-a-judge.md) — if context is the new code, evals are its tests; run on your codebase, not public benchmarks
- [Execution Sandboxing](execution-sandboxing.md) — run agent code as untrusted-code-from-the-internet; isolation by default is the precondition for autonomy
- [Fixing SWE-bench (Toloka)](fixing-swe-bench-toloka.md) — audit: unfit tests, vague specs, env drift, stale/leaked data; two-step cleanup
- [Gateways Are All You Need](gateways-are-all-you-need.md) — MCP gateway as root of trust; decouple the harness from the data
- [Guardrails Proxy](guardrails-proxy.md) — real-time policy/safety layer (injection, PII, moderation); necessary not sufficient, pairs with red-teaming
- [LLMs Demand Observability-Driven Development (Honeycomb)](honeycomb-observability-for-llms.md) — why nondeterministic LLMs need wide events, traces, high-cardinality querying
- [LiteLLM](litellm.md) — one OpenAI-format interface to 100+ LLMs; router + gateway
- [LLM-as-a-Judge — A Complete Guide](llm-as-a-judge-complete-guide.md) — Hamel: critique shadowing, binary verdicts, validate judge vs human
- [LLM Evals FAQ](llm-evals-faq.md) — error analysis is the game; binary over Likert; generic metrics are useless
- [LLM Safeguards (Whitenack)](llm-safeguards.md) — five LLM failure modes and the around-the-model layers that mitigate each
- [Model Context Protocol (MCP) Architecture](mcp-architecture.md) — standardized host↔server way to connect tools/data
- [MCP Configuration Reference](mcp-configuration-reference.md) — MCP server config, popular servers, security
- [MCP Gateway](mcp-gateway.md) — single root of trust for tool access; tames the observability/access/security hydra so MCP scales past the demo
- [Model Context Protocol](model-context-protocol.md) — the official open standard: host–client–server connection to tools/data
- [Model Router](model-router.md) — one gateway all LLM calls pass through; centralizes routing, keys, caching, logging (where vs allowed vs worth)
- [Models — Match Models to Tasks](models.md) — not "best model" but "best model for this task, at this price"; proprietary vs open-weight, serving with vLLM
- [OpenLLMetry Is All You Need](openllmetry-is-all-you-need.md) — OpenTelemetry-based LLM observability; auto-instrumentation, platform-portable
- [Production AI App — Repository Structure](production-ai-app-structure.md) — annotated dir tree for a production RAG/agent app
- [Public Benchmarks](public-benchmarks.md) — SWE-bench et al.; the coarse filter for what to trial — rot, leak, and aren't your codebase, so pair with your own evals
- [Registries](registries.md) — publish/discover/version/govern skills, tools, MCP servers, agents; a catalog + package manager in one index
- [Serving LLMs 24× Faster with vLLM + SkyPilot](serving-llms-vllm-skypilot.md) — PagedAttention + continuous batching; you own the serving tax
- [Shipping Products When You Don't Know What They Can Do](shipping-products-you-dont-know.md) — Ben Stein: PM work on probabilistic agents, eval = spec
- [LLM — Simon Willison's CLI](simon-willison-llm.md) — one Unix-style CLI over every model, with SQLite logging, schemas, tools, embeddings
- [SWE-bench Leaderboard](swe-bench-leaderboard.md) — real GitHub issues, hidden-test scoring; Verified/Lite/Full/Multilingual variants
- [SWT-Bench: Unit Test Generation](swt-bench-unit-test-generation.md) — test-writing benchmark; F2P tests reproducing an issue, scored by success + coverage
- [τ-bench (TAU-bench)](tau-bench.md) — Sierra's multi-turn rule-following agent benchmark; introduces pass^k for reliability
- [A Proposed Evaluation Framework for Coding Agents](tessl-coding-agent-eval-framework.md) — versioned doc "tiles" lift idiomatic API use ~35%
- [The Prompt Report](the-prompt-report.md) — Schulhoff et al.'s taxonomy of 58 prompting techniques and a 33-term vocabulary mapping the field
- [Usage Panda LLM Proxy](usage-panda-llm-proxy.md) — OSS proxy enforcing security/cost/PII policy between app and LLM API
- [Why AI Evals Are the Hottest New Skill](why-ai-evals-are-the-hottest-skill.md) — Lenny's w/ Hamel & Shreya: evals as highest-ROI skill
- [Why, and How, You Need to Sandbox AI-Generated Code](why-and-how-to-sandbox-ai-generated-code.md) — AI code is untrusted internet code; three threats, capability allow-lists
- [Your AI Product Needs Evals](your-ai-product-needs-evals.md) — Hamel Husain's three levels of LLM evaluation and what a good eval system unlocks
- [Testing AI](testing-ai.md) — Arbon's guide to testing non-deterministic systems: evaluation criteria over assertions, graded oracles, uncertainty as the tester's job
