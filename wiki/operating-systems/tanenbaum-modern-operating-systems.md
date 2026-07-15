---
type: Reference
title: Modern Operating Systems (Tanenbaum & Bos)
tags: [operating-systems, textbook, processes, memory, file-systems, security]
timestamp: 2026-07-14
source: https://www.pearson.com/en-us/subject-catalog/p/modern-operating-systems/P200000003295
---

# Modern Operating Systems (Tanenbaum & Bos)

Andrew S. Tanenbaum and Herbert Bos's *Modern Operating Systems* (now in its 5th
edition, 2022) is one of the two standard comprehensive textbooks used to teach the
subject at the undergraduate level. Tanenbaum — the designer of MINIX, whose
public discussion of a small teaching kernel famously helped inspire Linus Torvalds —
writes with an emphasis on **principles first, then concrete systems**: each core
mechanism is explained in the abstract, then illustrated with how real operating
systems actually implement it.

## Scope

The book is a broad survey of everything an operating system does. Its major arcs map
almost one-for-one onto the core OS concepts in this field:

- **Processes and threads** — what a process is, how it is represented, thread models,
  and the mechanics of interprocess communication and coordination. See
  [processes-and-threads.md](processes-and-threads.md).
- **Scheduling** — the policies that decide which runnable thread gets the CPU, from
  simple round-robin to multilevel feedback queues. See [cpu-scheduling.md](cpu-scheduling.md).
- **Memory management** — allocation, paging, segmentation, and the demand-paged
  **virtual memory** that gives each process its own large, protected address space.
  See [memory-management-and-virtual-memory.md](memory-management-and-virtual-memory.md).
- **File systems** — files and directories as abstractions, on-disk layout, allocation
  strategies, and consistency/recovery. See [file-systems.md](file-systems.md).
- **Input/output** — device drivers, interrupts, and the layering that hides hardware
  variety behind uniform interfaces.
- **Deadlocks** — detection, avoidance, and prevention of circular resource waits.
- **Security** — protection models, access control, authentication, and a survey of
  attacks and defenses that has grown with each edition.

## Approach

What distinguishes the book is its **case-study method**. After the principles, it
devotes substantial chapters to full real systems — historically UNIX/Linux, Windows,
and (in Tanenbaum's own tradition) MINIX and mobile/embedded systems like Android — so
the reader sees how the same abstractions are realized under different design pressures.
Tanenbaum is a proponent of **microkernel** design (minimal privileged core, most
services in user space), and the book gives that debate — microkernel versus the
monolithic design of [the kernel and system calls](the-kernel-and-system-calls.md) as
seen in [../linux/the-linux-kernel.md](../linux/the-linux-kernel.md) — a fair and
opinionated treatment. It also covers [virtualization and containers](virtualization-and-containers.md)
as first-class OS topics, reflecting how hypervisors have become another layer of the
resource-management story.

As a college text it pairs well with the discipline-level overview in
[../computer-science/operating-systems.md](../computer-science/operating-systems.md) and
with the hands-on, free companion [OSTEP](../computer-science/ostep-operating-systems.md),
which drills the same mechanisms through worked problems and code.

## References

- [Modern Operating Systems — Pearson](https://www.pearson.com/en-us/subject-catalog/p/modern-operating-systems/P200000003295)
- Companion free text on the same topics: [Operating Systems: Three Easy Pieces (OSTEP)](../computer-science/ostep-operating-systems.md)
