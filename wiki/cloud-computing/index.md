---
type: Index
title: Cloud Computing
tags: [cloud, aws, gcp, azure, cloud-native, index]
timestamp: 2026-07-14
---

# Cloud Computing

Renting computing — compute, storage, networking, and managed services — on demand from a
provider instead of owning hardware. This is the dedicated deep-dive; the one-note intro is
[networking → cloud computing](../networking/cloud-computing.md). It's built on
[virtualization](../operating-systems/virtualization-and-containers.md) and
[networking](../networking/index.md), operated with the practices in
[DevOps & SRE](../devops-sre/index.md), and is where most modern
[distributed systems](../distributed-systems/index.md) and
[AI workloads](../ai-platform/serving-llms-vllm-skypilot.md) run.

## The shape of the field

The cloud is sold in layers — [service models](cloud-service-models.md) (IaaS/PaaS/SaaS/FaaS)
across [deployment models](cloud-deployment-models.md) (public/private/hybrid/multi) — from
[the major providers](the-major-cloud-providers.md). Its primitives are
[compute](compute-in-the-cloud.md), [storage](cloud-storage.md), and
[networking](cloud-networking.md), plus [serverless & managed services](serverless-and-managed-services.md).
Built well, that becomes [cloud-native architecture](cloud-native-and-kubernetes.md)
following [cloud architecture patterns](cloud-architecture-patterns.md) — while keeping
[cost](cloud-cost-and-finops.md) and [security & IAM](cloud-security-and-iam.md) under control.

## Concepts

- [Cloud Service Models](cloud-service-models.md) — IaaS/PaaS/SaaS/FaaS and the shared-responsibility shift
- [Cloud Deployment Models](cloud-deployment-models.md) — public/private/hybrid/multi-cloud, edge, lock-in
- [Compute in the Cloud](compute-in-the-cloud.md) — VMs → containers → serverless; elasticity; on-demand/reserved/spot
- [The Major Cloud Providers](the-major-cloud-providers.md) — AWS/GCP/Azure positions & philosophies, regions & AZs
- [Cloud Storage](cloud-storage.md) — object (S3 model), block, and file storage; durability tiers, lifecycle
- [Cloud Networking](cloud-networking.md) — VPCs, security groups, load balancers, cloud DNS, CDNs
- [Serverless and Managed Services](serverless-and-managed-services.md) — FaaS, scale-to-zero, cold starts; control-for-burden
- [Cloud-Native and Kubernetes](cloud-native-and-kubernetes.md) — containers + orchestration, microservices, twelve-factor, GitOps
- [Cloud Architecture Patterns](cloud-architecture-patterns.md) — the Well-Architected pillars, design for failure, decoupling, auto-scaling
- [Cloud Cost and FinOps](cloud-cost-and-finops.md) — pay-as-you-go, pricing dimensions, spot/reserved, egress, FinOps
- [Cloud Security and IAM](cloud-security-and-iam.md) — shared responsibility, least-privilege IAM, secrets, encryption, isolation

## Canonical works

- [AWS Well-Architected Framework](aws-well-architected-framework.md) — the six pillars; the de-facto cloud-architecture reference
- [Cloud Computing: Concepts, Technology & Architecture](erl-cloud-computing-concepts.md) — Thomas Erl; the comprehensive academic text
- [Cloud Native Patterns](cloud-native-patterns-davis.md) — Cornelia Davis; designing apps for the cloud
- [Architecting the Cloud](kavis-architecting-the-cloud.md) — Michael Kavis; design decisions across the service models

## Related fields

[Networking](../networking/index.md) (VPCs, DNS, CDNs), [DevOps & SRE](../devops-sre/index.md)
(Docker, Kubernetes, IaC, SRE), [operating systems](../operating-systems/virtualization-and-containers.md)
(virtualization), [distributed systems](../distributed-systems/index.md), and
[AI platform](../ai-platform/serving-llms-vllm-skypilot.md) (running models in the cloud).
