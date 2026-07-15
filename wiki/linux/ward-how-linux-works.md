---
type: Reference
title: "How Linux Works: What Every Superuser Should Know"
tags: [linux, system-internals, boot, kernel, filesystem, sysadmin]
timestamp: 2026-07-14
source: https://nostarch.com/howlinuxworks3
---

# How Linux Works: What Every Superuser Should Know

Brian Ward's *How Linux Works* (No Starch Press; 3rd edition, 2021) is the accessible,
big-picture tour of how a Linux system actually fits together. Its stance is that Linux
does not hide the important parts from you — it gives you full control — so to master
the system you should understand its internals rather than memorize commands. The book
"peels back the layers," moving from the hardware upward, and is deliberately layered
itself so a reader can go as deep on any topic as the question at hand requires.

## Scope and central ideas

Ward walks the system bottom-to-top, showing how each layer supports the next:

- **How the system boots.** The path from power-on through the boot loader into
  [the Linux kernel](the-linux-kernel.md), and what the kernel does as it comes up.
- **Kernel and user space.** The division between the privileged kernel and the
  programs that run on top of it, and how processes, devices, and system calls
  cross that boundary. Complements the API-level view in
  [The Linux Programming Interface](kerrisk-linux-programming-interface.md).
- **Devices, disks, and file systems.** How the kernel represents devices, how disks
  are partitioned and mounted, and how the directory tree is organized — the concrete
  companion to [the filesystem and FHS](the-filesystem-and-fhs.md), including swap
  space and the logical volume manager.
- **Startup and services.** How the system reaches a usable state after the kernel
  boots — the init system launching and supervising services — mapping onto
  [init and services](init-and-services.md).
- **User space, shells, and scripting.** The command line, shell fundamentals, and
  writing shell scripts to automate work.
- **Networking.** How the network stack is configured and how packets move, at a level
  a superuser can reason about and troubleshoot.
- **Development and resource management** — a look at how programs are built and how
  the system shares CPU, memory, and I/O.

The organizing idea is **operational understanding**: enough of the *why* behind the
system that an administrator can diagnose problems instead of pattern-matching
symptoms. It sits a step above the theory in
[operating systems](../computer-science/operating-systems.md) and a step below a
system-programming reference.

## Related notes

- [the-filesystem-and-fhs.md](the-filesystem-and-fhs.md)
- [the-linux-kernel.md](the-linux-kernel.md)
- [init-and-services.md](init-and-services.md)
- [the-shell-and-pipes.md](the-shell-and-pipes.md)
- [processes-and-signals.md](processes-and-signals.md)
- [unix-philosophy.md](unix-philosophy.md)
- [operating systems](../computer-science/operating-systems.md)

## References

- [How Linux Works, 3rd Edition — No Starch Press](https://nostarch.com/howlinuxworks3)
