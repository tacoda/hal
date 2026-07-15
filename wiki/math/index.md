---
type: Index
title: Mathematics
tags: [math, index]
timestamp: 2026-07-14
---

# Mathematics

The language the rest of HAL is written in. This folder is the college-level core:
foundations (logic, sets, proof), the continuous world (calculus, analysis, differential
equations), structure (linear & abstract algebra, number theory, topology), the discrete
world (combinatorics, graphs), and information theory. It is the substrate under
[artificial intelligence](../ai/index.md), [statistics](../statistics/index.md),
[computer science](../computer-science/index.md), and
[systems thinking](../systems-thinking/index.md).

## The shape of the field

Everything rests on [proof and logic](mathematical-proof-and-logic.md) and
[set theory](set-theory.md) — how we state things precisely and establish them. From
there the field splits into the **continuous** ([calculus](calculus.md) →
[multivariable calculus](multivariable-calculus.md) → [real analysis](real-analysis.md);
[differential equations](differential-equations.md)), the **structural**
([linear algebra](linear-algebra.md), [abstract algebra](abstract-algebra.md),
[number theory](number-theory.md), [topology](topology.md)), and the **discrete**
([discrete mathematics](discrete-mathematics.md), [graph theory](graph-theory.md)).
[Information theory](information-theory.md) sits on top of probability and powers modern
ML losses. Linear algebra + multivariable calculus are the two that AI leans on hardest —
they are the machinery of [backpropagation](../ai/backpropagation-and-gradient-descent.md).

## Concepts

- [Mathematical Proof and Logic](mathematical-proof-and-logic.md) — propositional & predicate logic, quantifiers, and proof techniques (direct, contrapositive, contradiction, induction)
- [Set Theory](set-theory.md) — sets, relations, functions, cardinality/countability; the common language everything encodes into
- [Linear Algebra](linear-algebra.md) — vectors, matrices, linear maps, eigenvalues, SVD; the language of ML and data
- [Calculus](calculus.md) — limits, derivatives, integrals, the Fundamental Theorem, Taylor series (single-variable)
- [Multivariable Calculus](multivariable-calculus.md) — gradients, Jacobians, Hessians, the multivariable chain rule behind gradient descent
- [Differential Equations](differential-equations.md) — ODEs, PDEs, analytic vs numerical solutions, the dynamical-systems view
- [Discrete Mathematics](discrete-mathematics.md) — combinatorics, recurrences, Boolean algebra; the math of computer science
- [Real Analysis](real-analysis.md) — the rigorous foundations of calculus: epsilon-delta limits, continuity, convergence, completeness
- [Abstract Algebra](abstract-algebra.md) — groups, rings, fields; structure and symmetry under cryptography and coding theory
- [Number Theory](number-theory.md) — divisibility, primes, modular arithmetic; the math behind public-key cryptography
- [Information Theory](information-theory.md) — entropy, cross-entropy, KL divergence, mutual information; the currency of ML losses
- [Graph Theory](graph-theory.md) — vertices, edges, trees, connectivity, coloring; ubiquitous in CS, AI search, and networks
- [Topology](topology.md) — open sets, generalized continuity, compactness; the manifold view behind ML representations

## Canonical works

- [Introduction to Linear Algebra](strang-linear-algebra.md) — Gilbert Strang (MIT 18.06)
- [Linear Algebra Done Right](axler-linear-algebra-done-right.md) — Sheldon Axler; determinant-free, operator-centric
- [Calculus](spivak-calculus.md) — Michael Spivak; rigorous, proof-first
- [Principles of Mathematical Analysis](rudin-principles-of-mathematical-analysis.md) — Walter Rudin ("baby Rudin")
- [Elements of Information Theory](cover-thomas-information-theory.md) — Cover & Thomas
- [Discrete Mathematics and Its Applications](rosen-discrete-mathematics.md) — Kenneth Rosen
- [Introduction to Graph Theory](west-introduction-to-graph-theory.md) — Douglas West; the standard graph-theory text
- [Graph Theory](diestel-graph-theory.md) — Reinhard Diestel; the rigorous graduate reference (free)
- [Abstract Algebra](dummit-foote-abstract-algebra.md) — Dummit & Foote; the comprehensive standard
- [Algebra](artin-algebra.md) — Michael Artin; linear-algebra-forward algebra
- [Naive Set Theory](naive-set-theory.md) — Paul Halmos; the shortest serious set-theory introduction

## Related fields

[Statistics](../statistics/index.md) (probability, inference), [linear optimization](../linear-optimization/index.md)
(pending), [computer science](../computer-science/index.md) (algorithms, complexity),
[artificial intelligence](../ai/index.md), and [systems thinking](../systems-thinking/index.md)
(cybernetics, formal methods).
