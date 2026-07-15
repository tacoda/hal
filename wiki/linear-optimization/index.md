---
type: Index
title: Optimization (Linear & Convex)
tags: [optimization, linear-programming, convex-optimization, index]
timestamp: 2026-07-14
---

# Optimization

Choosing the best option from a feasible set — minimize or maximize an objective subject to
constraints. This folder is the college-level core, spanning linear programming, convex
optimization, and the continuous/gradient methods that train models. It is the field
[artificial intelligence](../ai/index.md) leans on for *training*: every model fit is an
optimization problem, and [backpropagation](../ai/backpropagation-and-gradient-descent.md)
is gradient descent. It rests on [mathematics](../math/index.md) (linear algebra,
multivariable calculus) and shares its LP/duality core with
[economics](../economics/index.md) and operations research.

## The shape of the field

Every problem is an [optimization problem](optimization-problems.md): objective, variables,
constraints, feasible region. The great divide is **convex vs non-convex** — for
[convex problems](convex-optimization.md) every local optimum is global, which is why they
are tractable. [Linear programming](linear-programming.md) is the flagship convex case,
solved by the [simplex method](simplex-method.md) and understood through
[duality](duality.md). Smooth continuous problems are solved by
[gradient descent and first-order methods](gradient-descent-and-first-order-methods.md) or
[nonlinear/numerical methods](nonlinear-and-numerical-optimization.md) (Newton, quasi-Newton),
with constraints handled by [Lagrange multipliers and the KKT conditions](lagrange-multipliers-and-kkt.md).
Discreteness makes things hard: [integer & combinatorial optimization](integer-and-combinatorial-optimization.md)
is NP-hard, though [network flows](network-flows.md) are a lucky tractable special case.
[Stochastic optimization](stochastic-optimization.md) handles uncertainty, and
[optimization in machine learning](optimization-in-machine-learning.md) is where all of it
meets [AI](../ai/index.md).

## Concepts

- [Optimization Problems](optimization-problems.md) — objective, variables, constraints, feasible region; the convex/non-convex divide; the field's taxonomy
- [Linear Programming](linear-programming.md) — linear objective over a feasible polytope; the optimum sits at a vertex
- [Simplex Method](simplex-method.md) — Dantzig's vertex-walking LP algorithm; pivoting, the tableau, interior-point contrast
- [Duality](duality.md) — the dual problem, weak/strong duality, complementary slackness, shadow prices
- [Convex Optimization](convex-optimization.md) — convex sets/functions, local=global, the LP/QP/SOCP/SDP ladder
- [Gradient Descent and First-Order Methods](gradient-descent-and-first-order-methods.md) — GD, SGD, momentum/Nesterov, AdaGrad/RMSProp/Adam; the ML workhorse
- [Lagrange Multipliers and KKT](lagrange-multipliers-and-kkt.md) — constrained optimality: the Lagrangian, KKT conditions, the duality link
- [Nonlinear and Numerical Optimization](nonlinear-and-numerical-optimization.md) — Newton, quasi-Newton (BFGS/L-BFGS), line search, trust regions
- [Integer and Combinatorial Optimization](integer-and-combinatorial-optimization.md) — MILP, branch-and-bound, cutting planes, LP relaxation; knapsack, TSP, scheduling
- [Network Flows](network-flows.md) — max-flow/min-cut, shortest path, assignment/matching; integral solutions for free
- [Stochastic Optimization](stochastic-optimization.md) — optimizing under uncertainty: stochastic programming, SGD, online/bandit, robust optimization
- [Optimization in Machine Learning](optimization-in-machine-learning.md) — training as empirical risk minimization; convex ML vs non-convex deep learning; why SGD works

## Canonical works

- [Convex Optimization](boyd-vandenberghe-convex-optimization.md) — Boyd & Vandenberghe; the canonical convex text (free)
- [Numerical Optimization](nocedal-wright-numerical-optimization.md) — Nocedal & Wright; continuous/nonlinear algorithms
- [Introduction to Linear Optimization](bertsimas-tsitsiklis-linear-optimization.md) — Bertsimas & Tsitsiklis; the LP standard
- [Linear Programming: Foundations and Extensions](vanderbei-linear-programming.md) — Vanderbei; simplex and interior-point as peers
- [Algorithms for Optimization](kochenderfer-algorithms-for-optimization.md) — Kochenderfer & Wheeler; modern, code-first, ML-flavored

## Related fields

[Mathematics](../math/index.md) (linear algebra, multivariable calculus, real analysis),
[artificial intelligence](../ai/index.md) (training, deep learning),
[statistics](../statistics/index.md) (MLE as optimization),
[computer science](../computer-science/index.md) (algorithms, NP-hardness), and
[economics](../economics/index.md) (LP, duality, operations research — pending).
