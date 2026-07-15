---
type: Reference
title: Linux Kernel Development (Robert Love)
tags: [operating-systems, linux, kernel, systems-programming, scheduling, memory]
timestamp: 2026-07-14
source: https://rlove.org/
---

# Linux Kernel Development (Robert Love)

Robert Love's *Linux Kernel Development* (3rd edition) is the practitioner's guide to how
the Linux kernel actually works. Unlike the general-purpose survey textbooks, it is not a
principles-first course — it is a tour of one specific, monolithic, production kernel by a
core kernel developer, aimed at people who want to *read and write* kernel code rather
than only reason about operating systems in the abstract. Love describes it as "a guide
to understanding the Linux kernel," and it is widely treated as the definitive
approachable introduction to the 2.6-era kernel.

## Scope

The book walks the major kernel subsystems roughly in the order a contributor would need
to understand them:

- **Process management and the scheduler** — how Linux represents a task, how `fork`/`exec`
  and threads (which Linux treats as processes sharing resources) work, and the design of
  the **Completely Fair Scheduler (CFS)** and the preemptive kernel. Anchors
  [processes-and-threads.md](processes-and-threads.md) and [cpu-scheduling.md](cpu-scheduling.md).
- **The system-call interface** — how user space crosses into the kernel, the mechanics
  of the trap, and how a syscall is added. This is the concrete counterpart to
  [the-kernel-and-system-calls.md](the-kernel-and-system-calls.md).
- **Interrupts and bottom halves** — interrupt handlers, softirqs, tasklets, and work
  queues: how the kernel responds to hardware without blocking the whole system.
- **Kernel synchronization** — why concurrency inside the kernel is uniquely hard, and
  the full locking toolkit (atomic operations, spinlocks, semaphores, mutexes,
  read-copy-update). This is the kernel-side of
  [concurrency-and-synchronization.md](concurrency-and-synchronization.md).
- **Memory management** — physical memory, the page cache, `kmalloc`/`vmalloc`, the slab
  allocator, and virtual address spaces. Anchors
  [memory-management-and-virtual-memory.md](memory-management-and-virtual-memory.md).
- **The Virtual File System (VFS) and the block I/O layer** — the common abstraction over
  concrete filesystems, plus I/O schedulers. Anchors [file-systems.md](file-systems.md).
- Time and timers, portability concerns, kernel data structures, and **debugging**
  techniques round out the practical toolkit.

## Approach

The book's value is that it explains the kernel with both a theoretical and a practical
eye: it states *why* a design exists and then shows the actual data structures and code
paths that implement it. That makes it the concrete anchor for the more abstract Linux
material in [../linux/the-linux-kernel.md](../linux/the-linux-kernel.md), and a bridge
from textbook operating-systems theory to a real monolithic kernel. Because it targets a
specific kernel version, it pairs best with the current source tree — but the mental
model it builds (process, scheduler, syscall, interrupt, lock, page, VFS) is durable.

For the discipline-level framing see
[../computer-science/operating-systems.md](../computer-science/operating-systems.md); for
a free, hands-on OS course that motivates the same mechanisms from first principles, see
[OSTEP](../computer-science/ostep-operating-systems.md).

## References

- [Robert Love — author site (Linux Kernel Development)](https://rlove.org/)
- Companion free text on operating-systems mechanisms: [Operating Systems: Three Easy Pieces (OSTEP)](../computer-science/ostep-operating-systems.md)
