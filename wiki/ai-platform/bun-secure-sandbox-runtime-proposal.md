---
type: Reference
title: "Bun as a Secure Sandbox Runtime for AI Agent Code (Proposal)"
tags: [execution-sandboxing, bun, deno, capability-based-security, permissions, runtime, ai-generated-code]
timestamp: 2026-07-14
source: https://github.com/oven-sh/bun/issues/25929
---

# Bun as a Secure Sandbox Runtime for AI Agent Code (Proposal)

A feature request on the Bun repository (issue #25929) asking Bun to add a
**Deno-compatible permissions model** so it can safely execute LLM-generated code.
It is a runtime-level expression of the [Execution Sandboxing](execution-sandboxing.md)
pattern and the **capability-based security** principle: deny by default, grant only
the specific capabilities the code needs.

## The problem

AI agents increasingly **generate and then execute code**. Running that untrusted
code in a normal runtime gives it the process's full privileges — filesystem,
network, environment — which is exactly the risk profile described in
[Why, and How, You Need to Sandbox AI-Generated Code](why-and-how-to-sandbox-ai-generated-code.md).
Node and (by default) Bun have no built-in way to constrain what a script may touch.

## The proposal

A `--secure` flag that starts with **zero permissions**, plus explicit grants
modeled on Deno's flags:

```shell
# Execute LLM-generated code with zero permissions
bun --secure generated-code.js

# Grant only the capabilities the agent needs
bun --secure --allow-net=api.openai.com --allow-read=./workspace agent.js
```

The pitch: this would make Bun **the go-to runtime for the AI-agent era** — fast
execution combined with secure, allow-list sandboxing at the runtime level rather
than relying on an external container or VM.

## Why it matters

Most agent sandboxing today happens *above* the runtime — a container, a microVM, a
managed service like the [Bedrock AgentCore Code Interpreter](bedrock-agentcore-code-interpreter.md).
Baking an allow-list permission model **into the runtime itself** (as Deno pioneered)
pushes capability-based security down to where the code actually runs, closing the
gap for the common case of "just run this snippet safely."

## Related

- [Execution Sandboxing](execution-sandboxing.md) — the pattern; this is the
  runtime-level flavor.
- [Why, and How, You Need to Sandbox AI-Generated Code](why-and-how-to-sandbox-ai-generated-code.md)
  — the capability-based-security principle (allow-list, not block-list) this
  proposal embodies.
- [Bedrock AgentCore Code Interpreter](bedrock-agentcore-code-interpreter.md) — the
  managed-service alternative to runtime-level sandboxing.

## References
- [Bun as a secure sandbox runtime for AI agent code execution — Issue #25929](https://github.com/oven-sh/bun/issues/25929)
