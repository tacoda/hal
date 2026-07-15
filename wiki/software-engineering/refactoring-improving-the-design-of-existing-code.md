---
type: Reference
title: "Refactoring: Improving the Design of Existing Code"
tags: [refactoring, code-smells, design, testing, maintainability, craft]
timestamp: 2026-07-14
source: https://martinfowler.com/books/refactoring.html
---

# Refactoring: Improving the Design of Existing Code

Martin Fowler's foundational book on refactoring. This is the **1st edition**
(Addison-Wesley, 1999), whose examples are written in **Java**. (The 2nd edition,
published 2018, rewrote the examples in JavaScript.) The book named and cataloged a
practice that working programmers already did informally, and gave it a disciplined,
repeatable form.

## What refactoring is

Refactoring is **changing the internal structure of code without changing its external
behavior**. You improve how the code is organized — its readability, its design — while
keeping what it does exactly the same. Behavior preservation is the defining constraint:
if the observable output changes, it isn't a refactoring, it's a rewrite or a bug.

The discipline is a series of **small, behavior-preserving transformations**, each one
tiny enough to be obviously correct, chained together to produce a large structural
change. Because every step preserves behavior, the system stays working the whole way
through — you never have a long stretch where the code is broken.

## Why refactor

- **Improve the design.** Code decays as it's changed for short-term goals; refactoring
  counteracts that decay and keeps the design coherent.
- **Make it easier to understand.** Restructuring code to say clearly what it does turns
  vague understanding into something explicit in the code itself.
- **Find bugs.** Clarifying structure surfaces the assumptions and edge cases that hid in
  the mess.
- **Program faster.** A clean design lets you add features quickly; a good internal
  structure is what makes fast, safe change possible. This is the economic argument —
  refactoring is not cosmetic, it pays for itself in future velocity.

## The two hats

At any moment you are wearing one of two hats: **adding function** or **refactoring**.
When adding function you don't change existing code, you only add new capability and
tests. When refactoring you don't add function, you only restructure. Swap hats
frequently, but never wear both at once — knowing which activity you're doing keeps each
one honest and keeps behavior changes separate from structure changes.

## When to refactor

Refactoring is opportunistic, not a scheduled phase:

- **The Rule of Three.** The first time you do something, just do it. The second time you
  do something similar, wince but duplicate. The third time, refactor.
- **Before adding a feature** ("Preparatory refactoring"). If the current design makes a
  new feature hard, first refactor to make the change easy, then make the easy change.
- **To understand code** ("Comprehension refactoring"). As you understand a piece of
  code, fold that understanding back into it so the next reader doesn't have to rediscover
  it.
- **To fix a bug.** Restructuring to understand the code often reveals the defect.

## Code smells

A "smell" is a surface symptom that usually points to a deeper design problem — a heuristic
for *where* to refactor, not a hard rule. The catalog includes:

- **Duplicated code** — the same structure in more than one place; the number-one target.
- **Long method** — methods that do too much; short, well-named methods read better.
- **Large class** — a class trying to do too much, usually with too many instance fields.
- **Long parameter list** — hard to understand; often a hint that objects are missing.
- **Feature envy** — a method more interested in another class's data than its own; it
  probably belongs on that other class.
- **Data clumps** — the same group of fields/parameters travelling together, wanting to
  become their own object.
- **Shotgun surgery** — one change forces many small edits scattered across classes.
- **Divergent change** — one class changed for many unrelated reasons.
- **Primitive obsession**, **switch statements** (often better as polymorphism),
  **comments** used to excuse unclear code, and others.

## The mechanics

Every refactoring in the catalog is written as a **motivation** plus a set of numbered
**mechanics** — the concrete, small steps to perform it safely. The safety net is
**tests**: you refactor only when you have a solid, self-checking test suite, so that
after each small step you can run the tests and confirm behavior is unchanged. Small steps
plus a green test suite mean a mistake is caught immediately and is trivial to undo. This
is why refactoring and testing are inseparable — see [TDD as five practices](tdd-five-practices.md).
When the code has no tests to refactor safely, first get it under test — see
[Working Effectively with Legacy Code](working-effectively-with-legacy-code.md).

## Key refactorings

- **Extract Function/Method** — pull a fragment into its own well-named function; the
  workhorse of the catalog, driven by the Long Method smell.
- **Rename (Method/Variable)** — names are the primary way code communicates; renaming to
  reveal intent is a first-class refactoring.
- **Move Method / Move Field** — relocate a member to the class it actually belongs with;
  the cure for Feature Envy.
- **Replace Conditional with Polymorphism** — turn a branching switch/if-ladder on type
  into subclasses that each handle their own case, so behavior lives with its type.
- **Replace Temp with Query, Inline, Extract Class** — and dozens more, each a named,
  reversible move.

## Where it fits

Refactoring is part of the everyday practice of software craftsmanship — the ongoing,
deliberate improvement of code as a discipline rather than a one-off cleanup. See
[learning the craft](../ai-org/learning-the-craft.md) for the broader stance this fits into.

## References

- [Refactoring: Improving the Design of Existing Code](https://martinfowler.com/books/refactoring.html) — Martin Fowler (1st ed., Addison-Wesley, 1999)
