---
type: Reference
title: "CodeGate / Stacklok: Securing AI Coding Assistants and MCP"
tags: [security, mcp, guardrails, ai-code-security, secrets, open-source, kubernetes]
timestamp: 2026-07-14
source: https://codegate.ai
---

# CodeGate / Stacklok: Securing AI Coding Assistants and MCP

`codegate.ai` is Stacklok's project. **CodeGate** began as a local, open-source privacy
and security layer that sits between an AI coding assistant (Copilot, Cursor, Claude,
Continue, etc.) and the model — a [guardrails proxy](guardrails-proxy.md) that keeps
sensitive data local: **redacting secrets and PII** out of prompts, screening for
prompt-injection and malicious-package suggestions, all on the developer's own machine so
raw context never ships to a vendor. [Data Governance](data-governance.md) cites it,
alongside the [LLM Secrets vault](llm-secrets.md), as a "local data-loss control" that
keeps secrets out of the model's reach.

Stacklok has since folded that ambition into a broader **enterprise MCP platform** built
on the open-source **ToolHive** core (Apache 2.0). The `codegate.ai` domain now presents
this platform: **run AI agents and Model Context Protocol (MCP) servers on your existing
Kubernetes infrastructure, under the same governance as everything else.** (Stacklok was
founded by Craig McLuckie and Joe Beda, co-creators of Kubernetes — hence the K8s-native
framing.)

## The platform model: MCP as a Kubernetes-native, governed runtime

The pitch is to treat MCP servers as ordinary cluster workloads so existing platform
controls apply, rather than letting "shadow MCP" proliferate:

- **MCP servers are pods; namespaces are boundaries.** Existing Ingress, NetworkPolicy,
  and service-mesh rules apply out of the box.
- **Identity reuse** — map K8s ServiceAccounts and OIDC claims to MCP permissions, so
  agents authenticate the same way microservices do. This is the
  [agent identity & access](agent-identity-access.md) pattern applied to tool servers.
- **A curated registry** of trusted MCP servers teams can discover and deploy, plus a
  single gateway endpoint to reach all tools safely.
- **Observability** — native OpenTelemetry means every agent tool call flows into the
  existing stack: one pane of glass for services and agents, ending shadow MCP with full
  visibility of every agent action.
- **GitOps + governance** — MCP stays inside the same GitOps workflow and policy regime
  as the rest of the platform.

The through-line from CodeGate to the platform is the same principle: **keep AI's reach
governed and its sensitive context local**, using controls the org already trusts. It is
a concrete instance of both the [guardrails proxy](guardrails-proxy.md) and
[agent identity & access](agent-identity-access.md) patterns, bearing on the OWASP risks
of [Sensitive Information Disclosure and Excessive Agency](owasp-llm-top-10.md).

## Related

- [Guardrails Proxy](guardrails-proxy.md) — CodeGate is a canonical local example.
- [Data Governance](data-governance.md) — cites CodeGate as a local data-loss control.
- [LLM Secrets](llm-secrets.md) — the sibling local-secrets control for Claude Code.
- [Agent Identity & Access](agent-identity-access.md) — mapping K8s identity to MCP
  permissions.
- [OWASP LLM Top 10](owasp-llm-top-10.md) — the LLM02 / LLM06 risks this addresses.

## References
- [Enterprise MCP Platform for Secure AI Workflows — Stacklok / CodeGate](https://codegate.ai)
