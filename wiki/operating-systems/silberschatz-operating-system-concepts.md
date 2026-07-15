---
type: Reference
title: Operating System Concepts (Silberschatz, Galvin & Gagne)
tags: [operating-systems, textbook, scheduling, concurrency, synchronization, deadlock]
timestamp: 2026-07-14
source: https://www.os-book.com/
---

# Operating System Concepts (Silberschatz, Galvin & Gagne)

Abraham Silberschatz, Peter Baer Galvin, and Greg Gagne's *Operating System Concepts* —
universally nicknamed the **"dinosaur book"** for the prehistoric creatures on its
covers — is the other standard undergraduate OS textbook alongside Tanenbaum's. Now
past its tenth edition, it has been a fixture of computer-science curricula for decades
and is often the first rigorous treatment a student sees.

## Scope and approach

Where Tanenbaum leans on real-system case studies, the dinosaur book is more of a
**structured, mechanism-by-mechanism course**. It builds the subject up in layers, and
its coverage is deliberately exhaustive so it can serve as both a semester text and a
reference:

- **Processes and threads** — the process abstraction, process state and control blocks,
  context switching, threading models, and interprocess communication. See
  [processes-and-threads.md](processes-and-threads.md).
- **CPU scheduling** — a thorough treatment of scheduling criteria and algorithms
  (FCFS, SJF, priority, round-robin, multilevel queues) plus multiprocessor and
  real-time scheduling. This is one of the book's signature chapters. See
  [cpu-scheduling.md](cpu-scheduling.md).
- **Concurrency and synchronization** — the classic core of the book: the critical-section
  problem, mutex locks, semaphores, monitors, and canonical problems (bounded-buffer,
  readers-writers, dining philosophers). See
  [concurrency-and-synchronization.md](concurrency-and-synchronization.md).
- **Deadlocks** — the four necessary conditions, and the full spectrum of prevention,
  avoidance (banker's algorithm), detection, and recovery.
- **Memory and storage** — main-memory management, paging, and demand-paged virtual
  memory, then mass storage, I/O, and file systems.

## Why it endures

The book's strength is **pedagogical clarity**: precise definitions, careful pseudocode,
and a consistent progression from problem statement to algorithm to trade-off analysis.
Later editions modernized the examples (Linux, Windows, and mobile systems) and added
material on [virtualization and containers](virtualization-and-containers.md),
distributed systems, and security, but the spine — the concurrency and scheduling
chapters — is what makes it the reference many engineers keep returning to.

It sits naturally beside the discipline overview in
[../computer-science/operating-systems.md](../computer-science/operating-systems.md), and
its abstractions are grounded in the same
[kernel and system-call](the-kernel-and-system-calls.md) machinery that a book like
[../linux/the-linux-kernel.md](../linux/the-linux-kernel.md) shows in concrete code. For
a free, hands-on companion that drills the same mechanisms, see
[OSTEP](../computer-science/ostep-operating-systems.md).

## References

- [Operating System Concepts — official companion site (os-book.com)](https://www.os-book.com/)
- Companion free text on the same topics: [Operating Systems: Three Easy Pieces (OSTEP)](../computer-science/ostep-operating-systems.md)
