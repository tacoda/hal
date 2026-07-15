---
type: Index
title: Linux & Unix
tags: [linux, unix, operating-systems, index]
timestamp: 2026-07-14
---

# Linux & Unix

The concepts, philosophy, and mental model of Linux/Unix — how the system is put together
and *why*, plus the idioms that follow — **not** command/man-page reference (that lives in
an MCP docs server). This folder is the applied, opinionated companion to the general
[operating systems](../computer-science/operating-systems.md) theory in computer science,
and the substrate under [containers/sandboxing](containers-and-namespaces.md) that
[agent execution sandboxing](../ai-platform/execution-sandboxing.md) relies on.

## The shape of the field

It all descends from the [Unix philosophy](unix-philosophy.md) — small tools that do one
thing well and compose over text streams — expressed through
[everything is a file](everything-is-a-file.md) (one open/read/write interface for files,
devices, pipes, sockets) and driven from [the shell and pipes](the-shell-and-pipes.md).
Underneath, [the kernel](the-linux-kernel.md) manages
[processes and signals](processes-and-signals.md), [the filesystem](the-filesystem-and-fhs.md),
[permissions and users](permissions-and-users.md), and [networking](networking-on-linux.md),
and is brought up by [init and services](init-and-services.md). A
[distribution](package-management-and-distributions.md) bundles the kernel, userland, and a
package manager; and [containers](containers-and-namespaces.md) turn out to be just kernel
namespaces + cgroups — a process, not a VM.

## Concepts

- [The Unix Philosophy](unix-philosophy.md) — do one thing well, compose over text streams, mechanism not policy
- [Everything Is a File](everything-is-a-file.md) — files, devices, pipes, sockets, /proc all through one interface (the VFS)
- [The Shell and Pipes](the-shell-and-pipes.md) — the composition engine: stdin/stdout/stderr, pipes, redirection, filters, globbing
- [Processes and Signals](processes-and-signals.md) — PIDs and the process tree, fork/exec, zombies, job control, SIGTERM→SIGKILL
- [The Filesystem and the FHS](the-filesystem-and-fhs.md) — one unified tree, mounts, the FHS layout, inodes vs names, the VFS
- [Permissions and Users](permissions-and-users.md) — users/groups, owner/group/other rwx, setuid/sticky, root vs least privilege, sudo
- [The Linux Kernel](the-linux-kernel.md) — kernel vs userspace, the syscall boundary, monolithic-with-modules, what it manages
- [Init and Services](init-and-services.md) — PID 1, SysV init vs systemd, units/targets, daemons, journald, the boot sequence
- [Package Management and Distributions](package-management-and-distributions.md) — what a distro is; apt/dnf/pacman, dependency resolution, signing, Flatpak/Snap/Nix
- [Networking on Linux](networking-on-linux.md) — interfaces, the sockets API, routing, DNS, netfilter/nftables, network namespaces
- [Containers and Namespaces](containers-and-namespaces.md) — namespaces + cgroups + union FS; a container is a process, the basis of sandboxing

## Canonical works

- [The Art of Unix Programming](art-of-unix-programming.md) — Eric S. Raymond; the Unix design culture (free)
- [The Linux Programming Interface](kerrisk-linux-programming-interface.md) — Michael Kerrisk; the definitive syscall reference
- [How Linux Works](ward-how-linux-works.md) — Brian Ward; the accessible bottom-up tour
- [UNIX and Linux System Administration Handbook](nemeth-unix-linux-sysadmin.md) — Nemeth et al.; the sysadmin bible
- [The Unix Programming Environment](kernighan-pike-unix-programming-environment.md) — Kernighan & Pike; programming the Unix way

## Related fields

[Computer science](../computer-science/operating-systems.md) (OS theory, networks),
[AI platform](../ai-platform/execution-sandboxing.md) (sandboxing agent code on containers),
[DevOps & SRE](../devops-sre/index.md) (systemd, IaC, Kubernetes),
[distributed systems](../distributed-systems/index.md), and
[software engineering](../software-engineering/simple-made-easy.md) (the Unix-philosophy → simplicity lineage).
