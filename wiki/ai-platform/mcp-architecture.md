---
type: Image
title: Model Context Protocol (MCP) Architecture
tags: [mcp, agents, tools, integration, architecture]
timestamp: 2026-07-14
---

# Model Context Protocol (MCP) Architecture

A diagram (Rahul Biswas) of MCP as a standardized way for AI applications to connect with
tools, data, and enterprise systems.

- **Users / enterprise applications:** chat apps, IDE assistants, copilots, agentic
  workflows.
- **AI application / MCP host:** user interface, agent/orchestrator, LLM/model runtime,
  context manager, MCP client — manages prompts, context, memory, tool selection, and
  request orchestration.
- **Model Context Protocol (MCP):** standardized request/response, context exchange, tool
  invocation, resource discovery. Transport examples: STDIO, HTTP, WebSocket.
- **MCP servers** by type:
  - *Tools* — search, calculator, code execution, automation.
  - *Resources* — files, documents, knowledge base, APIs.
  - *Prompts / Templates* — reusable prompts, task templates, guardrails.
  - *Memory / Context services* — session memory, user preferences, conversation state.
- **Backends:** databases (Postgres/MySQL/Mongo/Redis), business apps (CRM/ERP), cloud
  services, internal APIs, observability & security.

Request flow: user request → AI app/host → MCP client → MCP server → enterprise
data/tools → response. Benefits: standardized integration, reusable tools/context, secure
access, modular & scalable, supports agentic workflows.

## Request flow

```mermaid
flowchart LR
  U["User request"] --> Host["AI App / MCP Host"]
  Host --> Cli["MCP Client"]
  Cli -->|"MCP protocol"| Srv["MCP Server (tools / resources / prompts / memory)"]
  Srv --> Ext["Enterprise data & tools"]
  Ext --> Resp["Response"]
```

## Cross-links

The tooling/integration layer (layer 5) of [Agentic Engineering Stack](../agentic-coding/agentic-engineering-stack.md)
and the "tool integration" layer of [Agent Harness Engineering](../harness-engineering/agent-harness-engineering.md),
detailed. MCP appears as a connector in [AI Harness Architecture](../harness-engineering/ai-harness-architecture.md)
and [The AI Factory Stack](ai-factory-stack.md).
