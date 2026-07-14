---
type: Reference
title: "Context Assembly: The Window Never Overflowed, and the Agent Still Forgot"
tags: [harness-engineering, agents, context-engineering, context-window, compaction, lost-in-the-middle]
timestamp: 2026-07-14
source: https://rickhigh.substack.com/p/harness-engineering-context-assembly
---

# Context Assembly: The Window Never Overflowed, and the Agent Still Forgot

Part 4 of Rick Hightower's harness series. Its thesis: **the context window is not memory —
it is working RAM, and the harness is its memory manager.** Most agent failures get blamed
on a full window; the real culprit is quieter — nobody decided what the model should *see*
on the turn that mattered.

The story: Maria did everything right, telling a rebooking agent her Thursday deadline, a
no-Denver constraint, a United preference, and a $400 credit over six turns. On turn 14 it
recommended a Denver connection; on turn 17 it forgot the credit and quoted full fare; on
turn 20 it asked her to repeat constraints she'd given twenty minutes earlier. The detail
that matters: **the window never overflowed** — the token count sat comfortably under the
limit the whole time. It wasn't a model defect or bad luck; it's what happens when nothing
in the harness protects the facts that matter.

## Remember vs. see

There's a distinction hiding in the failure. One job is what the agent *remembers* — the
durable store of everything it's been told (see [the memory-tiers note](hightower-allergy-vector-store.md)).
A different job is what the agent *sees* — the slice of that store that actually reaches the
model on a given call. Conflating them gives you an agent with a perfect memory store and
amnesia at the moment of decision. Context assembly is the second job: **assembling the
model's working memory deliberately on every single call.**

## Four levers of context window management

The essay frames context management as four levers — **select, compress, isolate, write** —
and builds three of them in both the Claude Agent SDK and LangChain Deep Agents.

- **Select — keep the noise out.** "The cheapest token is the one you never admit." The most
  common self-inflicted bloat is loading every tool definition up front: ~50 MCP tool
  schemas run roughly **72,000 tokens** before any work happens, while on-demand discovery
  of the same tools costs about **8,700 tokens — a 95% cut** in that one component. In the
  Claude Agent SDK on-demand discovery is the default, so the win is mostly not undoing it:
  keep the tool surface lean, restrict which config sources load, and return narrow
  projections from tools instead of dumping raw payloads.
- **Compress** — summarize/compact a near-full window so older turns don't crowd out the
  facts that matter.
- **Isolate** — give heavy work its own clean window (e.g., subagents) and hand back only a
  distilled result.
- **Write** — offload notes and state to disk so the live window stays lean.

## Why order matters

Assembly is not just *what* to include but *where*. The literature the series leans on —
*Lost in the Middle* (TACL 2024) and the *U-shaped attention* finding — shows information
buried mid-prompt is reliably under-attended relative to the beginning and end. Selection
without ordering still lets critical facts get lost. And the essay is explicit that there's
one judgment no framework can make for you: deciding what the model must see on the turn
that matters.

## Related notes

- [The naked agent (Hightower)](hightower-the-naked-agent.md) — Part 1; this closes its Failure 2 (silent context rot).
- [The allergy in the vector store (Hightower)](hightower-allergy-vector-store.md) — Part 3; the *remember* half to this *see* half.
- [Context engineering](context-engineering.md) and [Effective context engineering (Anthropic)](effective-context-engineering-anthropic.md) — compaction, progressive disclosure, subagent isolation.
- [What Is Harness Engineering? (Hightower)](hightower-what-is-harness-engineering.md) — context rot, context panic, lost-in-the-middle as named failure modes.
- [Claude context management](claude-context-management.md), [CRESS context checklist](cress-context-checklist.md) — applied context tooling.

## References

- [Context Assembly: The Window Never Overflowed, and the Agent Still Forgot](https://rickhigh.substack.com/p/harness-engineering-context-assembly) — Rick Hightower
