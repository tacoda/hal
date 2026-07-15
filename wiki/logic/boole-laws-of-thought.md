---
type: Reference
title: An Investigation of the Laws of Thought (Boole)
tags: [logic, boolean-algebra, symbolic-logic, algebra-of-logic, history-of-logic, probability]
timestamp: 2026-07-14
source: https://www.gutenberg.org/ebooks/15114
---

# An Investigation of the Laws of Thought (Boole)

George Boole's *An Investigation of the Laws of Thought, on Which Are Founded the
Mathematical Theories of Logic and Probabilities* (1854) is the founding work of
algebraic, symbolic logic. Its thesis is radical for its time: the laws of valid
reasoning are not a branch of philosophy or rhetoric but a branch of **mathematics**, and
can be captured by an *algebra*. Boole set out to show that reasoning about classes and
propositions obeys formal laws every bit as exact as the laws of ordinary algebra — and
then to derive those laws and calculate with them.

## Scope and approach

Boole represents classes (or, later, propositions) by symbols like `x`, `y`, `z` and lets
algebraic operations stand for logical ones.

- **Selection as multiplication.** `xy` denotes the things that are both `x` and `y`
  (class intersection / logical "and"). Because selecting the `x`s and then the `x`s again
  changes nothing, his system obeys the **index law** `x² = x` (`xx = x`) — the algebraic
  signature that distinguishes the logic of classes from ordinary numerical algebra.

- **A two-valued universe.** The idempotent law `x² = x` forces every symbol toward the
  values **0 and 1**: `1` is the universe (the "Universe of discourse," a term Boole
  popularized) and `0` is the empty class / nothing. This restriction of quantities to 0
  and 1 is exactly what later became a **Boolean** variable, and Boole's `x² = x` is the
  ancestor of the modern axioms of [boolean-algebra.md](boolean-algebra.md).

- **Addition, subtraction, and the derivation of inference.** Boole uses `+` for
  aggregation of disjoint classes and `1 − x` for the complement of `x` ("not-`x`"). From
  these he re-derives the classical logical relationships — the conversions and syllogisms
  of Aristotelian term logic — as algebraic manipulations, and treats propositions as a
  special case (a proposition is "true" = 1 or "false" = 0), which is the seed of modern
  truth-functional [propositional logic](propositional-logic.md).

- **Logic and probability unified.** The second half of the book extends the same algebra
  to the calculus of probabilities, treating a probability as a generalized truth value
  between 0 and 1 — an early attempt to place logic and probability on one formal footing.

## Why it matters

Boole demonstrated that logic could be *computed*, not merely argued. His algebra of 0 and
1, later refined by Jevons, Peirce, and Schröder into the modern axiomatic
[boolean-algebra.md](boolean-algebra.md), became the mathematical substrate of digital
circuit design and of truth-functional logic. The line from `x² = x` to the logic gate is
short and direct. For HAL this note anchors the historical and algebraic root of the logic
folder; it connects to the abstract-algebra treatment in
[../math/mathematical-proof-and-logic.md](../math/mathematical-proof-and-logic.md) and, via
the two-valued switching algebra, to the foundations of
[../computer-science/index.md](../computer-science/index.md).

## References

- [An Investigation of the Laws of Thought (Boole) — Project Gutenberg](https://www.gutenberg.org/ebooks/15114)
