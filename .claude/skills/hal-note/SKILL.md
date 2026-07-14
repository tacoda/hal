---
name: hal-note
description: Add a small freeform Note to HAL. Writes a short note under wiki/ (no external source) and updates the catalog. Use when the user has a thought or observation to capture rather than a URL or image.
---

# hal-note

Add a freeform note to the HAL knowledge base. Read `CLAUDE.md` for the schema first.

## Steps

1. Take the note text from the user.
2. Decide a title and kebab-case slug. Pick tags. If it belongs with an existing note,
   append to or cross-link that note instead of duplicating.
3. Write `wiki/<slug>.md` (or a topic subfolder if one fits):
   - Frontmatter: `type: Note`, `title`, `tags`, `timestamp` (today). No `source`.
   - Body: the note, lightly cleaned up. Cross-link related notes with markdown links.
   - Add a `## References` section only if the note cites something.
4. Append a pointer line to the nearest `index.md`.
5. Report the path written.

Keep it small. This is for quick captures, not synthesis.
