---
type: Reference
title: "The Allergy Was in the Vector Store. The Agent Still Bought the Shrimp"
tags: [harness-engineering, agents, memory, rag, vector-store, retrieval]
timestamp: 2026-07-14
source: https://rickhigh.substack.com/p/the-allergy-was-in-the-vector-store
---

# The Allergy Was in the Vector Store. The Agent Still Bought the Shrimp

Part 3 of Rick Hightower's harness series, on agent memory — and specifically why treating
memory as one undifferentiated bucket ("dump everything in, retrieve by similarity, hope")
is a failure surface. RAG is not automatically memory; a fact can exist in storage, in a
vector store, with a correct embedding, and *still* never reach the model when it matters.

The story: Sarah's severe shellfish allergy was "remembered" — embedded in a vector store.
But when the agent ran `vector_store.search("show me this week's promotions", k=10)`, it got
back ten "prefers email contact" look-alikes. The allergy was in the store; it just wasn't
*close* to the query. The agent bought the shrimp. The fix was never a better embedding
model.

## Three tiers, three questions

Confusing the tiers is the single most common memory design mistake — and it produces
exactly Sarah's failure. Each tier answers a different question:

| Tier | What it is | Access pattern |
|------|-----------|----------------|
| **Working memory** | Bounded tokens currently in the context window — the live scratchpad for this turn | In-context; does not survive a session restart |
| **Semantic memory** | Extracted facts in a queryable store, retrieved *by meaning* across sessions | Vector store + extraction logic, top-k by similarity |
| **Persistent cross-session memory** | Durable, human-readable state loaded *by identity* — confirmed preferences, account config, allergies | Loaded at session start by user identity, not similarity |

The decision rule is one line: **name the tier before you write the entry.**

Sarah's allergy is a confirmed, safety-critical fact about a specific person. It belongs in
**persistent memory, loaded by her identity at session start** — not embedded and hoped for.
The distinction that matters: *a fact retrieved by similarity is a fact you might find; a
fact loaded by identity is a fact you always have.* Similarity search returns what's close
to the current query, and "show me this week's promotions" is not close to "shellfish
allergy."

## Why "embed everything" fails

Semantic memory isn't the villain — misuse is. A vector store is *right* for facts you
genuinely retrieve by meaning because you can't know in advance which will matter next: past
bookings a customer disliked, phrasings they responded to, a constraint mentioned once. It's
*wrong* for a confirmed safety-critical fact about a known person.

Done right, semantic memory respects a four-step pipeline (memory is one step, not the whole
job): **extract → dedupe on write → embed & upsert → retrieve top-k**. When a turn ends,
send it to an extractor that pulls *salient facts, not the raw transcript*; a write-time
similarity check keeps near-duplicates out (near-duplicates are what drowned Sarah's allergy
in a stack of look-alikes); retrieval pulls only the few facts relevant now. Skip
extraction and you store noise; skip deduplication and you store noise twice. What belongs
here: durable preferences, named entities, corrected errors. What doesn't: raw transcript,
session metadata, tool logs.

## Forgetting on purpose

An agent that keeps every memory forever accumulates contradictions, pays a growing
retrieval bill, and eventually surfaces facts so stale they mislead. **Forgetting is a design
decision, not a failure mode.** The canonical discipline scores each entry at retrieval time
and lets low-signal entries fall out of the top-k while remaining in the store for audit.

## Related notes

- [The naked agent (Hightower)](hightower-the-naked-agent.md) — Part 1; this closes its Failure 2 (lost state).
- [Context assembly (Hightower)](hightower-context-assembly.md) — Part 4; the companion distinction between what an agent *remembers* vs what it *sees*.
- [Memory engineering](memory-engineering.md), [Architecting agent memory](architecting-agent-memory.md), [Agent memory systems & knowledge graphs](agent-memory-systems-knowledge-graphs.md) — the memory-tier discipline in HAL.
- [Zep temporal knowledge graph](zep-temporal-knowledge-graph.md), [Best AI agent memory 2026](best-ai-agent-memory-2026.md) — concrete memory backends.

## References

- [The Allergy Was in the Vector Store. The Agent Still Bought the Shrimp](https://rickhigh.substack.com/p/the-allergy-was-in-the-vector-store) — Rick Hightower
