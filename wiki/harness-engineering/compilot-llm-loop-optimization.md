---
type: Reference
title: "Agentic Auto-Scheduling: LLM-Guided Loop Optimization (COMPILOT)"
tags: [compilers, llm, loop-optimization, agents, generator-evaluator, polyhedral]
timestamp: 2026-07-14
source: https://arxiv.org/abs/2511.00592
---

# Agentic Auto-Scheduling: LLM-Guided Loop Optimization (COMPILOT)

A PACT 2025 experimental study (Merouani, Kara Bernou, Baghdadi — NYU Abu Dhabi) asking:
**can off-the-shelf LLMs, grounded by empirical compiler feedback, guide complex loop
optimization?** Answer: yes.

## The framework

**COMPILOT** casts an off-the-shelf LLM (no fine-tuning) as an optimization agent in a
closed loop with the **Tiramisu** polyhedral compiler:

1. *Context initialization* — a constant system prompt defines the role, input/output
   format, the transformation repertoire, and hardware target; the target loop nest is
   presented (anonymized, comp-ID-annotated) with its baseline runtime; the LLM first
   **analyzes** the nest (chain-of-thought).
2. *Iterative optimization* — the LLM proposes a schedule (sequence of transformations
   in `<schedule>` tags with reasoning). A **two-stage correctness check** follows: a
   lightweight validity pre-filter, then the compiler's formal **polyhedral dependence
   analysis** for legality. Legal schedules are compiled, run, and the measured
   speedup/slowdown (or failure category) is fed back. The LLM refines via in-context
   learning — no fine-tuning, no gradient updates.

Nine transformation primitives: fusion, shifting, interchange, parallelization, 2D/3D
tiling, unrolling, skewing, reversal. **Core design principle — delegation:** the LLM
does high-level strategic exploration; the compiler owns formal correctness and code
generation.

## Results (PolyBench, 150 instances, gemini-2.0-flash)

- Geometric mean **2.66× single-run**, **3.54× best-of-5** over original code; **2.94×
  over Pluto** (SOTA polyhedral optimizer), winning 119/150 instances. Some >100×
  (correlation_XLARGE 339×, trmm_XLARGE 183×).
- Only ~36% of proposed schedules are runnable (~31% invalid, ~32% illegal) — two-thirds
  are unproductive; illegal rate starts ~60% and falls as the LLM learns from feedback.
- ~8.9 min/instance; ~78.5% of wall-clock is the compiler, not the LLM.

## Key ablations

- **Feedback matters:** removing it costs 23–40% of the speedup — the loop's value is the
  grounding, not the model.
- **Delegating codegen to the compiler beats direct code generation:** direct gen was
  14–16% slower, ~5.3× more tokens, and 17.9% of its "provisionally legal" (output-match)
  schedules were actually illegal under random inputs — output comparison can't guarantee
  correctness; formal legality checking can.
- Hardware details in the prompt: no significant effect (the feedback loop dominates).
- Chain-of-thought (initial analysis + per-step reasoning): consistent ~8–14% benefit.
- Reasoning-specialized and coding-specialized models did *not* consistently beat top
  general models; a baseline of instruction-following / structured output is what matters.

## Cross-links

A concrete, measured instance of the **generator/evaluator** pattern in the
[Loop Engineering Playbook](loop-engineering-playbook.md) and the **verification layer**
of [Agent Harness Engineering](agent-harness-engineering.md): the compiler is the
deterministic checker that *acts* (compiles, runs, measures) rather than judging by
inspection — exactly the "assume broken, verify by acting" evaluator. The feedback loop
is likened to RAG. Echoes [Engineer the Loop, Not the Prompt](engineer-the-loop.md)
(act → verify → refine until done).

## References

- [Agentic Auto-Scheduling: LLM-Guided Loop Optimization (arXiv 2511.00592)](https://arxiv.org/abs/2511.00592)
