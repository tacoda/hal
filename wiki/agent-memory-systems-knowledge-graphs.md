---
type: Reference
title: Agent Memory Systems and Knowledge Graphs
tags: [agent-memory, knowledge-graph, letta, mem0, graphiti, cognee, temporal-graph]
timestamp: 2026-07-14
source: https://codepointer.substack.com/p/agent-memory-systems-and-knowledge
---

# Agent Memory Systems and Knowledge Graphs

A code-level comparison of four agent-memory systems — **Letta, Mem0, Graphiti
(Zep), and Cognee** — asking two concrete questions of each: how does it handle
**co-retrieval** (pulling related facts together) and how does it handle **facts
that change over time**?

## Graphiti (Zep): a bi-temporal fact graph

Graphiti is built entirely around a graph. Its data model has:

- **EpisodicNodes** — store the original input each fact was extracted from.
- **EntityNodes** — the entities themselves.
- **CommunityNodes** — summaries of clusters of related entities.
- **EntityEdges** — the *fact* edges: `Entity --RELATES_TO--> Entity`, each
  carrying fact text and an embedding.

Every fact edge is **bi-temporal**, recording two independent time axes:

- **Valid time** — when the fact was true in the world (`valid_at` / `invalid_at`).
- **Transaction time** — when the system learned it (`created_at` / `expired_at`).

When a contradicting fact arrives, the old edge is **stamped invalid, not
deleted** (`edge.invalid_at = new_edge.valid_at`, `edge.expired_at = now`). The
graph keeps its own history, so you can ask "what did we believe was true as of
last Tuesday." This is the engine behind [Zep](zep-temporal-knowledge-graph.md).

## The four, side by side

- **Mem0** — a memory *layer*, not a framework. Optimizes for stable
  **user-preference recall**. Fastest path from zero to working memory.
- **Letta** (MemGPT lineage) — memory *is* the architecture: stateful agents you
  address as services, each with a self-edited core scratchpad plus a large
  archival store.
- **Graphiti / Zep** — a **temporal knowledge graph**; the value is
  chronologically-correct fact lookup with validity windows.
- **Cognee** — closer to **graph-RAG**: documents, entities, relationships, with a
  remember / recall / forget / improve pipeline.

Mem0 and Zep both brand as "memory for AI agents," but Mem0 optimizes for stable
preference recall while Zep optimizes for temporally-correct fact lookup — they
overlap less than the marketing suggests.

## Related

- [Memory Engineering](memory-engineering.md) — the general discipline these tools implement.
- [Zep](zep-temporal-knowledge-graph.md) — the paper behind Graphiti.
- [Best AI Agent Memory 2026](best-ai-agent-memory-2026.md) — a decision-tree comparison of the same four.

## References
- [Agent Memory Systems and Knowledge Graphs: Letta, Mem0, Graphiti, and Cognee](https://codepointer.substack.com/p/agent-memory-systems-and-knowledge)
