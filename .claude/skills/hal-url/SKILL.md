---
name: hal-url
description: Ingest a URL into HAL. Fetches the page, writes a synthesized Reference note under wiki/ with a source link at the bottom, and updates the catalog. Use when the user pastes or names a URL to save.
---

# hal-url

Ingest a URL into the HAL knowledge base. Read `CLAUDE.md` for the schema first.

## Steps

1. Take the URL from the user's message.
2. Fetch and read the content. Prefer `ctx_fetch_and_index` (keeps raw bytes out of
   context); fall back to `WebFetch`.
3. Decide the title and a kebab-case slug. Pick tags. Check `wiki/` for an existing
   note on the same topic — if one exists, update it instead of creating a duplicate,
   and cross-link.
4. Choose the path: `wiki/<slug>.md`, or `wiki/<topic>/<slug>.md` if a topic folder
   already holds related notes.
5. Write the note:
   - Frontmatter: `type: Reference`, `title`, `tags`, `timestamp` (today), `source`
     (the URL).
   - Body: a clean synthesis **in your own words** — key ideas, definitions, takeaways.
     Not a transcript. Cross-link related notes with markdown links.
   - **Visuals:** if the page explains an inherently visual concept — a layered stack, a
     loop/cycle, a flow, an architecture — recreate it as a **mermaid** diagram (GitHub
     renders it) with an appropriate chart type. Only when it aids understanding; for
     prose, tables, or lists, words are enough.
   - End with:
     ```
     ## References
     - [<page title>](<url>)
     ```
6. Append a pointer line to the nearest `index.md`:
   `- [Title](slug.md) — one-line hook`.
7. Report the path written and a one-line summary.
