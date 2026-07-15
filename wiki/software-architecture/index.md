---
type: Index
title: Software Architecture
timestamp: 2026-07-14
---

# Software Architecture

Architecture & service design — clean/hexagonal, DDD, microservices, patterns.

- [Architecting for Scale](architecting-for-scale.md) — Atchison's five focus areas: availability vs reliability, the risk matrix, service decomposition, graceful degradation, self-service capacity
- [Building Evolutionary Architectures](building-evolutionary-architectures.md) — Ford/Parsons/Kua: fitness functions as automated architectural guardrails; guided, incremental change
- [Building Microservices (2nd ed.)](building-microservices.md) — Sam Newman: decompose around bounded contexts, independent deployability, integration styles, strangler-fig migration, the operational tax
- [The C4 Model](c4-model.md) — Simon Brown's four-level (context/container/component/code) way to visualise software architecture
- [Clean Architecture](clean-architecture.md) — Uncle Bob on SOLID, component principles, and the Dependency Rule: draw boundaries, keep business rules at the center, defer the details
- [Design It!](design-it.md) — risk-driven architecture + design thinking: significant decisions, quality attributes/ASRs, empathize-define-ideate-prototype, views, design studios, ADRs
- [Design Patterns (Gang of Four)](design-patterns-gof.md) — the GoF's 23 patterns and a shared vocabulary: program to interfaces, favor composition
- [Documenting Architecture Decisions](documenting-architecture-decisions.md) — Nygard's ADR: short in-repo records of the why behind a decision
- [Domain-Driven Design](domain-driven-design.md) — Evans' blue book: bind code to a domain model via ubiquitous language, tactical building blocks, strategic bounded contexts
- [Domain-Driven Design Distilled](domain-driven-design-distilled.md) — Vernon's short on-ramp to DDD: strategic design first (bounded contexts, ubiquitous language, subdomains, context mapping), then tactical (aggregates, events), plus EventStorming
- [Domain Modeling Made Functional](domain-modeling-made-functional.md) — Wlaschin pairs DDD with typed FP: model the domain as algebraic data types to make illegal states unrepresentable; workflows as functions where the type signature is the design
- [Fundamentals of Software Architecture](fundamentals-of-software-architecture.md) — Richards & Ford: architecture characteristics, a catalog of styles, components, the architect's soft skills — everything is a trade-off
- [Hexagonal Architecture & Domain-Driven Design](hexagonal-architecture-ddd.md) — ports & adapters around a DDD core
- [Hexagonal Architecture (Ports & Adapters)](hexagonal-architecture-ports-and-adapters.md) — wrap the app core in an API so users, programs, and tests drive it equally; ports/adapters + one inward-dependency rule
- [Implementing Domain-Driven Design](implementing-domain-driven-design.md) — Vernon's practical "red book": strategic design first, small aggregates, keep the domain pure
- [Microservice Architecture](microservice-architecture.md) — microservices as a goal (speed + safety at scale), not just small services: DDD boundaries, the platform, Conway-driven team alignment
- [Monolith to Microservices](monolith-to-microservices.md) — Sam Newman's evolutionary playbook: when (and when not) to migrate, strangler fig / branch by abstraction / parallel run, and splitting the database with sagas
- [The Mother of All Architecture Diagrams](mother-of-all-architecture-diagrams.md) — one 10-layer blueprint across five computing eras
- [Patterns of Enterprise Application Architecture](patterns-of-enterprise-application-architecture.md) — Fowler's catalog: three-layer architecture + domain-logic, data-source, ORM, web-presentation, and offline-concurrency patterns
- [Production-Ready Microservices](production-ready-microservices.md) — Susan Fowler's eight-principle production-readiness standard + checklist for a uniform availability bar across a service ecosystem
- [Refactoring to Patterns](refactoring-to-patterns.md) — Kerievsky marries Fowler's Refactoring to the GoF patterns: evolve to/toward/away from patterns via small tested steps guided by smells
- [Release It! (2nd ed.)](release-it.md) — Nygard: circuit breaker, bulkhead, timeouts, steady state; capacity patterns; the operational mindset
- [Service-Oriented Architecture](service-oriented-architecture.md) — Erl's canonical SOA text: eight service-orientation design principles, the ESB/orchestration model, and how SOA became the enterprise ancestor of microservices
- [The Software Architect Elevator](software-architect-elevator.md) — Gregor Hohpe: the architect riding between penthouse and engine room; architecture as selling priced options
- [Software Architecture in Practice](software-architecture-in-practice.md) — the SEI foundation: quality attributes and scenarios, tactics, the ATAM evaluation method, views/documentation
- [Software Architecture: The Hard Parts](software-architecture-the-hard-parts.md) — trade-off analysis for distributed architectures: decomposition, pulling data apart, sagas, contracts; "no best practices, only trade-offs"
- [System Design Master Tree](system-design-master-tree.md) — ~50 system-design concepts as a study index
