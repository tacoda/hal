---
type: Index
title: Distributed Systems
timestamp: 2026-07-14
---

# Distributed Systems

Distributed data & systems — DDIA, integration patterns, Kubernetes, twelve-factor.

- [Designing Data-Intensive Applications](designing-data-intensive-applications.md) — Kleppmann on reliability, scalability, idempotence, backpressure, durability
- [Designing Distributed Systems](designing-distributed-systems.md) — sidecar, ambassador, scatter-gather, work-queue: a pattern language for wiring systems (and agents)
- [Enterprise Integration Patterns](enterprise-integration-patterns.md) — Hohpe & Woolf's 65 messaging patterns for asynchronous integration
- [HTTP QUERY Method](http-query-method.md) — new verb: safe+idempotent like GET, body like POST
- [Kubernetes: Up and Running (3rd ed.)](kubernetes-up-and-running.md) — the reconciler/control-loop pattern: declare desired state, continuously converge reality to it
- [The Outbox Pattern](outbox-pattern.md) — atomic DB+outbox write, reliable at-least-once publish
- [The Twelve-Factor App](twelve-factor-app.md) — twelve rules for portable, stateless, disposable SaaS apps with clean env separation
