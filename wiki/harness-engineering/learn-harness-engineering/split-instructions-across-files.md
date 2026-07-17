---
type: Reference
title: "Lecture 04: Split Instructions Across Files"
tags: [harness-engineering, instructions, context-rot, lost-in-the-middle]
timestamp: 2026-07-17
source: https://walkinglabs.github.io/learn-harness-engineering/en/lectures/lecture-04-why-one-giant-instruction-file-fails/
---

# Lecture 04: Split Instructions Across Files

You took harness engineering seriously, made an AGENTS.md, and packed in every rule and lesson
learned. One month → 300 lines, three months → 600. Then the agent gets *worse*: a simple bug
fix burns context on irrelevant deployment rules, a critical security constraint buried at line
300 is ignored, three contradictory style rules get picked at random. This is the **giant
instruction file trap.**

## The vicious cycle at the root

Agent makes a mistake → "add a rule to prevent this" → it works, temporarily → different
mistake → another rule → repeat until the file bloats out of control. Each "add a rule" feels
reasonable; the cumulative effect is disastrous.

## Why the single file fails

- **Context budget eaten alive** — a 200K window with a 10–20K bloated instruction file leaves
  little for the dozens of source files, tool output, and history a real task needs.
- **Lost in the middle** — the "Lost in the Middle" result (Liu et al., 2023): LLMs use
  information in the *middle* of long text far less than the start or end. Your line-300 hard
  constraint is almost certainly ignored.
- **Priority conflicts** — non-negotiable hard constraints ("never use `eval()`"), soft
  guidelines ("prefer functional style"), and one-off historical lessons all mixed together
  with no way to tell them apart.

## The fix: progressive disclosure

Split rules into small, scoped files loaded **on demand** rather than one always-on wall of
text — the right rules present when relevant, absent when not. This is
[context engineering](../context-engineering.md) applied to instructions: smallest set of
high-signal tokens for the task at hand.

Related: [Effective Context Engineering for AI Agents
(Anthropic)](../effective-context-engineering-anthropic.md), [CRESS: A Context-Quality
Checklist](../cress-context-checklist.md).

## References
- [Lecture 04: Why One Giant Instruction File Fails](https://walkinglabs.github.io/learn-harness-engineering/en/lectures/lecture-04-why-one-giant-instruction-file-fails/)
