---
type: Reference
title: "The Prompt Report: A Systematic Survey of Prompt Engineering Techniques (Schulhoff et al., 2024)"
tags: [prompting, prompt-engineering, survey, taxonomy, llm, context-engineering]
timestamp: 2026-07-14
source: https://arxiv.org/abs/2406.06608
---

# The Prompt Report

A large-team systematic survey (Sander Schulhoff, Michael Ilie, Nishant Balepur, and ~28 co-authors, 2024) that tries to impose order on the messy, jargon-laden field of prompt engineering. The authors' core complaint: prompting is widely used and heavily researched, yet suffers from conflicting terminology and a fragmented understanding of what actually makes a prompt effective, because the discipline emerged so recently. Their answer is a structured ontology built from a systematic literature review.

## What it delivers

- **A vocabulary of 33 terms** — a shared lexicon for talking about prompts precisely (e.g., what "prompt," "prompt template," "exemplar," "in-context learning" concretely mean), so papers and practitioners stop reinventing names for the same thing.
- **A taxonomy of 58 text-based prompting techniques** — organized into families (zero-shot, few-shot, thought-generation / chain-of-thought, decomposition, ensembling, self-criticism, etc.), each placed in relation to the others rather than listed in isolation.
- **40 techniques for other modalities** — extending the taxonomy beyond text to image, audio, and multimodal prompting.
- **Best practices and guidelines**, including concrete advice for prompting state-of-the-art LLMs like ChatGPT.
- **A meta-analysis** of the entire literature on natural-language prefix-prompting, aggregating what the empirical record actually supports.

The value is the map, not any single technique: it is a reference taxonomy you consult to locate a method and understand how it relates to its neighbors.

## Why it matters here

Prompting is the surface where a human (or a harness) steers a model, so a disciplined taxonomy is foundational to [context engineering](context-engineering.md) and to deliberately shaping the loop in [engineer the loop](engineer-the-loop.md). It complements the counter-pressure in [delete 90% of your prompt](delete-90-percent-of-your-prompt.md): the survey catalogs what techniques exist, while that note argues most of a real-world prompt is dead weight. The techniques it names are also the raw material that programmatic systems like [DSPy](dspy.md) aim to select and optimize automatically instead of by hand-tuning prompt strings.

## References

- [The Prompt Report: A Systematic Survey of Prompt Engineering Techniques (arXiv:2406.06608)](https://arxiv.org/abs/2406.06608)
