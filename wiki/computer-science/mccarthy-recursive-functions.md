---
type: Reference
title: Recursive Functions of Symbolic Expressions and Their Computation by Machine, Part I
tags: [lisp, lambda-calculus, metacircular-evaluator, eval, s-expressions, functional-programming, symbolic-ai, foundations, mccarthy]
timestamp: 2026-07-14
source: http://www-formal.stanford.edu/jmc/recursive/recursive.html
---

# Recursive Functions of Symbolic Expressions and Their Computation by Machine, Part I

John McCarthy's April 1960 paper, written at MIT, is the founding document of
[Lisp](lisp.md). Its ambition was modest on its face — a practical scheme for
computing with *symbolic* rather than purely numeric data — but in carrying it
out McCarthy introduced a cluster of ideas that reshaped both programming-language
theory and artificial intelligence.

## What the paper introduces

- **Symbolic expressions (s-expressions).** McCarthy defines a class of data
  built from atomic symbols and the pairing operation, so that all data is a tree
  of pairs terminating in atoms. The elementary functions `cons`, `car`, and
  `cdr` construct and take apart these pairs; `atom` and `eq` test them. This is
  the minimal kernel from which every Lisp data structure — and every Lisp
  program — is assembled.
- **Functions over s-expressions, and conditionals.** The paper develops a
  notation for defining functions by cases using conditional expressions, and for
  defining functions **recursively** — recursion, not iteration, is taken as the
  primitive way to express repetition. This is where the language's functional
  character comes from.
- **`eval` — the universal function.** McCarthy's central technical result is a
  function `eval` that, given a symbolic expression *representing* a Lisp
  function together with a representation of its arguments, computes the value
  that the function would produce. Because Lisp programs are themselves
  s-expressions, `eval` is an interpreter for Lisp written in the very notation it
  interprets — the first **metacircular evaluator**. This concretely demonstrates
  the universal-machine idea: one function that can carry out any computation
  expressible in the system. The mutually recursive `eval`/`apply` structure
  developed in depth in [SICP](sicp.md) descends directly from this construction.

## Lineage from the lambda calculus

McCarthy borrows Church's `lambda` notation for anonymous functions and binding,
tying Lisp to the **lambda calculus** — the same formalism treated in
[mathematical proof and logic](../math/mathematical-proof-and-logic.md) as a model
of effective computation. The paper is, in effect, a bridge: it takes a
mathematical logic of functions and turns it into something a machine can run,
keeping the theoretical clarity of function abstraction and application as the
computational core. (The paper also notes an alternative formalism and the
relationship of recursion to flowcharts.)

## Influence

The ideas seeded here propagated widely:

- On **functional programming**: first-class and higher-order functions,
  recursion as the primary control structure, and evaluation as function
  application all trace to this paper.
- On **language implementation**: the metacircular evaluator became the canonical
  way to teach and reason about interpreters, and `eval` exposed interactively
  became the REPL.
- On **artificial intelligence**: treating symbolic expressions as first-class,
  manipulable data made Lisp the language of
  [symbolic AI / GOFAI](../ai/knowledge-representation-and-reasoning.md) for
  decades, since reasoning programs could build and transform symbolic structures
  — including other programs.

The companion "Part I" in the title anticipated a Part II that was never
published; Part I alone proved foundational.

## References

- John McCarthy, "Recursive Functions of Symbolic Expressions and Their
  Computation by Machine, Part I," *Communications of the ACM* (April 1960) —
  [www-formal.stanford.edu/jmc/recursive/recursive.html](http://www-formal.stanford.edu/jmc/recursive/recursive.html)
