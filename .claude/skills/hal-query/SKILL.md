---
name: hal-query
description: Query the HAL knowledge base. Answers the user's question from the notes with citations, then offers related notes/topics — expanding on them only if asked. Use when the user asks a question rather than adding content.
---

# hal-query

Answer a question from the HAL knowledge base. Read `CLAUDE.md` for the schema first.

## Steps

1. Search the notes for relevant material. Use `ctx_search` if the wiki is indexed,
   otherwise `Grep`/`Glob` over `wiki/`. Read the matching notes.
2. Answer **only from the notes**. If HAL doesn't cover it, say so plainly — don't
   answer from general knowledge without flagging it.
3. Cite every claim with a markdown link to the note it came from:
   `[note title](wiki/…md)`. When the user wants the primary source, follow the note's
   `source` field back to the origin URL/image.
4. After the answer, add a short **Related** list — other notes or topics connected to
   the question. List them; do **not** expand unless the user asks a follow-up.

## Style

- Direct answer first, citations inline or right after.
- If notes conflict, surface the conflict rather than picking silently.
- No source in HAL for a claim → say "not in HAL" instead of guessing.
