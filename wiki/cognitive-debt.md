---
type: Reference
title: Cognitive Debt (Storey)
tags: [cognitive-debt, comprehension-debt, theory-of-the-system, teams, careers]
timestamp: 2026-07-14
source: https://margaretstorey.com/blog/2026/02/09/cognitive-debt/
---

# Cognitive Debt (Storey)

Margaret-Anne Storey's argument that generative and agentic AI shift the field's central
worry from **technical debt** to **cognitive debt**. The distinction:

> **Technical debt lives in the code; cognitive debt lives in developers' minds.**

Technical debt is a property of the code — you spend effort removing it *from the code*.
Cognitive debt is the debt compounded from going fast that lives in the developers'
heads: even if agents produce perfectly clean code, the humans may have **lost the plot**
— they no longer understand what the program is supposed to do, how their intentions were
implemented, or how to change it. She calls it a *bigger* threat than technical debt as
AI adoption rises. This is the same phenomenon named [comprehension debt](comprehension-debt.md)
from the individual-and-organizational angle.

## A program is a theory (Naur)

Storey grounds this in Peter Naur's **"Programming as Theory Building"**: a program is
more than its source code — it is a *theory* living in developers' minds, capturing what
the program does, how intentions were implemented, and how it can change. That theory is
usually **distributed across many minds**, not held by one person.

Her vivid case: a student team in an entrepreneurship course shipped fast for weeks, then
by **week 7–8 hit a wall** — they couldn't make simple changes without breaking
something. They blamed messy code, but the real problem was that **no one could explain
*why* design decisions were made or *how* the parts fit together**. The theory of the
system had evaporated. They'd accrued cognitive debt faster than technical debt, and it
paralyzed them. She ties this to Brooks's *Mythical Man-Month*: adding more agents adds
coordination overhead, invisible decisions, and cognitive load.

## What teams can do

- **Recognize velocity without understanding is not sustainable.** Slow down; use pair
  programming, refactoring, and TDD — practices that pay down *both* debts and rebuild
  shared understanding. (Kent Beck's "make the hard change easy.")
- **Require at least one human to fully understand each AI-generated change before it
  ships.** Document not just *what* changed but *why*. Create checkpoints (reviews,
  retros, knowledge-sharing) that rebuild shared theory.
- **Watch the warning signs:** hesitancy to change code for fear of breakage, growing
  reliance on tribal knowledge held by one or two people, the system becoming a black box.
- **Research it:** how do we *measure* cognitive debt, and which practices best prevent it
  in AI-augmented, distributed, and open-source settings?

Protecting the shared theory of what the software does and how it can change may matter
more for long-term software health than any single speed metric.

## Related

- [Comprehension Debt](comprehension-debt.md) — the same gap, framed as accruing debt.
- [Comprehension Debt (Osmani)](comprehension-debt-osmani.md) — cites Storey's week-seven
  team.

## References
- [How Generative and Agentic AI Shift Concern from Technical Debt to Cognitive Debt — Margaret-Anne Storey](https://margaretstorey.com/blog/2026/02/09/cognitive-debt/)
