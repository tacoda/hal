---
name: hal-ponder
description: Think deeply through a hard, open-ended, or hypothetical question using the HAL knowledge base — a deliberate, multi-pass reasoning process, not a lookup. Use for reflective/synthetic questions and thought experiments where the answer has to be worked out across many notes ("how should I think about…", "what follows from…", "what does HAL imply about…", "what if…", "suppose X — then…", "reason through…"). For a pointed fact use hal-query; to explain one concept use hal-explain; to stress-test a proposal use hal-propose.
---

# hal-ponder

Reason deeply through a question grounded in the HAL knowledge base. This is a **thinking
process** — take the time to explore, connect, and weigh before answering. Read
`CLAUDE.md` for the schema first.

## Steps

1. **Frame.** Restate the question and break it into the sub-questions it really turns on.
   Name what a good answer would have to account for.
2. **Gather — broadly, in more than one pass.** Search the notes across every angle a
   sub-question opens (`ctx_search` if indexed, else `Grep`/`Glob` over `wiki/`). Read the
   matches, then **follow their cross-links** to the next ring of notes. Do another pass as
   new terms surface. Don't stop at the first few hits — the value is in the graph, so
   pull from many notes across topics.
3. **Reason.** Work the question through *out loud*, building the argument across the notes
   rather than reporting one:
   - connect ideas from different notes into a coherent line of thought;
   - consider more than one angle, and weigh them against each other;
   - surface tensions and trade-offs the notes expose, and think through implications and
     second-order effects.
   For a **hypothetical or counterfactual** ("what if…", "suppose X"), take the premise as
   given and extrapolate from the principles in the notes — reason about what *would*
   follow. Keep the line clear between what HAL grounds and where you're extending past it;
   label the speculative leaps as speculation, not fact.
   Cite each load-bearing step with `[note title](wiki/…md)`.
4. **Land it.** Synthesize a reasoned conclusion — show *why* it follows from the notes,
   not just the verdict. Note where the reasoning is firm vs. where HAL is thin or silent.
   Flag any step filled from general knowledge as not-from-HAL.
5. Add a short **Related** list — notes/threads worth pulling next. List them; do **not**
   expand unless the user asks a follow-up.

## Style

- Depth over speed. This skill is for questions worth sitting with — show the working,
  not just the answer.
- Synthesis across many notes, not a single-note summary. Connect the dots.
- Hold competing views side by side and reason about them; surface conflict rather than
  resolving it silently.
- Grounded throughout: every step that carries weight cites a note. Where HAL runs out,
  say so plainly.
