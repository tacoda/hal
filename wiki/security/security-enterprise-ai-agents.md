---
type: Reference
title: "Securing Enterprise AI Agents (de Vos)"
tags: [security, ai-agents, agentsecops, mcp-security, bounded-autonomy, rag-governance, audit, enterprise]
timestamp: 2026-07-14
source: https://leanpub.com/securing-enterprise-ai-agents
---

# Securing Enterprise AI Agents (de Vos)

Thomas de Vos's field guide (six parts, twenty-one chapters) is written for **the person
who owns the sign-off** — the engineer whose demo now has to go live, the architect
triaging a stack of agent proposals, the security lead asked to bless something they
cannot fully see, the director choosing where platform investment goes. Worked examples
are drawn from financial services because that is what regulated builds look like.

The core argument: **the old security playbook was not written for agents.** Reviewing
prompts and logging chatbot sessions is enough for a chatbot, but not once a system can
pick a tool, call an API, and change state in production. Anything that can *act* needs an
identity, a boundary, an audit trail, and a way to fail safely — plus someone who has
thought about what happens when the model decides badly, retrieval returns poisoned
content, or a tool wrapper leaks a token.

## Structure

- **Part I** reframes the risk model for systems that act, not just answer.
- **Part II** — a **seven-layer reference architecture** for a production agent, from the
  human user down through the orchestrator, the model, the tool wrapper, MCP, the policy
  layer, and the data layer. Something you can defend to an auditor.
- **Part III** turns evals and observability into the **release control your CI does not
  have yet**.
- **Part IV** — secure RAG, including the parts most teams skip.
- **Part V** — coding agents in professional teams.
- **Part VI** — deployment, policy as code, incident response, run as one **AgentSecOps**
  discipline.

The deliverables it promises: the seven-layer architecture, a production-readiness
checklist you can run in an afternoon, and a working definition of **bounded AI autonomy**
that keeps the model useful without handing it the whole surface.

## Where it connects in HAL

- The attack surface it enumerates (prompt injection, poisoned retrieval, leaking tool
  wrappers) maps onto the [OWASP LLM Top 10](../ai-governance/owasp-llm-top-10.md).
- Its tool-wrapper and policy layers are the same control points as the
  [guardrails proxy](../ai-platform/guardrails-proxy.md) and
  [execution sandboxing](../ai-platform/execution-sandboxing.md) patterns.
- Part V (coding agents in teams) overlaps with [AI code security](ai-code-security.md).

## References

- [Securing Enterprise AI Agents (Leanpub)](https://leanpub.com/securing-enterprise-ai-agents)
