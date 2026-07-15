---
type: Image
title: The AI Factory Stack
tags: [ai, stack, llm, rag, vector-db, agents, mcp, guardrails, evals]
timestamp: 2026-07-14
---

# The AI Factory Stack

A seven-part stack for "turning data into real-world impact in 2026," each part with a
one-word role.

1. **LLM** — *the brain.* Understands and generates text, reasons, creates content → intelligence.
2. **RAG** — *the researcher.* Pulls the right information from trusted sources before the model answers → relevant context.
3. **Vector DB** — *the memory.* Stores knowledge as vectors so the system finds what it means, not just what it says → fast, smart recall.
4. **AI Agent** — *the doer.* Decides what to do, uses tools, gets things done → action & automation.
5. **MCP** — *the universal connector.* Lets agents plug into any tool, app, API, file, or database securely → one standard, endless connections.
6. **Guardrails** — *the safety layer.* Sets rules and policies to keep AI outputs safe, fair, compliant → trust & protection.
7. **Evals** — *the quality check.* Measures performance, catches issues, drives continuous improvement → reliability & improvement.

Together they form an "AI factory" that delivers real results.

## The pipeline

```mermaid
flowchart LR
  LLM["LLM — brain"] --> RAG["RAG — researcher"]
  RAG --> VDB["Vector DB — memory"]
  VDB --> AG["AI Agent — doer"]
  AG --> MCP["MCP — connector"]
  MCP --> GR["Guardrails — safety"]
  GR --> EV["Evals — quality"]
```

## Cross-links

A compact, role-per-component version of [Agentic Engineering Stack](../agentic-coding/agentic-engineering-stack.md)
and [AI Harness Architecture](../harness-engineering/ai-harness-architecture.md). Guardrails + Evals are the
verification/operations layers of [Agent Harness Engineering](../harness-engineering/agent-harness-engineering.md);
MCP is detailed in [Model Context Protocol (MCP) Architecture](mcp-architecture.md).
