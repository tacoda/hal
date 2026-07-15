---
type: Reference
title: "Build Your Own Coding Agent (Owen)"
tags: [agentic-coding, coding-agent, python, agent-loop, tools, testing, book]
timestamp: 2026-07-14
source: https://buildyourowncodingagent.com/
---

# Build Your Own Coding Agent (Owen)

A book by **J. Owen** (Owen Ou) — subtitled *The Zero-Magic Guide to AI Agents in Pure
Python* — that teaches you to build a production-grade terminal coding agent from
scratch. Its stance is a deliberate rebellion against framework "magic": no LangChain, no
Pydantic, just plain Python you can debug with `print()`. The tagline captures the whole
argument — an agent is **"not magic, just a while loop."**

## What you build

Over 12 chapters you build **Nanocode**, a terminal coding agent that:

- Reads, writes, and surgically edits files in a codebase.
- Executes shell commands and self-corrects from errors.
- Runs against three LLM providers — Claude, DeepSeek, and Ollama — swapping cloud and
  local models with a single command (Ollama lets you run the "brain" locally for free).

The capstone (Chapter 12) has the agent autonomously build a complete Snake game in
Pygame — writing, running, debugging, and fixing the code until it plays — without the
reader writing a line of game code.

## Notable techniques

- **The Adapter Pattern (Ch. 4)** — a thin abstraction over provider APIs that makes
  adding a new LLM trivial. This is the same instinct behind
  [model routing / gateways](../ai-platform/models.md).
- **FakeBrain test double** — a stand-in for the LLM that lets you run full `pytest`
  suites instantly, verifying agent logic without spending API credits. A concrete
  answer to the "how do you test a nondeterministic agent" problem.
- Real files, real shell commands, real error recovery, plus safety modes and persistent
  memory. Only three dependencies: `requests`, `python-dotenv`, `pytest`.

Complete per-chapter source is on GitHub (`optimalone/build-your-own-coding-agent`), each
chapter a runnable snapshot.

## Where it sits

The from-scratch, mechanistic counterpart to the conceptual guides: it makes concrete the
run-loop that [building effective agents](building-effective-agents.md) describes, and the
harness plumbing (tool contracts, verification, retries) that
[harness engineering](../harness-engineering/harness-engineering.md) treats as an
engineering discipline. Where the vendor tools in
[Claude Code: Up and Running](claude-code-book.md) hand you a finished agent, this book
has you build the loop yourself.

## References

- [Build Your Own Coding Agent](https://buildyourowncodingagent.com/)
