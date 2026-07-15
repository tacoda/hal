---
type: Reference
title: Amazon Bedrock AgentCore Code Interpreter
tags: [execution-sandboxing, aws, bedrock, agent-runtime, code-execution, security, managed-service]
timestamp: 2026-07-14
source: https://aws.amazon.com/blogs/machine-learning/introducing-the-amazon-bedrock-agentcore-code-interpreter/
---

# Amazon Bedrock AgentCore Code Interpreter

AWS's **managed, secure sandbox for running AI-agent-generated code.** An agent
sends code; the service runs it in an isolated environment and returns output,
errors, and any generated visualizations. It is a concrete managed instance of the
[Execution Sandboxing](execution-sandboxing.md) pattern, purpose-built for the
untrusted, unpredictable code that agents produce.

## What it is

The Code Interpreter runs **Python, JavaScript, and TypeScript** for data analysis,
visualization, and mathematical computation. Each execution happens in a
**dedicated sandbox** with complete isolation from other workloads and from the
broader AWS infrastructure. What sets it apart from a generic execution environment
is its optimization for **AI-generated workloads**: intelligent resource
management, automatic error handling, and built-in safeguards designed specifically
for untrusted code.

## Key capabilities

- **Secure sandbox architecture** — low-latency session startup and compute-based
  **session isolation** for complete workload separation.
- **Configurable network access** — either a fully isolated sandbox or a controlled
  public-network mode, chosen per policy.
- **Resource constraints** — maximum limits on compute/resources to contain
  runaway (e.g. hallucinated infinite-loop) code.
- **Session-based execution** — state persists within a session so an agent can run
  multi-step analyses.

## Why it matters

This is the "isolate first, grant narrow access inside the boundary" pattern
delivered as a service: the agent gets full freedom to run code, but only within a
disposable, resource-capped, network-restricted sandbox. It removes the need for
each team to build and harden its own execution substrate — the same motivation
laid out in [Why, and How, You Need to Sandbox AI-Generated Code](why-and-how-to-sandbox-ai-generated-code.md).

## Related

- [Execution Sandboxing](execution-sandboxing.md) — the pattern; this is a managed
  implementation.
- [Why, and How, You Need to Sandbox AI-Generated Code](why-and-how-to-sandbox-ai-generated-code.md)
  — the threat model this service answers.
- [Agent Runtime](agent-runtime.md) — AgentCore is AWS's broader agent runtime; the
  Code Interpreter is its execution sandbox.
- [Registries](registries.md) — sibling AgentCore concern (AWS Agent Registry).

## References
- [Introducing the Amazon Bedrock AgentCore Code Interpreter — AWS ML Blog](https://aws.amazon.com/blogs/machine-learning/introducing-the-amazon-bedrock-agentcore-code-interpreter/)
