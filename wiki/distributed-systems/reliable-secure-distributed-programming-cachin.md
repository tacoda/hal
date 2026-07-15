---
type: Reference
title: "Introduction to Reliable and Secure Distributed Programming (Cachin, Guerraoui & Rodrigues)"
tags: [distributed-systems, distributed-algorithms, broadcast, shared-memory, consensus, byzantine-fault-tolerance]
timestamp: 2026-07-14
source: https://www.distributedprogramming.net/
---

# Introduction to Reliable and Secure Distributed Programming (Cachin, Guerraoui & Rodrigues)

An algorithms-first textbook by Christian Cachin, Rachid Guerraoui, and Luís Rodrigues.
It is the second edition of the 2006 *Introduction to Reliable Distributed Programming*,
extended so that "Secure" now sits in the title: the new material treats processes that
do not merely crash but can behave arbitrarily or maliciously — the domain of Byzantine
fault tolerance. Where a survey text maps the territory, this book supplies the precise
building blocks: for each problem it states the abstraction, gives an algorithm that
implements it under stated assumptions, and proves the algorithm correct.

## Method

The book is deliberately incremental. It begins in the simplest environment and layers
sophistication one assumption at a time: from crash-stop processes toward crash-recovery
and then Byzantine (adversarial) processes; from synchronous timing toward
partially-synchronous and asynchronous models. Every abstraction is specified by the
*properties* it must guarantee (safety and liveness), then realized by an algorithm
built out of lower-level abstractions already established — so consensus is constructed
on top of broadcast and failure detection, not from scratch. This composition-by-layers
is the book's pedagogical spine.

## Scope

Six chapters, in two parts.

- **Part I — the model.** Chapter 1 motivates distributed programming abstractions and
  introduces the end-to-end argument and classes of algorithms. Chapter 2 fixes the
  ground rules: how processes are abstracted, cryptographic primitives, communication
  links, timing assumptions, and the resulting distributed-system models (fail-stop,
  fail-silent, fail-noisy, fail-recovery, fail-arbitrary/Byzantine). These failure and
  timing assumptions are exactly what
  [fault-tolerance-and-failure.md](fault-tolerance-and-failure.md) is about.
- **Reliable broadcast** — best-effort, regular, uniform, stubborn, logged,
  probabilistic, and FIFO/causal broadcast, then their Byzantine counterparts
  (consistent and reliable broadcast). Delivering a message to a group with defined
  guarantees despite failures.
- **Shared memory** — read/write registers as distributed storage objects, built up
  from (1,N) regular to (N,N) atomic registers, including logged and Byzantine
  variants. Models a replicated storage cell.
- **Consensus** — the central abstraction: a set of processes agreeing on one value
  despite faulty peers. Regular, uniform, fail-noisy, logged, randomized, and Byzantine
  consensus. This is the book's clearest link to [consensus.md](consensus.md).
- **Consensus variants** — total-order broadcast, terminating reliable broadcast,
  (non-blocking) atomic commit, group membership, and view-synchronous communication —
  the abstractions real applications actually consume, each reduced to or extended from
  plain consensus.

## Why it anchors the field

This is the reference for *how* the guarantees are met, not just what they are. It
supplies the specification-and-proof discipline behind consensus and its relatives, and
it is one of the standard treatments of Byzantine fault tolerance at textbook level —
the bridge from crash-tolerant algorithms (see the Raft paper,
[raft-consensus-paper.md](raft-consensus-paper.md), which handles crash faults only) to
adversarial settings. Pair it with a survey text like
[distributed-systems-tanenbaum-van-steen.md](distributed-systems-tanenbaum-van-steen.md)
for breadth, and read it against
[distributed-systems-fundamentals.md](distributed-systems-fundamentals.md) for the model
vocabulary it leans on.

## References

- [Introduction to Reliable and Secure Distributed Programming — distributedprogramming.net](https://www.distributedprogramming.net/)
