---
type: Reference
title: Algorithms for Optimization (Kochenderfer & Wheeler)
tags: [optimization, algorithms, stochastic-optimization, gradient-descent, machine-learning, julia]
timestamp: 2026-07-14
source: https://algorithmsbook.com/optimization/
---

# Algorithms for Optimization (Kochenderfer & Wheeler)

Mykel Kochenderfer and Tim Wheeler's *Algorithms for Optimization* (MIT Press, 2019) is
a modern, code-first survey of optimization written from an **engineering-design
perspective**: the recurring frame is designing a system that optimizes a set of
metrics subject to constraints. Every method is presented with the intuition behind the
mathematics and a concrete implementation in the **Julia** language, which makes it a
natural companion for machine-learning and design work where you want to run the
algorithms, not just prove theorems about them.

## Scope and approach

The book sweeps broadly across the modern optimization toolbox:

- **Derivatives and local descent.** Derivatives and their multidimensional
  generalization (gradients, Jacobians, and automatic differentiation), then local
  descent and the **first- and second-order methods** that guide it — the practical
  core of [gradient-descent-and-first-order-methods.md](gradient-descent-and-first-order-methods.md).
- **Stochastic and population methods.** Methods that inject **randomness** into the
  search (simulated annealing, evolutionary and genetic algorithms, particle swarm),
  covering the terrain of [stochastic-optimization.md](stochastic-optimization.md).
- **Constrained and linear optimization.** Linear constrained optimization where both
  objective and constraints are linear, plus general constraint handling.
- **Surrogate and probabilistic models.** Building surrogate and *probabilistic*
  surrogate models (Bayesian optimization) to optimize expensive black-box functions,
  and optimization under uncertainty with uncertainty propagation.
- **Beyond a single objective.** Multiobjective optimization, expression optimization,
  and multidisciplinary design optimization.

Because it treats the full range of problem shapes with a common vocabulary, it maps
directly onto the taxonomy in
[optimization-problems.md](optimization-problems.md). Its algorithm choices — SGD-style
descent, adaptive methods, Bayesian hyperparameter search, evolutionary methods — are
exactly the ones that train and tune modern models, tying it to
[optimization-in-machine-learning.md](optimization-in-machine-learning.md) and
[../ai/deep-learning.md](../ai/deep-learning.md).

## Why it matters

It bridges the gap between mathematical optimization and applied ML/engineering: a
single accessible volume that lets you see, run, and compare the algorithms behind
model training, design search, and black-box tuning.

## References

- [Algorithms for Optimization — Kochenderfer & Wheeler (MIT Press)](https://algorithmsbook.com/optimization/)
