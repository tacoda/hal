---
name: hal-image
description: Ingest images into HAL — a pasted image, or a batch of images dropped in sources/inbox/. Stores each as a PNG under sources/images/, extracts the information into an Image note under wiki/, links the stored PNG, and clears the inbox. Use when the user pastes an image or asks to process the inbox. With no argument, list the inbox and confirm before processing.
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

1. Get the image: read the pasted attachment, or `Read` the file from
   `sources/inbox/`.
2. Decide a title and kebab-case slug from its content.
3. Store the original PNG at `sources/images/<slug>.png` (immutable — never edited
   later):
   - Inbox file: `git mv sources/inbox/<file> sources/images/<slug>.png` (converts the
     name; keep the bytes). This also clears it from the queue.
   - Pasted image: if the harness gives a file path, copy it there; otherwise ask the
     user to save it to that exact path.
4. Choose the note path: `wiki/<slug>.md` (or a topic subfolder if one fits).
5. Write the note:
   - Frontmatter: `type: Image`, `title`, `tags`, `timestamp` (today),
     `source: sources/images/<slug>.png`.
   - Body: extract everything useful from the image — text, diagrams described,
     data in tables, key points — as clean markdown. Cross-link related notes.
   - End with:
     ```
     ## References
     - ![<title>](../sources/images/<slug>.png)
     ```
     (adjust the relative path to the note's depth).
6. Append a pointer line to the nearest `index.md`.

## Finish

Report each note path and stored image path. For inbox runs, confirm the inbox is
empty (`ls sources/inbox/`) — every processed image should have moved out.
