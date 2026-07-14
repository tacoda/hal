---
type: Reference
title: LLM Evals FAQ — Everything You Need to Know
tags: [evals, error-analysis, rag, binary-evals, domain-expert, faq]
timestamp: 2026-07-14
source: https://hamel.dev/blog/posts/evals-faq/
---

# LLM Evals FAQ — Everything You Need to Know

The sharp-opinion FAQ Hamel Husain and Shreya Shankar wrote from teaching evals
to 700+ engineers and PMs. Pairs with the method in
[LLM-as-a-Judge — A Complete Guide](llm-as-a-judge-complete-guide.md) and the
concept note [evals & LLM-as-a-judge](evals-llm-as-a-judge.md).

## Error analysis is the whole game

The single highest-ROI activity. Two steps, both human-led:

1. **Open coding** — one annotator (a [domain-expert](llm-as-a-judge-complete-guide.md)
   "benevolent dictator") reads raw traces and journals notes, focusing on the
   *first* failure per trace (upstream errors cascade downstream).
2. **Axial coding** — cluster those notes into a failure taxonomy, then count.

You cannot skip looking at your own data. "Can't the AI just eval it?" is the
top misconception — it can't discover *new* failure modes, only score known ones.

## Sharp opinions that recur

- **Binary (pass/fail) over Likert (1–5).** Binary forces a decision instead of
  hiding uncertainty in the middle. Adjacent points on a scale are subjective and
  need larger samples to distinguish. Track sub-components as separate binary
  checks ("4 of 5 expected facts") rather than one fuzzy number.
- **Generic metrics (BERTScore, ROUGE, cosine) are mostly useless** for judging
  app behavior — "the abuse of generic metrics is endemic." Derive
  app-specific checks from error analysis instead. Similarity metrics *do* help
  for retrieval/recommendation.
- **One benevolent dictator, not a committee.** Needing five experts to judge one
  interaction is a sign the product scope is too broad. Add annotators (with
  Cohen's Kappa agreement) only when the domain truly demands it.
- **Don't outsource prompt-writing to auto-optimizers early.** "Good writing is
  good thinking" — the act of writing the prompt externalizes your requirements.
  Optimizers hill-climb a fixed metric; they can't surface new failures.

## What you can and cannot hand to an LLM

You *may* use an LLM to scale labeling once your judge is validated. You must
**not** delegate: initial open coding, validating failure taxonomies, ground-truth
labels for judge validation, or root-cause analysis. Use LLMs to *scale* what
you've learned, not to avoid looking at data.

## RAG evals

Split retrieval from generation. **Retrieval** is a search problem — use IR
metrics (Recall@k, Precision@k, MRR) against synthetically generated
query/document pairs (take a doc, extract a fact, generate the question it
answers). **Generation** uses the standard error-analysis + validated-judge loop.

## References
- [LLM Evals: Everything You Need to Know — Hamel Husain & Shreya Shankar](https://hamel.dev/blog/posts/evals-faq/)
