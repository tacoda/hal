---
type: Image
title: "TDD: Unit Tests and Hexagonal Boundaries"
tags: [tdd, testing, hexagonal-architecture, ports-and-adapters, refactoring]
timestamp: 2026-07-14
---

# TDD: Unit Tests and Hexagonal Boundaries

A diagram (Valentina Jemuović, journal.optivem.com) placing unit tests on a hexagonal
(ports & adapters) architecture.

## Core idea

A unit test is:

- **Coupled to the external system behavior (API)** — it exercises the application
  through its ports, asserting on what the system does.
- **Decoupled from the internal system structure (implementation)** — it does not depend
  on how the inside is built.

Because of that decoupling, **you can safely refactor the internal implementation
without breaking the unit tests**. The test boundary (drawn around the application core)
sits at the ports, not inside the domain.

## Structure shown

- **Driving adapters** (left) take input from a human user or external system into the
  application via the user-side API.
- **Driven adapters** (right) let the application reach a database or external system via
  the server-side API. In tests these are swapped for **test doubles**.

## Cross-links

Same architecture as [Hexagonal Architecture & Domain-Driven Design](hexagonal-architecture-ddd.md).
Refactoring safety is one of the five practices in
[TDD: Five Supporting Practices](tdd-five-practices.md).
