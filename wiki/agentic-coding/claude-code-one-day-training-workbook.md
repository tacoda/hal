---
type: Reference
title: "Claude Code One-Day Training Student Workbook (Closedloop.ai)"
tags: [claude-code, training, primitives, workflow, review, token-efficiency, harness]
timestamp: 2026-07-14
source: https://closedloop.ai
---

# Claude Code One-Day Training Student Workbook (Closedloop.ai)

A follow-along workbook for a five-hour Claude Code intensive (Closedloop.ai): a
practical operating model plus artifact templates for primitive design, planning,
investigation, review, and workflow design. Assumes setup pre-work (Claude Code working,
repo cloned) so live time is spent practicing, not repairing setup.

> **Copyright:** Closedloop.ai course material — PDF/HTML not stored here. This is a
> synthesized summary; see the source for the full workbook.

## Modules (the day's arc)

1. **Build Claude Code Primitives** — primitive design is the first skill. Interactive vs
   headless work; goal mode vs debate mode; model selection for the job; assemble a
   reusable "primitive kit." Emphasis on what-good-looks-like vs anti-patterns, then
   graduating primitives into workflows.
2. **Planning and Context Management** — the plan is a *compression artifact*; separate
   **facts, assumptions, and open questions**; build an Implementation Plan and context
   maps; run a debate review *before* coding; make plans reusable downstream.
3. **Intent Recovery and Dynamic Evidence** — find the *why* before the *what*; static
   code isn't enough; distinguish **evidence vs inference**; gather dynamic evidence;
   "that didn't work" fails as feedback; the **Request Changes** pattern.
4. **Review, Test, and Verify** — review the diff *against the plan*; watch scope drift;
   testing is one gate, not the only gate; regression risk; PR-ready handoffs; "review as
   a fleet, not a reviewer."
5. **Workflow Design and Minimal Improvement Loop** — turn good sessions into repeatable
   workflows; compact multi-agent workflows; handoffs; gates and stop conditions;
   orchestration patterns; guarding the main branch against "slop"; a lightweight retro.

## Token Savings Field Guide (cross-cutting)

Enable RTK for noisy command output; move repeated tasks to executable scripts; never say
"explore" without intention; use permission posture as a productivity lever; enable and
curate memory; share context/investigation across tasks; bound subagent output; prompt
with a token budget; run an end-of-task token checklist. Three ideas carried all day:
**give Claude better context, burn fewer tokens for more impact, land better code the
first time** (then standardize the patterns).

## Cross-links

A hands-on curriculum for the discipline in [Agent Harness Engineering](../harness-engineering/agent-harness-engineering.md)
and the [Loop Engineering Playbook](../harness-engineering/loop-engineering-playbook.md) (plan → investigate →
review → workflow, with gates and stop conditions). Primitives/commands overlap
[Claude Code Pro Tips](claude-code-pro-tips.md) and the command cheat sheets
([21](claude-code-commands-21.md) / [26](claude-code-commands-26.md)); token discipline
mirrors [CRESS](../harness-engineering/cress-context-checklist.md) (keep context small) and
[Delete 90% of Your Prompt](delete-90-percent-of-your-prompt.md).

## References

- *Claude Code One-Day Training Student Workbook*, [Closedloop.ai](https://closedloop.ai) (course material; not stored here).
