---
type: Reference
title: The Linux Programming Interface
tags: [linux, system-calls, system-programming, posix, kernel-api]
timestamp: 2026-07-14
source: https://man7.org/tlpi/
---

# The Linux Programming Interface

Michael Kerrisk's *The Linux Programming Interface* (TLPI, No Starch Press, 2010) is
the definitive single-volume reference on the **Linux and UNIX system-call API** — the
boundary at which user-space programs ask the [kernel](the-linux-kernel.md) to do
things on their behalf. At roughly 1,550 pages with nearly 200 worked example
programs, it is comprehensive by design. Kerrisk maintained the Linux *man-pages*
project (documenting the kernel and glibc APIs) for most of two decades, and the book
carries that authority: it explains not just *what* each system call does but *why* the
interface is shaped the way it is, and how it behaves at the edges.

## Scope and central ideas

TLPI is organized around the services the kernel exposes to programs:

- **File I/O — the universal I/O model.** Open, read, write, close on file
  descriptors, and the way that same descriptor abstraction unifies regular files,
  pipes, devices, terminals, and sockets. This is the concrete API behind the
  Unix design maxim [everything is a file](everything-is-a-file.md).
- **[Processes and signals](processes-and-signals.md).** Process creation with `fork`,
  program loading with the `exec` family, termination and `wait`, process groups and
  sessions; and the full treatment of signals — delivery, handlers, masks, and the
  subtleties of async-signal safety.
- **Memory.** The process address space, virtual memory, memory allocation, and memory
  mapping (`mmap`).
- **Threads.** POSIX threads, synchronization primitives, and thread-vs-process
  tradeoffs.
- **Interprocess communication.** Pipes and FIFOs (the mechanism under
  [the shell and pipes](the-shell-and-pipes.md)), System V and POSIX IPC — message
  queues, semaphores, shared memory.
- **Sockets and networking.** The Berkeley sockets API for local and network
  communication.
- **Time, terminals, daemons, file systems, and more** — timers, terminal I/O, writing
  well-behaved background services, and the file-system-level calls.

The through-line is that Linux presents a **POSIX-conformant but Linux-specific**
interface, and mastering system programming means understanding both the portable
standard and the Linux extensions. It is the practitioner's companion to the theory in
[operating systems](../computer-science/operating-systems.md).

## Related notes

- [processes-and-signals.md](processes-and-signals.md)
- [the-linux-kernel.md](the-linux-kernel.md)
- [everything-is-a-file.md](everything-is-a-file.md)
- [unix-philosophy.md](unix-philosophy.md)
- [the-shell-and-pipes.md](the-shell-and-pipes.md)
- [the-filesystem-and-fhs.md](the-filesystem-and-fhs.md)
- [init-and-services.md](init-and-services.md)
- [operating systems](../computer-science/operating-systems.md)

## References

- [The Linux Programming Interface — man7.org/tlpi](https://man7.org/tlpi/)
