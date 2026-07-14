---
name: hal-note
description: Capture a concrete note about how I implement the general standards and ideas already in the wiki — my applied workflow and work style, made into a concrete example. Writes a note under wiki/ with no source, cross-linked to the general note(s) it puts into practice, and updates the catalog. Use for implementation notes, not for external URLs, images, or documents.
---

# hal-note

Capture an implementation note in HAL. These are **not** freeform musings: each note takes
a general standard or idea that already lives in the wiki and turns it into a concrete
example of how I actually apply it — my preferred workflow and work style. There is **no
`source`** (it's my own thinking). Read `CLAUDE.md` for the schema first.

## Steps

1. Take the note from the user.
2. Decide a title, kebab-case slug, and tags. Identify the general standard/idea note(s)
   in the wiki this note implements — **cross-link to them** (or append to an existing
   note instead of duplicating when it fits).
3. Write `wiki/<slug>.md` (or a topic subfolder if one fits):
   - Frontmatter: `type: Note`, `title`, `tags`, `timestamp` (today). No `source`.
   - Body: the concrete implementation — how the general idea gets applied in practice, in
     my voice. Cross-link the general note(s) it puts into practice.
   - **Visuals:** if the workflow is inherently visual (a flow, a cycle, a small
     structure), a short **mermaid** diagram can capture it (GitHub renders it) — only if
     it helps.
   - Add a `## References` section only if the note cites something.
4. Append a pointer line to the nearest `index.md`.
5. Report the path written.

Keep it concrete: a general principle made specific to how I work, tied back to the wiki
note it implements.
