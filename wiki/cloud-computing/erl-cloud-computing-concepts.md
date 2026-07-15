---
type: Reference
title: "Cloud Computing: Concepts, Technology & Architecture"
tags: [cloud-computing, architecture, service-models, deployment-models, sla, textbook]
timestamp: 2026-07-14
source: https://www.oreilly.com/library/view/cloud-computing-concepts/9780133387568/
---

# Cloud Computing: Concepts, Technology & Architecture

Thomas Erl's *Cloud Computing: Concepts, Technology & Architecture* (written with
cloud-computing experts and researchers) is the comprehensive, vendor-neutral academic
treatment of cloud computing. Where a vendor framework teaches you one provider's way of
doing things, Erl's book builds the field up from first principles: it defines the
concepts, models, technology mechanisms, and reference architectures that underlie *any*
mainstream cloud platform, and it does so in the structured, building-block style Erl is
known for from his service-oriented-architecture work.

## Scope

The book moves deliberately from fundamentals to architecture to economics:

- **Fundamentals** — what a cloud actually is: a distributed technology platform that uses
  virtualization and related innovations to deliver scalable, resilient, remotely
  consumable IT resources. It grounds the reader in the business drivers and risks that
  make organizations adopt (or avoid) cloud.
- **Models** — the delivery and deployment taxonomy. On the delivery side it dissects the
  three canonical service models — see [cloud-service-models](cloud-service-models.md) —
  and on the deployment side the public/private/community/hybrid distinctions, see
  [cloud-deployment-models](cloud-deployment-models.md).
- **Technology mechanisms** — the concrete, reusable building blocks a cloud is assembled
  from: virtual servers, hypervisors, resource pools, load balancers, automated scaling
  listeners, failover systems, cloud storage devices, and the monitoring and billing
  mechanisms that sit on top. This mechanism-catalog approach is the book's signature.
- **Architecture** — how the mechanisms compose into repeatable reference architectures
  (dynamic scalability, elastic resource pooling, redundant storage, workload
  distribution, and so on), which overlap strongly with
  [cloud-architecture-patterns](cloud-architecture-patterns.md).
- **Economics and SLAs** — business-centric models, metrics, and formulas for financially
  assessing cloud resources against on-premises IT, plus templates for calculating
  SLA-related quality-of-service values (availability, reliability, response time).

## Central ideas

The organizing insight is that cloud computing is best understood as a *layered assembly
of well-defined, reusable mechanisms* rather than as a set of vendor products. By naming
each mechanism precisely and showing how mechanisms combine into architectures, the book
gives a stable mental model that survives the churn of individual services and providers —
which is exactly why it works as a textbook. Its second insight is that cloud decisions
are inseparable from economics: the same rigor applied to the technology (defined
mechanisms) is applied to cost, SLA quality-of-service, and the comparison against
traditional enterprise premises.

## Where it fits

This is the theory layer beneath the practitioner references in this folder. The
service-model and deployment-model concepts it formalizes are the same ones expanded in
[cloud-service-models](cloud-service-models.md) and
[cloud-deployment-models](cloud-deployment-models.md); its mechanism-to-architecture
progression is the vendor-neutral counterpart to
[cloud-architecture-patterns](cloud-architecture-patterns.md).

## References

- [Cloud Computing: Concepts, Technology & Architecture](https://www.oreilly.com/library/view/cloud-computing-concepts/9780133387568/)
