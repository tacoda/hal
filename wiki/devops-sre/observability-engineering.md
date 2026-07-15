---
type: Reference
title: "Observability Engineering"
tags: [observability, telemetry, wide-events, high-cardinality, tracing, slo, testing-in-production, honeycomb]
timestamp: 2026-07-14
source: https://www.honeycomb.io/blog/observability-engineering-book
---

# Observability Engineering

Charity Majors, Liz Fong-Jones, and George Miranda define observability rigorously and
argue that it is a distinct capability from monitoring, essential for the complex,
distributed, and increasingly nondeterministic systems we now run. The book comes out of
Honeycomb's practice and is the canonical text for the modern, event-based view of
observability.

## The three pillars critique vs. the real definition

The popular "three pillars" framing (metrics, logs, traces) is treated as a
**vendor/tooling artifact, not a definition**. Having three data types tells you nothing
about whether you can actually answer new questions about your system. The book's real
definition, borrowed from control theory: **observability is the ability to understand
any internal state of a system from its external outputs — including states you never
anticipated.** Monitoring answers *known-unknowns* (dashboards for failures you predicted);
observability is built to answer **unknown-unknowns** — the novel, never-seen-before
problems that dominate complex systems.

## Wide structured events

The atomic unit of observability is the **wide, structured event**: one richly-dimensioned
record per unit of work (per request), carrying every piece of context you can attach —
user id, build id, region, feature flags, downstream latencies, and so on. Pre-aggregated
metrics throw this context away at write time; wide events preserve it so you can slice
arbitrarily at query time.

## High cardinality and high dimensionality

The power comes from being able to group and filter by fields with enormous numbers of
possible values (**high cardinality** — e.g. user id, request id) and by *many* such
fields at once (**high dimensionality**). This is exactly what metrics systems handle
badly and what lets you isolate "the one customer, on this build, in that region" without
knowing to ask in advance.

## Tracing, SLOs, and testing in production

- **Tracing** — ordering related events in time across services to follow a single request
  through a distributed system, connecting to
  [microservice architecture](../software-architecture/microservice-architecture.md) debugging.
- **SLOs** — service level objectives, error budgets, and burn-based alerting as the
  humane alternative to threshold spam, aligned with
  [Site Reliability Engineering](site-reliability-engineering.md).
- **Testing in production** — because staging can never reproduce real traffic, cardinality,
  and emergent behavior, you must observe real production and treat it as part of the
  development loop, which is why complex systems fail in ways
  [How Complex Systems Fail](../systems-thinking/how-complex-systems-fail.md) predicts.

This same observability-driven approach is what Honeycomb extends to LLM systems in
[observability for LLMs](../ai-platform/honeycomb-observability-for-llms.md), the far end of the
unpredictability spectrum, and it is the mature form of the telemetry practices in
[The DevOps Handbook](devops-handbook.md).

## References

- [Observability Engineering — Honeycomb / O'Reilly](https://www.honeycomb.io/blog/observability-engineering-book)
