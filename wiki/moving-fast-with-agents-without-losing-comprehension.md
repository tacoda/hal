---
type: Reference
title: Moving Fast With Agents Without Losing Comprehension
tags: [ai-assisted-development, comprehension-debt, agents, code-review, workflow]
timestamp: 2026-07-14
source: https://alexocallaghan.com/moving-fast-with-agents-without-losing-comprehension
---

# Moving Fast With Agents Without Losing Comprehension

Alex O'Callaghan's observation: nearly all guidance about working with agents
optimizes for **agent** comprehension — context files, MCP servers, documented
skills, feeding the model the right information so it can reason about your
codebase. Almost none of it asks whether the **humans** still understand the
system the agent is changing.

## The asymmetry

We pour effort into making the agent understand the code while human
understanding quietly erodes. AI generates code far faster than humans can
evaluate it, and that gap "hollows out the team's understanding of their own
codebase" — this is exactly Addy Osmani's
[comprehension debt](comprehension-debt-osmani.md). The point of the piece is
that you can't fix the gap by feeding the agent more context; you have to build
practices that keep *human* comprehension intact **before** you let velocity
climb.

## The stance

Speed with agents is fine — desirable, even — but only once the scaffolding that
preserves understanding is in place. Moving fast is a *consequence* of that
scaffolding, not a substitute for it. Without it, the codebase accumulates code
no one on the team actually understands, and the understanding that keeps a
codebase healthy walks out the door with every merge.

## Related

- [Comprehension Debt (Osmani)](comprehension-debt-osmani.md) — the original
  framing of the human-understanding gap this responds to.
- [Comprehension Debt](comprehension-debt.md) — the broader synthesis.
- [Ironies of Automation](ironies-of-automation.md) — why supervising code you
  didn't write is the hard case.

## References
- [Moving fast with agents without losing comprehension — Alex O'Callaghan](https://alexocallaghan.com/moving-fast-with-agents-without-losing-comprehension)
