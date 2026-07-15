---
type: Concept
title: Agile and the Agile Manifesto
tags: [agile, manifesto, values, principles, iterative, software-process]
timestamp: 2026-07-14
---

# Agile and the Agile Manifesto

**Agile** is a family of software approaches that favor short feedback loops, working
software, and adaptation over big up-front plans. The name and the movement crystallized
in February 2001, when seventeen practitioners — many already advocating lightweight
methods like [Extreme Programming](extreme-programming.md), Scrum, Crystal, and DSDM — met
at Snowbird, Utah and wrote the **Manifesto for Agile Software Development**. The Manifesto
was less an invention than a synthesis: a shared banner for methods that had independently
concluded that heavyweight, plan-driven ("waterfall") process was failing on projects where
requirements and technology changed faster than a plan could be written.

## The four values

The Manifesto is deliberately short. Its core is four value statements, each of the form
*we value the left over the right — while still valuing the right*:

| We value… | …over |
| --- | --- |
| Individuals and interactions | processes and tools |
| Working software | comprehensive documentation |
| Customer collaboration | contract negotiation |
| Responding to change | following a plan |

The trailing clause matters and is the most-abused part: the right-hand items still have
value. Agile does not mean "no documentation" or "no plan." It means that when the two
sides conflict, the left wins — because that is where a project's real information lives.

## The twelve principles

Behind the values sit twelve principles that make them operational. Paraphrased and
grouped:

- **Deliver value early and often** — satisfy the customer through early and continuous
  delivery of working software; deliver in weeks, not months; working software is the
  primary measure of progress.
- **Welcome change** — even late in development; agile processes harness change for the
  customer's advantage.
- **Collaborate closely** — business people and developers work together daily; build
  around motivated individuals and trust them; face-to-face conversation is the most
  effective communication.
- **Sustain the pace** — maintain a constant, indefinitely sustainable pace (see
  [peopleware](peopleware.md) on burnout and overtime).
- **Pursue technical excellence** — continuous attention to good design and simplicity
  ("maximize the work *not* done").
- **Reflect and adjust** — self-organizing teams tune their behavior at regular intervals
  (the seed of [continuous-improvement-and-retrospectives](continuous-improvement-and-retrospectives.md)).

## What "agile" actually means

Read charitably, agile is a bet on **empirical process control**: you cannot fully specify
software in advance, so build a little, show it, learn, and steer. That bet is why the
concrete methods share a shape — short iterations, a working increment each cycle, a
tight customer loop, and a retrospective. [Scrum](scrum.md) packages this into a
role/event/artifact framework; [Kanban](kanban-and-flow.md) applies it to continuous flow;
[Extreme Programming](extreme-programming.md) supplies the engineering practices that keep
the increment actually shippable. Agile also inherits directly from lean manufacturing —
see [lean-software-development](lean-software-development.md) and
[lean-thinking](lean-thinking.md) — and its delivery ambitions are industrialized by
[../devops-sre/continuous-delivery.md](../devops-sre/continuous-delivery.md).

## Roots

Agile did not appear from nothing. Iterative and incremental development predates the term
by decades (military and NASA projects used it in the 1960s–70s). Its immediate parents
are the lightweight methods of the 1990s — Scrum (Sutherland/Schwaber), XP (Beck), Crystal
(Cockburn), FDD, DSDM — reacting against the document-heavy, stage-gated processes that
dominated enterprise software. The intellectual DNA also runs through the Toyota Production
System and [the-goal](the-goal.md)'s theory of constraints: reduce batch size, expose
problems fast, improve continuously ([toyota-kata](toyota-kata.md)).

## How it has been diluted

The common critique is not that agile is wrong but that it is widely misapplied — a
phenomenon its own signatories lament as **"Agile" (capital-A, trademarked-feeling)** versus
**agility**:

- **Process theater** — adopting ceremonies (standups, sprints, story points) while
  ignoring the values. This is the "individuals and interactions over processes and tools"
  value inverted: the process becomes the point.
- **Command-and-control in agile clothing** — velocity used as a management target,
  estimates weaponized as commitments, "self-organizing" teams told exactly what to do.
- **Certification and framework industry** — heavyweight scaling frameworks and two-day
  certifications that reintroduce the bureaucracy agile was meant to shed (see
  [agile-at-scale-and-critiques](agile-at-scale-and-critiques.md)).
- **Skipping the engineering** — teams adopt Scrum's project mechanics but not XP's
  technical practices, so the increment is never actually shippable and change stays
  expensive.

The healthiest reading: treat the Manifesto as a compass, not a checklist. If a practice
stops serving working software and rapid feedback, it is no longer agile, whatever it is
called.

## References

- [Manifesto for Agile Software Development](agile-manifesto.md) — the anchoring source
  (values, principles, signatories).
- [Extreme Programming Explained](extreme-programming-explained.md) — Beck's lightweight
  method that fed the Manifesto.
- [The Scrum Guide](scrum-guide.md) — the most widely adopted agile framework.
- [Lean Thinking](lean-thinking.md) and [The Goal](the-goal.md) — the manufacturing roots.
