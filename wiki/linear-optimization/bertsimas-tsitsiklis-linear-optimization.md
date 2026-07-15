---
type: Reference
title: Introduction to Linear Optimization (Bertsimas & Tsitsiklis)
tags: [linear-programming, simplex, duality, network-flows, integer-programming, optimization]
timestamp: 2026-07-14
source: http://athenasc.com/linoptbook.html
---

# Introduction to Linear Optimization (Bertsimas & Tsitsiklis)

Dimitris Bertsimas and John Tsitsiklis's *Introduction to Linear Optimization* (Athena
Scientific, 1997) is the graduate standard for linear programming and its discrete
relatives. It gives what reviewers call a "unified, insightful, and modern treatment"
of linear optimization — linear programming, network flow problems, and discrete
optimization — combining classical results with the state of the art, and pairing
rigorous theory with strong geometric intuition throughout.

## Scope and approach

- **Foundations and the simplex method.** It opens with the geometry of linear
  programming — polyhedra, extreme points, vertices, and the fundamental fact that an
  optimum, if it exists, is attained at a vertex — and then develops the **simplex
  method** as a principled walk between adjacent vertices, including degeneracy,
  anti-cycling, and the revised simplex. See
  [linear-programming.md](linear-programming.md) and
  [simplex-method.md](simplex-method.md).
- **Duality.** LP **duality** gets a central, geometric treatment: the dual problem,
  weak and strong duality, complementary slackness, and sensitivity analysis, framed
  as the theory of certificates and prices rather than a formal exercise. See
  [duality.md](duality.md).
- **Beyond the simplex.** The book covers **interior-point (large-scale) methods**,
  **network flow problems** as a structured LP subclass with specialized algorithms
  (see [network-flows.md](network-flows.md)), and then crosses into **integer
  programming** — branch-and-bound, cutting planes, and the theory of LP relaxations
  and integrality (see
  [integer-and-combinatorial-optimization.md](integer-and-combinatorial-optimization.md)).

These topics sit inside the broader taxonomy in
[optimization-problems.md](optimization-problems.md); LP is also the simplest convex
case, connecting to
[convex-optimization.md](convex-optimization.md).

## Why it matters

The book is prized for pedagogy: it consistently explains algebraic constructions
through geometric and intuitive pictures, which is why it remains a first-choice
graduate text for a rigorous but readable path into LP.

## References

- [Introduction to Linear Optimization — Bertsimas & Tsitsiklis (Athena Scientific)](http://athenasc.com/linoptbook.html)
