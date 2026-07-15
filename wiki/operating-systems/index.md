---
type: Index
title: Operating Systems
tags: [operating-systems, kernel, processes, memory, index]
timestamp: 2026-07-14
---

# Operating Systems

The software layer that manages a computer's hardware and gives programs the illusions they
run on — many processes on one CPU, a huge private memory, files instead of raw blocks. This
is the dedicated deep-dive field; the one-note survey lives at
[computer science → operating systems](../computer-science/operating-systems.md), and the
concrete Linux angle is in [Linux & Unix](../linux/index.md). The OS sits directly above the
[hardware/software boundary](../electrical-engineering/hardware-software-boundary.md) and
below every language runtime and application.

## The shape of the field

The OS virtualizes three things. The **CPU**: [processes and threads](processes-and-threads.md)
time-shared by the [scheduler](cpu-scheduling.md). **Memory**:
[memory management and virtual memory](memory-management-and-virtual-memory.md). And
**devices/persistence**: [file systems](file-systems.md) and
[I/O & device management](io-and-device-management.md). Holding it together are
[concurrency and synchronization](concurrency-and-synchronization.md), the privileged
[kernel and its system-call interface](the-kernel-and-system-calls.md), the
[boot and init](boot-and-init.md) sequence that starts it all, and the modern pillars of
[virtualization and containers](virtualization-and-containers.md) and
[OS security and protection](os-security-and-protection.md).

## Concepts

- [Processes and Threads](processes-and-threads.md) — the process abstraction, PCB & state machine, threads, context switching, IPC
- [CPU Scheduling](cpu-scheduling.md) — FCFS/SJF/RR/priority/MLFQ/CFS; fairness vs throughput vs latency
- [Memory Management and Virtual Memory](memory-management-and-virtual-memory.md) — paging, the MMU, page tables, TLB, page faults, swapping
- [Concurrency and Synchronization](concurrency-and-synchronization.md) — races, mutexes/semaphores/monitors, deadlock's four conditions
- [File Systems](file-systems.md) — inodes, allocation, the VFS, journaling, caching, copy-on-write
- [I/O and Device Management](io-and-device-management.md) — drivers, the device abstraction, interrupts vs polling, DMA, buffering
- [The Kernel and System Calls](the-kernel-and-system-calls.md) — kernel vs user mode, the trap/syscall interface, monolithic vs microkernel
- [Boot and Init](boot-and-init.md) — firmware → bootloader → kernel → init (PID 1); the handoff to userspace
- [Virtualization and Containers](virtualization-and-containers.md) — VMs & hypervisors vs containers (namespaces + cgroups); where isolation sits
- [OS Security and Protection](os-security-and-protection.md) — protection rings, user/kernel separation, access control, least privilege

## Canonical works

- [Modern Operating Systems](tanenbaum-modern-operating-systems.md) — Tanenbaum & Bos; the classic principles + case studies
- [Operating System Concepts](silberschatz-operating-system-concepts.md) — Silberschatz, Galvin & Gagne; the "dinosaur book"
- [Linux Kernel Development](love-linux-kernel-development.md) — Robert Love; how the Linux kernel actually works
- [Operating Systems: Three Easy Pieces](../computer-science/ostep-operating-systems.md) — Arpaci-Dusseau; free, virtualization/concurrency/persistence (in computer-science)

## Related fields

[Computer science](../computer-science/operating-systems.md) (the survey + concurrency),
[Linux & Unix](../linux/index.md) (a concrete OS), [electrical engineering](../electrical-engineering/hardware-software-boundary.md)
(the hardware below), [AI platform](../ai-platform/execution-sandboxing.md) (sandboxing on
OS primitives), and [DevOps & SRE](../devops-sre/kubernetes.md) (containers at scale).
- [From Code to Kernel](from-code-to-kernel.md) — the full call chain: Python → CPython → a C function → libc → the syscall trap → kernel mode; why everything eventually speaks C to the OS
