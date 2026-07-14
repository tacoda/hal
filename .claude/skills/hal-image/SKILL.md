---
name: hal-image
description: Ingest images from inbox/ into HAL. Images are dropped into inbox/ on disk; this extracts each into an Image note under wiki/, then deletes the image (ingested images are pixelated and low-value — the extracted note is what matters). With no clear instruction, list the inbox and confirm before processing. Use when the user asks to process image(s) in the inbox.
---

# hal-image

Ingest image(s) from `inbox/` into the HAL knowledge base. Read `CLAUDE.md` for the
schema first. Images are processed from the **inbox only** — the user drops image files
into `inbox/`, the shared intake queue. Anything in `inbox/` is unprocessed by definition.

With no clear instruction, run `ls inbox/`, show the pending images, and ask which to
process (default: all).

## Steps (per image)

1. `Read` the image file from `inbox/`.
2. Decide a title and kebab-case slug from its content.
3. Choose the note path: `wiki/<slug>.md` (or a topic subfolder if one fits).
4. Write the note:
   - Frontmatter: `type: Image`, `title`, `tags`, `timestamp` (today). **No `source`** —
     the image is not retained.
   - Body: extract everything useful from the image — text, data in tables, key points —
     as clean markdown, in your own words. Cross-link related notes.
   - **Visuals:** if the image is a diagram/flow/stack/cycle where a picture genuinely
     helps the concept, recreate it as a **mermaid** diagram (GitHub renders it) using an
     appropriate chart type. Only when it helps — for a table or a list of points, words
     are enough. Never embed the pixelated original.
   - No `## References` section (there is no stored file and no URL).
5. **Delete the image:** `rm inbox/<file>` (clears it from the queue).
6. Append a pointer line to the nearest `index.md`.

## Finish

Report each note path written. Confirm the inbox is empty (`ls inbox/`) — every processed
image should be gone.
