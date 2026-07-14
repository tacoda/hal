---
type: Image
title: Six Friction Clusters When Building Agent Harnesses
tags: [harness-engineering, agents, failure-modes, observability, security]
timestamp: 2026-07-14
---

# Six Friction Clusters When Building Agent Harnesses

A dark-theme reference ("Harness Engineering / AI Coding Agents", synthesized from
Perplexity + own research, 2024–2026 practitioner sources) grouping where harness
builds run into trouble.

> **Note:** the source image is low-resolution; cluster titles are legible, the
> per-cluster detail is only partially readable. Sub-points below are a best-effort
> read — verify against the image.

The six clusters:

1. **Context management** — context bloat, error accumulation, state/definition drift, "token dead" or under-used context.
2. **Evaluation & observability** — no ground truth for open-ended tasks; trajectory grading is hard; non-determinism and flaky checks; missing traces / reasoning artifacts.
3. **Security & sandboxing** — prompt injection via inputs; sandbox escape / edge cases; secret & credential exposure; supply-chain risk.
4. **Team & org friction** — ambiguous ownership, shared tuning/maintenance burden, onboarding to the harness itself, spend & governance.
5. **Context distribution** — tool knowledge not compact; context handoff between components/subagents; expert dilution in shared context.
6. **Maintenance debt** — rules/data outgrown; harness more complex than the agent; high cost to run non-deterministic pulls; transient scaffolding treated as permanent.

Common pain states (bottom band): **partial context**, **weak verification**, **tooling
friction**, **no observability** — mapped across lifecycle stages **setup → first run →
team scale → sustained use**.

## Cross-links

The failure-mode companion to [Agent Harness Engineering](agent-harness-engineering.md)
— clusters 1–3 and 6 line up with its four failure modes (over-engineered harness,
retry-masked corruption, cheap validation, observability tax).
