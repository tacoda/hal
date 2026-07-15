---
type: Reference
title: "DSPy: Compiling Declarative Language Model Calls into Self-Improving Pipelines (Khattab et al., 2023)"
tags: [dspy, prompting, llm-pipelines, compilers, optimization, prompt-engineering]
timestamp: 2026-07-14
source: https://arxiv.org/abs/2310.03714
---

# DSPy

A programming model from Omar Khattab, Arnav Singhvi, and co-authors (Stanford / Databricks, incl. Matei Zaharia and Christopher Potts, 2023) that replaces hand-written prompt strings with declarative, compilable programs. The premise: LM pipelines today are built from "prompt templates" — long strings discovered by trial and error and brittle to any change in model, task, or upstream step. DSPy proposes treating a pipeline as code that a compiler can optimize instead.

## The idea

DSPy abstracts an LM pipeline as a **text transformation graph**: an imperative computational graph in which language models are invoked through **declarative modules**. You describe *what* each step should do (its input/output behavior), not the exact prompt wording.

- **Modules are parameterized.** They can *learn* how to apply compositions of prompting, finetuning, augmentation, and reasoning techniques — by generating and collecting demonstrations rather than by a human editing a prompt string.
- **A compiler optimizes the whole pipeline** to maximize a given metric. Point it at a metric and some data, and within minutes it self-bootstraps the demonstrations and prompt structure that best serve that metric.

This inverts the usual workflow: instead of tuning prompts by hand for a fixed model, you write a small declarative program and let the compiler produce the prompts.

## Results claimed

Across case studies (math word problems, multi-hop retrieval, complex QA, agent-loop control), a few lines of DSPy let GPT-3.5 and llama2-13b-chat self-bootstrap pipelines that beat standard few-shot prompting (generally by >25% and >65% respectively) and even beat pipelines using expert-written demonstrations. Compiled to small open models (770M-parameter T5, llama2-13b-chat), DSPy programs were competitive with expert-hand-written prompt chains running on proprietary GPT-3.5. Code: [github.com/stanfordnlp/dspy](https://github.com/stanfordnlp/dspy).

## Why it matters here

DSPy is the "compiler" counterpart to the "map" that [The Prompt Report](the-prompt-report.md) provides: the survey catalogs prompting techniques, DSPy automates *choosing and tuning* them against a metric. That programmatic, metric-driven stance aligns with [engineer the loop](../harness-engineering/engineer-the-loop.md) and the broader argument in [context engineering](../harness-engineering/context-engineering.md) that prompts should be systematically produced, not artisanally hand-crafted. It also pairs naturally with agent evaluation harnesses like [tau-bench](tau-bench.md), which supply exactly the kind of end-state metric a DSPy compiler could optimize toward.

## References

- [DSPy: Compiling Declarative Language Model Calls into Self-Improving Pipelines (arXiv:2310.03714)](https://arxiv.org/abs/2310.03714)
