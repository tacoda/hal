---
type: Reference
title: "LLM: Simon Willison's CLI and Python Library for Language Models"
tags: [llm, cli, tooling, structured-output, tool-use, embeddings, simon-willison]
timestamp: 2026-07-14
source: https://llm.datasette.io/
---

# LLM: Simon Willison's CLI and Python Library for Language Models

`llm` is a command-line tool and Python library, built by Simon Willison, for talking
to language models. It treats "run a prompt against a model" as a Unix primitive: read
from stdin, write to stdout, pipe it into anything. One interface fronts OpenAI,
Anthropic Claude, Google Gemini, Meta Llama, and dozens of others — remote APIs and
local models alike — so you can swap models without changing your workflow.

## What it does

- **Run prompts from the shell.** `llm "Ten fun names for a pet pelican"` hits the
  default model. Pipe a file in for context: `cat myfile.py | llm -s "Explain this code"`.
- **Model-agnostic via plugins.** Providers are plugins: `llm install llm-anthropic`,
  `llm install llm-gemini`, `llm install llm-ollama` for local models. `-m` picks the
  model (`llm -m claude-4-opus "…"`); aliases give short names.
- **Log everything to SQLite.** Every prompt and response is stored automatically, so
  your whole history is a queryable database — the backbone for later analysis and for
  building datasets.
- **Structured output via schemas.** Extract typed JSON from text or images with a
  schema — either full JSON Schema or Willison's terse shorthand (`name, age int, bio`).
  Logged JSON objects can be browsed back out of the SQLite store. This is the CLI
  counterpart to the [structured-output guardrails](eugene-yan-llm-patterns.md) other
  practitioners rely on for machine-readable output.
- **Tool use.** Grant a model the ability to call functions/tools; ships with default
  tools and hooks for writing your own.
- **Embeddings.** Generate and store embeddings, enabling semantic search and
  similarity from the command line — useful for RAG-style retrieval.
- **Templates and fragments.** Save reusable system prompts, options, schemas, and
  tools as named templates (YAML files); pull in long context as reusable "fragments."
- **Attachments and multimodal.** Feed images, audio, and video as attachments
  (`llm "extract text" -a scanned-document.jpg`).
- **Interactive chat.** `llm chat -m gpt-4.1` opens a REPL with multiline input,
  editor integration, and fragment insertion.

## Why it matters

The design philosophy is composability: because prompts are shell commands with
SQLite logging underneath, LLM slips into scripts, pipes, and cron jobs the way `grep`
or `jq` do. That makes it a practical substrate for the evaluation and observability
loops described in [Hamel Husain's evals work](your-ai-product-needs-evals.md) — you can
capture traces, build datasets, and script assertions without adopting a heavier
framework. Its plugin architecture keeps it provider-neutral, echoing the "instrument/
build once, choose the vendor later" stance in [harness engineering](bockeler-harness-engineering.md).

## References

- [LLM documentation](https://llm.datasette.io/)
