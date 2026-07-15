---
type: Reference
title: "Breaking AI to Fix It: Ian Webster's Journey from Discord's Clyde to Promptfoo"
tags: [evals, red-teaming, guardrails, security, prompt-injection, promptfoo, interview]
timestamp: 2026-07-14
source: https://www.youtube.com/watch?v=-uiF1txQxV8
---

# Breaking AI to Fix It: Ian Webster's Journey from Discord's Clyde to Promptfoo

A Latent Space podcast conversation with **Ian Webster**, founder of Promptfoo,
tracing how shipping AI to 200 million Discord users turned into an open-source
eval tool and then a security company (an $18M Series A led by a16z).

## From Clyde to Promptfoo

At Discord, Webster started the developer-platform org and then led its AI efforts,
including **Clyde** — an AI chatbot built in the GPT-3.5 era, designed as a *social*
bot that lived in channels rather than a helpful assistant (a concept later carried
forward by Character.AI and similar products). He also worked on AI summaries and
support tooling. The recurring pain of **shipping AI to 200M teenagers** is what
convinced him there was a real problem in both **evaluation** and **risk
management**.

Promptfoo began, while he was still at Discord, as a dead-simple **side-by-side
comparison** interface for prompts — this was before "eval" was even a common term.
It grew into a popular open-source eval tool.

## The fork: eval vs security

Webster faced a fork: lean into being an eval/observability tool, or pivot. He saw
the pure-eval market as a **"bloodbath"** — a long feature-parity slog, enterprise
by enterprise, against well-funded competitors. Asking instead *what do people do
with evals that has the most value to the org*, he landed on **security and safety**
as the go-to-market. Promptfoo today is "a way to find and fix issues or risks in
your AI application," security-first while remaining a popular open-source eval
tool.

## Guardrails are necessary but not sufficient

His signature framing (quoted in [Guardrails Proxy](guardrails-proxy.md)): shipping
to 200M users taught him that **"traditional guardrails aren't enough… you can't fix
stupid."** Base-model safety training addresses toxicity and generic
misbehavior, but the dangerous failures are **application-specific** — RAG access
control, business-logic mistakes — and no amount of runtime filtering removes them.
This is why Promptfoo's answer is **adversarial red-teaming tailored to each app's
business context**, run before deployment, paired with runtime guardrails as the
last line.

## Related

- [Guardrails Proxy](guardrails-proxy.md) — the runtime pattern; sources Webster's
  "can't fix stupid" quote.
- [Evals & LLM-as-a-Judge](evals-llm-as-a-judge.md) — the eval discipline Promptfoo
  grew out of.
- [AI Code Security](../security/ai-code-security.md) — securing the artifact and the runtime.

## References
- [Breaking AI to Fix It: Ian Webster's Journey — Latent Space (YouTube)](https://www.youtube.com/watch?v=-uiF1txQxV8)
