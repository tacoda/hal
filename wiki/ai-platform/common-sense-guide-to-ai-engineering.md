---
type: Reference
title: "A Common-Sense Guide to AI Engineering (Jay Wengrow)"
tags: [ai-engineering, llm, rag, evals, agents, prompt-engineering, book, production]
timestamp: 2026-07-14
source: https://commonsensedev.com
---

# A Common-Sense Guide to AI Engineering (Jay Wengrow)

A practitioner's book (Pragmatic Bookshelf; read as Beta **B4.0**, so specifics may still
change) on building real-world LLM applications — bridging theory and the practical
realities of shipping AI products: iteration, trade-offs, RAG, evals, and agents. The
companion site with links/resources is [commonsensedev.com](https://commonsensedev.com).

> **Copyright:** the PDF is not stored in this repo. This note is a synthesized summary;
> follow the source link for the full book.

The book builds in four parts, foundations first (echoing the "learn in order" idea of
[The AI Learning Ladder](../misc/ai-learning-ladder.md)).

## Part I — Foundations

1. **HeLLMo, World!** — first LLM app; the shape of an AI-powered program.
2. **Understanding How LLMs Work** — tokens, prediction, what the model is actually doing.
3. **Diving Deeper into LLMs** — context windows, sampling, and model behavior.
4. **Selecting an LLM** — choosing a model by capability, cost, and latency trade-offs.

## Part II — Chatbots

5. **Building a Chatbot** — a chat-powered application end to end.
6. **Augmenting a Prompt with Knowledge** — injecting external knowledge into prompts.
7. **Efficiently Adding Knowledge with RAG** — retrieval-augmented generation; embeddings,
   vector search, chunking, relevance ranking.
8. **Measuring Quality with Evals** — evaluating output quality systematically.
9. **Prompt Engineering** — practical prompting that works.
10. **Reducing Hallucinations** — grounding answers, limiting fabrication.
11. **Evaluating and Optimizing RAG** — measuring and tuning the retrieval pipeline.

## Part III — Agents

12. **Equipping an LLM with Tools** — tool/function calling.
13. **Running the Agent Loop** — the perceive → act → observe cycle.
14. **Architecting Agentic Workflows** — structuring multi-step agent systems.
15. **Enhancing Retrieval with Agentic RAG** — agents that drive retrieval.
16. **Building System-Integrated Agents** — agents wired into real systems/APIs.

## Part IV — Production

17. **Setting Guardrails** — safety, policy, and input/output constraints.
18. **Observing AI Systems** — tracing, logging, monitoring AI behavior.
19. **Handling Exceptions** — failure handling in probabilistic systems.
20. **Automating Evals** — evals in CI, continuous quality measurement.

## Cross-links

The book-length treatment of themes running through HAL's AI-engineering cluster: RAG and
the [AI Factory Stack](ai-factory-stack.md); evals/guardrails/observability as the
production layers of [Agent Harness Engineering](../harness-engineering/agent-harness-engineering.md); the agent
loop of [Engineer the Loop, Not the Prompt](../harness-engineering/engineer-the-loop.md); prompting economy in
[Delete 90% of Your Prompt](../agentic-coding/delete-90-percent-of-your-prompt.md); and production structure
in [Production AI App — Repository Structure](production-ai-app-structure.md).

## References

- Jay Wengrow, *A Common-Sense Guide to AI Engineering* (Beta), published by The Pragmatic Bookshelf — [pragprog.com](https://pragprog.com) (search the title; exact URL not verified here). Companion site: [commonsensedev.com](https://commonsensedev.com).
