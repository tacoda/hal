---
type: Reference
title: AWS Agent Registry
tags: [registries, aws, bedrock, agentcore, governance, discovery, agents, lifecycle]
timestamp: 2026-07-14
source: https://aws.amazon.com/blogs/machine-learning/the-future-of-managing-agents-at-scale-aws-agent-registry-now-in-preview/
---

# AWS Agent Registry

A managed **catalog and governance layer for agents, tools, and agent skills**,
available in preview through Amazon Bedrock AgentCore. It is a concrete instance of
the [Registries](registries.md) pattern: the system-of-record that makes agents
**discoverable, governable, and versioned** once an org has more than a handful of
them.

## The problem it solves

When you have a few agents you can track them in a spreadsheet. At hundreds or
thousands, you lose control: you can't enforce standards, track ownership, or manage
agents from development through retirement — and without governance, **anyone can
register anything**. Teams also rebuild capabilities that already exist because they
can't find them.

## What it provides

```mermaid
flowchart LR
    D[Draft] --> P[Pending approval]
    P --> A[Approved / discoverable]
    A --> DEP[Deprecated]
    DEP --> RET[Retired]
```

- **Discovery** — a searchable enterprise catalog so teams find and **reuse**
  existing agents, tools, and skills instead of rebuilding them.
- **Governance over publishing** — admins use **IAM policies** to control who may
  register and who may discover. Every record follows an **approval workflow**
  (draft → pending approval → discoverable), with hooks to plug in existing approval
  processes.
- **Lifecycle management** — tracks records across their whole lifecycle,
  development through retirement, and lets orgs **deprecate** records no longer in
  use.
- **Versioning** — records are versioned to track change over time.
- **Custom metadata** — attach team ownership, compliance status, deployment
  environment, and similar attributes to each entry.

Southwest Airlines is cited as an early adopter using it for an enterprise-wide
agent catalog and governance.

## Related

- [Registries](registries.md) — the pattern; AWS Agent Registry is a managed
  implementation.
- [Bedrock AgentCore Code Interpreter](bedrock-agentcore-code-interpreter.md) —
  sibling AgentCore service (execution) to this one (cataloguing).
- [Agent Identity & Access](../ai-governance/agent-identity-access.md) — the IAM-based control over
  who can register and discover.
- [Data Governance](../ai-governance/data-governance.md) — the broader governance frame this sits
  inside.

## References
- [The future of managing agents at scale: AWS Agent Registry now in preview — AWS ML Blog](https://aws.amazon.com/blogs/machine-learning/the-future-of-managing-agents-at-scale-aws-agent-registry-now-in-preview/)
