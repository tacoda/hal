---
type: Reference
title: "OWASP Top 10 for LLM Applications (2025)"
tags: [security, llm, owasp, prompt-injection, ai-code-security, guardrails]
timestamp: 2026-07-14
source: https://genai.owasp.org/llm-top-10/
---

# OWASP Top 10 for LLM Applications (2025)

The OWASP Gen AI Security Project's Top 10 is the industry reference list of the most
critical risks in building and securing LLM and generative-AI applications across the
development, deployment, and management lifecycle. It is the canonical vocabulary teams
use to name AI-specific failure modes — the same list Daniel Whitenack points people to
in [LLM Safeguards](llm-safeguards.md) ("just search for llm top 10").

## The 2025 list

| ID | Risk | What it is |
|----|------|-----------|
| **LLM01** | Prompt Injection | User (or retrieved) input alters the model's behavior or instructions in unintended ways. |
| **LLM02** | Sensitive Information Disclosure | PII, secrets, or proprietary data leak out through the model or its application. |
| **LLM03** | Supply Chain | Vulnerabilities in models, datasets, packages, and third-party components feeding the system. |
| **LLM04** | Data and Model Poisoning | Tampering with pre-training, fine-tuning, or embedding data to corrupt behavior. |
| **LLM05** | Improper Output Handling | Insufficient validation/sanitization of model output before it's used downstream. |
| **LLM06** | Excessive Agency | Too much autonomy, permission, or reach granted to an agent, so one bad instruction does real damage. |
| **LLM07** | System Prompt Leakage | Exposure of system-prompt contents (instructions, secrets, guardrails) to users. |
| **LLM08** | Vector and Embedding Weaknesses | Attacks on the embedding/retrieval layer of RAG systems. |
| **LLM09** | Misinformation | Confident, plausible, but wrong output (hallucination) treated as fact. |
| **LLM10** | Unbounded Consumption | Resource-exhaustion and denial-of-service via uncontrolled token/compute usage. |

## How the entries connect

These risks are not independent — mitigating one often means engineering a control that
sits *around* the model:

- **LLM01 / LLM02 / LLM06** motivate the [guardrails proxy](guardrails-proxy.md) pattern:
  a filter in front of and behind the model that catches injections and strips sensitive
  data. [Data Governance](data-governance.md) cites LLM02 and LLM06 directly.
- **LLM06 Excessive Agency** is the agentic risk — the fix is least-privilege identity
  ([Agent Identity & Access](agent-identity-access.md)) and bounded execution
  ([Execution Sandboxing](execution-sandboxing.md)), plus human-in-the-loop dry runs.
- **LLM03 Supply Chain** is the AI-flavored version of the classic dependency problem —
  trusted model registries, license checks, and attestation.
- **LLM09 Misinformation** is the hallucination problem addressed with grounding (RAG) and
  factual-consistency scoring rather than trust.

See [LLM Safeguards](llm-safeguards.md) for a practitioner's concrete mitigations mapped
onto this list, and [AI Code Security](ai-code-security.md) for the code-generation slice.

## Related

- [LLM Safeguards](llm-safeguards.md) — concrete Enterprise mitigations mapped to this list.
- [Guardrails Proxy](guardrails-proxy.md) — the filter-around-the-model control for
  LLM01/02/06.
- [Data Governance](data-governance.md) — cites LLM02 and LLM06 as core failure modes.
- [Agent Identity & Access](agent-identity-access.md) and
  [Execution Sandboxing](execution-sandboxing.md) — mitigations for LLM06 Excessive Agency.
- [AI Code Security](ai-code-security.md) — the code-generation security surface.

## References
- [2025 Top 10 Risk & Mitigations for LLMs and Gen AI Apps — OWASP Gen AI Security Project](https://genai.owasp.org/llm-top-10/)
