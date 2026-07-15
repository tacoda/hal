---
type: Reference
title: Numerical Optimization (Nocedal & Wright)
tags: [numerical-optimization, nonlinear-programming, newton-methods, algorithms, optimization]
timestamp: 2026-07-14
source: https://link.springer.com/book/10.1007/978-0-387-40065-5
---

# Numerical Optimization (Nocedal & Wright)

Jorge Nocedal and Stephen Wright's *Numerical Optimization* (Springer, 2nd ed. 2006,
Springer Series in Operations Research and Financial Engineering) is the standard
reference for the **algorithms of continuous optimization** — how you actually compute
a solution to a smooth minimization problem, with attention to convergence rates,
numerical stability, and large-scale practicality. Where a theory text asks *what is
the optimum*, this book asks *what iteration finds it, how fast, and how robustly*.

## Scope and approach

The book is organized around the machinery of iterative descent for smooth problems.

- **Unconstrained optimization.** After the fundamentals (optimality conditions), it
  builds the two global strategies — **line search** and **trust region** — and then
  the search-direction families: steepest descent, nonlinear conjugate gradient,
  **quasi-Newton** methods (BFGS, L-BFGS for large scale), and Newton's method. These
  are the second- and quasi-second-order counterparts to the plain first-order methods
  in [gradient-descent-and-first-order-methods.md](gradient-descent-and-first-order-methods.md),
  and the chapters on calculating derivatives (including automatic differentiation) and
  large-scale methods make them usable at real problem sizes.
- **Constrained optimization.** The theory of constrained optimization (KKT conditions,
  constraint qualifications — see
  [lagrange-multipliers-and-kkt.md](lagrange-multipliers-and-kkt.md)) leads into the
  workhorse algorithms: **linear programming** by both the simplex method and
  interior-point methods (see [linear-programming.md](linear-programming.md) and
  [simplex-method.md](simplex-method.md)), quadratic programming, penalty and augmented
  Lagrangian methods, **sequential quadratic programming (SQP)**, and interior-point
  methods for nonlinear programming.

The whole book is the deep reference behind
[nonlinear-and-numerical-optimization.md](nonlinear-and-numerical-optimization.md): the
convergence analysis, the derivative-computation chapter, and the derivative-free
methods added in the second edition. It pairs naturally with Boyd & Vandenberghe —
[boyd-vandenberghe-convex-optimization.md](boyd-vandenberghe-convex-optimization.md) —
which covers the convex-structure side while this covers the general smooth-algorithm
side.

## Why it matters

Its treatment of quasi-Newton and trust-region methods, and its careful attention to
convergence and conditioning, make it the practitioner's and researcher's manual for
building or choosing an optimization solver.

## References

- [Numerical Optimization — Nocedal & Wright (Springer)](https://link.springer.com/book/10.1007/978-0-387-40065-5)
