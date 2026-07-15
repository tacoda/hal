---
type: Reference
title: Linear Programming — Foundations and Extensions (Vanderbei)
tags: [linear-programming, simplex, interior-point, duality, optimization]
timestamp: 2026-07-14
source: https://vanderbei.princeton.edu/LPbook/
---

# Linear Programming — Foundations and Extensions (Vanderbei)

Robert Vanderbei's *Linear Programming: Foundations and Extensions* (Springer, now in
its 5th edition) is a widely used LP text that is distinctive for giving the **simplex
method and interior-point methods equal, first-class treatment** in a single book. Many
LP texts lead with the simplex method and treat interior-point methods as an
afterthought; Vanderbei, an interior-point researcher, develops both lines of algorithm
in depth and shows how they relate.

## Scope and approach

- **Foundations (the simplex method).** It begins with the standard LP form and builds
  the **simplex method** carefully: the dictionary/tableau mechanics, pivoting,
  handling degeneracy and cycling, and the two-phase and revised-simplex variants.
  See [linear-programming.md](linear-programming.md) and
  [simplex-method.md](simplex-method.md).
- **Duality and sensitivity.** LP **duality**, complementary slackness, and
  post-optimality/sensitivity analysis are developed as core theory, connecting the
  primal and dual simplex methods. See [duality.md](duality.md).
- **Interior-point methods.** The second half is the book's signature contribution:
  the path-following and primal-dual **interior-point** algorithms, their derivation
  from the KKT conditions and the central path, and their strong performance on large
  sparse problems.
- **Extensions.** Later chapters push past pure LP into network flows, integer
  programming, quadratic programming, and convex problems — showing LP as the base case
  of a wider optimization landscape (see
  [optimization-problems.md](optimization-problems.md),
  [network-flows.md](network-flows.md),
  [integer-and-combinatorial-optimization.md](integer-and-combinatorial-optimization.md),
  [convex-optimization.md](convex-optimization.md)).

## Why it matters

For someone who wants to understand *both* of the algorithm families that actually
solve linear programs in practice — the combinatorial simplex walk and the continuous
interior-point trajectory — and how duality and the KKT conditions tie them together,
this is the text that treats them as peers.

## References

- [Linear Programming: Foundations and Extensions — Vanderbei (Princeton)](https://vanderbei.princeton.edu/LPbook/)
