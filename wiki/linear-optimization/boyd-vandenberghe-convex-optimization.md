---
type: Reference
title: Convex Optimization (Boyd & Vandenberghe)
tags: [convex-optimization, duality, interior-point, kkt, optimization]
timestamp: 2026-07-14
source: https://web.stanford.edu/~boyd/cvxbook/
---

# Convex Optimization (Boyd & Vandenberghe)

Stephen Boyd and Lieven Vandenberghe's *Convex Optimization* (Cambridge University
Press, 2004) is the canonical modern text on convex optimization. The publisher lets
the authors keep the full PDF free on the web, which is part of why it became the
default reference for the field. Its central thesis is practical rather than
theoretical: an enormous range of engineering, statistics, and machine-learning
problems can be **recognized as, or reformulated into, convex problems**, and once a
problem is convex it can be solved reliably and efficiently, with a global optimum
guaranteed. The hard skill the book teaches is not running a solver but *modeling* —
learning to see the convex structure hiding inside a messy applied problem.

## Scope and approach

The book is built in three movements.

- **Theory.** It first develops the objects: convex sets (hyperplanes, cones,
  polyhedra, the positive semidefinite cone), convex functions (with the calculus of
  operations that preserve convexity — the real toolkit for recognizing convexity),
  and the standard problem forms: linear programs (LP), quadratic programs (QP),
  second-order cone programs (SOCP), semidefinite programs (SDP), and geometric
  programs. See [convex-optimization.md](convex-optimization.md) and
  [optimization-problems.md](optimization-problems.md).
- **Duality.** The Lagrangian, the dual problem, weak and strong duality, and the
  Karush–Kuhn–Tucker (KKT) optimality conditions get a full and unusually intuitive
  treatment — duality as the source of certificates, sensitivity, and bounds, not just
  a formal construction. See
  [lagrange-multipliers-and-kkt.md](lagrange-multipliers-and-kkt.md) and
  [duality.md](duality.md).
- **Algorithms and applications.** Unconstrained methods (gradient and Newton), then
  equality-constrained Newton, then **interior-point methods** (the barrier and
  primal-dual approaches) that solve the general convex problem. Application chapters
  span approximation, statistical estimation, and geometric problems.

Convex optimization sits underneath much of machine learning — regularized regression,
support vector machines, and many estimation problems are convex — so the modeling
mindset here directly serves [../ai/machine-learning.md](../ai/machine-learning.md).
The book's algorithm chapters connect to the broader continuous-optimization machinery
in [nonlinear-and-numerical-optimization.md](nonlinear-and-numerical-optimization.md)
and to first-order approaches in
[gradient-descent-and-first-order-methods.md](gradient-descent-and-first-order-methods.md);
LP as the simplest convex case links to
[linear-programming.md](linear-programming.md).

## Why it matters

The dividing line in optimization, the authors argue, is not linear versus nonlinear
but convex versus nonconvex. Convex problems are the ones we can actually solve at
scale with confidence; the payoff of the modeling effort is a solution you can trust.

## References

- [Convex Optimization — Boyd & Vandenberghe (free PDF, Stanford)](https://web.stanford.edu/~boyd/cvxbook/)
