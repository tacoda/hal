---
type: Reference
title: UNIX and Linux System Administration Handbook
tags: [linux, unix, sysadmin, devops, networking, security, operations]
timestamp: 2026-07-14
source: https://admin.com/
---

# UNIX and Linux System Administration Handbook

The *UNIX and Linux System Administration Handbook* — by Evi Nemeth, Garth Snyder,
Trent R. Hein, Ben Whaley, and Dan Mackin (the fifth edition, Addison-Wesley) — is the
long-standing **sysadmin bible**: the definitive practical guide to installing,
configuring, and maintaining production UNIX and Linux systems, including the machines
that carry core Internet and cloud infrastructure. Its voice is conversational and its
authors are working technologists, so the book reads as accumulated field experience
rather than abstract theory. It is deliberately practice-first: how real systems break
and how to keep them running.

## Scope and central ideas

The handbook covers essentially every facet of running systems and the networks they
sit on:

- **System fundamentals.** Booting, the [init system and services](init-and-services.md),
  process and resource management, and the day-to-day mechanics of keeping a host
  healthy.
- **Software and package management.** Installing and updating software across
  distributions — the operational side of
  [package management and distributions](package-management-and-distributions.md).
- **Storage.** Disks, file systems, volume management, and backup strategy, resting on
  the layout described in [the filesystem and FHS](the-filesystem-and-fhs.md).
- **Networking.** Network design and administration, DNS, and web hosting — the
  applied counterpart to [networking on Linux](networking-on-linux.md).
- **Security.** Hardening, access control, and defending systems in hostile
  environments.
- **Automation and modern operations.** Scripting, configuration management,
  continuous deployment, containerization, virtualization, cloud platforms, and the
  **DevOps** philosophy of running services as code — coverage the fifth edition
  substantially expanded.
- **Performance and monitoring.** Analyzing bottlenecks and observing systems in
  production.
- **The organization of IT.** Managing the human and process side of running
  infrastructure at scale.

The unifying theme is that administration is a discipline of **reliable operation under
real-world constraints** — the applied face of the concepts in
[operating systems](../computer-science/operating-systems.md).

## Related notes

- [init-and-services.md](init-and-services.md)
- [package-management-and-distributions.md](package-management-and-distributions.md)
- [networking-on-linux.md](networking-on-linux.md)
- [the-filesystem-and-fhs.md](the-filesystem-and-fhs.md)
- [the-linux-kernel.md](the-linux-kernel.md)
- [processes-and-signals.md](processes-and-signals.md)
- [the-shell-and-pipes.md](the-shell-and-pipes.md)
- [unix-philosophy.md](unix-philosophy.md)
- [operating systems](../computer-science/operating-systems.md)

## References

- [UNIX and Linux System Administration Handbook — admin.com](https://admin.com/)
