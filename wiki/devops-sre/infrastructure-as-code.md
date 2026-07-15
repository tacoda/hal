---
type: Reference
title: "Infrastructure as Code"
tags: [infrastructure-as-code, iac, immutability, idempotence, automation, cloud, devops, testing]
timestamp: 2026-07-14
source: https://infrastructure-as-code.com/book/
---

# Infrastructure as Code

Kief Morris makes the case that in a cloud/dynamic-infrastructure world, servers,
networks, and services should be defined and managed the same way we manage application
code: in **version-controlled, executable definition files**, provisioned and changed by
automated tooling rather than by hand. Manual, snowflake-configured infrastructure is the
enemy; the book is a catalog of principles, practices, and patterns for eliminating it.
Morris also appears in HAL on the agent side —
[humans and agents](../harness-engineering/humans-and-agents-morris.md).

## The core idea: infrastructure config as versioned code

Every piece of infrastructure is described in a definition file (Terraform, CloudFormation,
Ansible, etc.), kept under source control, reviewed, and applied through automation. The
benefits are the benefits of software engineering: reproducibility, auditability,
diffability, and the ability to rebuild an environment from scratch on demand.

## Key properties

- **Immutability** — rather than patching a running server in place (mutating it over
  time until it becomes a fragile snowflake), you rebuild and replace it from the
  definition. Immutable infrastructure means a running instance is a disposable, exact
  product of its config, never a hand-tuned artifact.
- **Idempotence** — applying the same definition any number of times converges to the
  same end state. Tooling reconciles actual state to declared state, so re-runs are safe
  and drift is corrected rather than compounded.

## Core practices

1. **Define everything as code** — no undocumented manual steps; the definition files are
   the single source of truth.
2. **Continuously test and deliver** — run infrastructure changes through a
   [deployment pipeline](continuous-delivery.md) with automated tests, exactly as with
   application code ([The DevOps Handbook](devops-handbook.md) telemetry and pipeline
   ideas apply directly).
3. **Small changes** — make many small, frequent, reversible changes rather than large
   risky batches; small batch size is what keeps risk low, echoing
   [Accelerate](accelerate.md).

## Patterns and anti-patterns

The book contrasts good patterns against the failure modes teams fall into:

- **Snowflake servers** — unique, hand-configured hosts nobody can reproduce. Anti-pattern.
- **Configuration drift** — running state silently diverging from the definition.
  Idempotent, continuously-applied config prevents it.
- **Immutable/phoenix servers** — servers rebuilt from scratch on every change, never
  patched in place. Pattern.

Together these support the disposable, self-service infrastructure that platform teams
provide in [Team Topologies](team-topologies.md) and that reliable operations in
[Site Reliability Engineering](site-reliability-engineering.md) depend on. The style also
underpins container/orchestration systems like
[Kubernetes](../distributed-systems/kubernetes-up-and-running.md) and the disposability principles of the
[Twelve-Factor App](../distributed-systems/twelve-factor-app.md).

## References

- [Infrastructure as Code — infrastructure-as-code.com](https://infrastructure-as-code.com/book/)
