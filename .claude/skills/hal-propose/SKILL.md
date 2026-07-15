---
name: hal-propose
description: Bounce an idea, plan, or design decision off the HAL knowledge base and analyse it — what the notes support, what they contradict, precedents, risks, and refinements, all cited. Use when the user floats a proposal and wants it stress-tested against HAL ("here's my idea…", "should we…", "what do you think of…", "poke holes in this"). To answer an open question use hal-ponder; for a pointed fact use hal-query.
---

# hal-propose

Stress-test an idea against the HAL knowledge base. Read `CLAUDE.md` for the schema first.

## Steps

1. Restate the idea in one line so the analysis is anchored. State any assumptions you're
   making; if the idea is ambiguous enough that the analysis would diverge, ask before
   proceeding.
2. Search the notes for relevant material. Use `ctx_search` if the wiki is indexed,
   otherwise `Grep`/`Glob` over `wiki/`. Read the matching notes and follow their
   cross-links.
3. Analyse the idea **against the notes**, not from general opinion. Cover:
   - **Support** — what in HAL backs the idea.
   - **Tension** — what in HAL contradicts or complicates it (this is the point; find the
     strongest objection the notes can make).
   - **Precedent** — analogous patterns/cases the notes already describe.
   - **Risks & failure modes** — what the notes say tends to go wrong here.
   - **Refinements** — concrete adjustments the notes suggest.
   Cite every point with `[note title](wiki/…md)`.
4. Give a clear **verdict** — grounded, and hedged where HAL is thin. Don't rubber-stamp.
   If you fill a gap with general knowledge, flag it as not-from-HAL.
5. After the verdict, add a short **Related** list — connected notes/topics. List them;
   do **not** expand unless the user asks a follow-up.

## Style

- Adversarial but fair: lead with the strongest objection HAL can raise, not just
  agreement. A proposal that survives a real challenge is worth more than a yes.
- If notes conflict, surface the conflict rather than picking silently.
- A verdict, not a survey. Say what you'd do and why, grounded in the notes.
- No HAL coverage for a load-bearing claim → say "not in HAL" instead of guessing.
