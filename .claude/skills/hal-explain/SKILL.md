---
name: hal-explain
description: Explain a concept from the HAL knowledge base. Builds a clear explanation from the notes with citations, then offers related notes/topics — expanding on them only if asked. Use when the user wants a concept explained ("explain X", "how does X work", "what is X"). For a pointed fact question, use hal-query instead.
---

# hal-explain

Explain a concept using the HAL knowledge base. Read `CLAUDE.md` for the schema first.

## Steps

1. Search the notes for material on the concept. Use `ctx_search` if the wiki is
   indexed, otherwise `Grep`/`Glob` over `wiki/`. Read the matching notes.
2. Build an explanation **from the notes** — definition first, then how it works, then
   why it matters. Synthesize across notes; don't just quote one.
3. Cite every claim with a markdown link to the note it came from:
   `[note title](wiki/…md)`. Follow a note's `source` field to the primary reference
   when the user wants to go deeper.
4. Where HAL is thin on the concept, say so plainly. If you fill a gap with general
   knowledge, flag it as not-from-HAL.
5. After the explanation, add a short **Related** list — connected notes/topics. List
   them; do **not** expand unless the user asks a follow-up.

## Style

- Explanation, not a fact lookup: lead with what the concept *is*, build up in layers.
- If notes conflict, surface the conflict rather than picking silently.
