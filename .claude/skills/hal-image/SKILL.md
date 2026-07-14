---
name: hal-image
description: Ingest images into HAL — a pasted image, or a batch of images dropped in sources/inbox/. Extracts the information into an Image note under wiki/, then deletes the image (ingested images are pixelated and low-value; the extracted note is what matters) and clears the inbox. Use when the user pastes an image or asks to process the inbox. With no argument, list the inbox and confirm before processing.
---

# hal-image

Ingest image(s) into the HAL knowledge base. Read `CLAUDE.md` for the schema first.

## Two modes

- **Pasted image** — the user pasted/attached one image in the message.
- **Inbox** — the user dropped image files into `sources/inbox/` on disk. This is the
  work queue: anything sitting in `sources/inbox/` is unprocessed by definition.

Pick the mode from the request. With no pasted image and no clear instruction, run
`ls sources/inbox/`, show the pending files, and ask which to process (default: all).

## Steps (per image)

1. Get the image: read the pasted attachment, or `Read` the file from `sources/inbox/`.
2. Decide a title and kebab-case slug from its content.
3. Choose the note path: `wiki/<slug>.md` (or a topic subfolder if one fits).
4. Write the note:
   - Frontmatter: `type: Image`, `title`, `tags`, `timestamp` (today). **Omit `source`** —
     the image is not retained.
   - Body: extract everything useful from the image — text, data in tables, key points —
     as clean markdown, in your own words. Cross-link related notes.
   - **Visuals:** if the image is a diagram/flow/stack/cycle where a picture genuinely
     helps the concept, recreate it as a **mermaid** diagram (GitHub renders it) using an
     appropriate chart type (`flowchart`, `graph`, etc.). Only when it helps — for a table
     or a list of points, words are enough. Never embed the pixelated original.
   - No `## References` image embed (there is no stored file).
5. **Delete the image** — it is not stored:
   - Inbox file: `rm sources/inbox/<file>` (clears it from the queue).
   - Pasted image: nothing to delete on disk.
6. Append a pointer line to the nearest `index.md`.

## Finish

Report each note path written. For inbox runs, confirm the inbox is empty
(`ls sources/inbox/`) — every processed image should be gone.
