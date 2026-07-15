---
type: Reference
title: 97 Things Every Programmer Should Know
tags: [software-craft, best-practices, career, code-quality, essays]
timestamp: 2026-07-14
source: https://www.oreilly.com/library/view/97-things-every/9780596809515/
---

# 97 Things Every Programmer Should Know

A crowd-sourced collection edited by **Kevlin Henney** (O'Reilly, 2010). Rather than one
author's argument, it gathers **97 short, roughly two-page essays** from a wide range of
working programmers and industry figures — each contributor distilling a single piece of
hard-won advice. The essays are independent and can be read in any order; the value is in
the accumulation of many perspectives converging on a small set of durable ideas.

Because it is a wisdom anthology, the point is not any one essay but the **recurring
themes** that surface again and again across different authors. Those themes are the note
below.

## The recurring themes

- **Care about your craft.** Professionalism means taking responsibility for the code you
  produce, not just making the feature "work." Pride in workmanship shows up in the small
  decisions. This is the same ethic at the center of
  [The Pragmatic Programmer](the-pragmatic-programmer.md).
- **Prefer simplicity.** The simplest thing that could possibly work beats the clever
  thing. Complexity is a cost you pay forever; fight it deliberately. See
  [Code Simplicity](code-simplicity.md).
- **Code is read far more than it is written.** Optimize for the next person (often future
  you) reading it. Readability, small functions, and clear intent outrank terseness — the
  core argument of [Clean Code](clean-code.md).
- **Name things well.** Good names are the cheapest, highest-leverage documentation there
  is. Bad names quietly compound into confusion.
- **Communicate.** Programming is a social activity — with teammates, with reviewers, and
  with the code's future readers. Comments should explain *why*, not restate *what*.
- **Automate and test relentlessly.** Manual, repeated work is a bug waiting to happen.
  Build the tests, the scripts, and the pipelines so the machine catches regressions
  instead of you.
- **Beware premature optimization.** Measure before you tune. Micro-optimizing on a hunch
  usually trades clarity for speed you didn't need and can't prove you gained.
- **Technical debt is real.** Shortcuts accrue interest. Track them, make the tradeoff
  consciously, and pay debt down before it dictates your schedule.
- **Own your professional development.** No employer will grow your skills for you. Keep
  learning, read code, practice deliberately — the mindset behind
  [Learning the Craft](../ai-org/learning-the-craft.md).

## A few of the most-cited essays

These recur most often when the book is referenced, and they illustrate the themes above:

- *"The Boy Scout Rule"* — leave the code a little cleaner than you found it.
- *"Beware the Share"* — premature reuse couples code that only accidentally looks alike.
- *"Comment Only What the Code Cannot Say"* — comments carry intent, not narration.
- *"Know Your IDE"* — mastering your tools is part of the craft.
- *"The Golden Rule of API Design"* — write tests against your own API to feel its edges.
- *"Prefer Domain-Specific Types to Primitive Types"* — let the type system enforce meaning.

These titles stand in for the whole: the book is a chorus of practitioners agreeing, from
many angles, on the same handful of disciplines.

## References

- [97 Things Every Programmer Should Know — O'Reilly](https://www.oreilly.com/library/view/97-things-every/9780596809515/)
