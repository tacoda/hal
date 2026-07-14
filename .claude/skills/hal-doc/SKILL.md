---
name: hal-doc
description: Ingest a local file into HAL — a PDF, HTML, or image — one you name, or a batch dropped in inbox/. Branches on type: images (jpg/jpeg/png/gif/webp) are extracted to an Image note then dropped; documents (pdf/html/htm) are synthesized into a Reference note linked to their source URL then dropped. Nothing is stored. For a web URL or video, use hal-url instead.
---

# hal-doc

Ingest local file(s) — PDF, HTML, or image — into the HAL knowledge base. Read
`CLAUDE.md` for the schema first. **Nothing is stored** — every note either links to a
URL or is a notes-only extraction of a dropped local file, and the file is removed after.

## Two modes

- **Named file** — the user points at one file on disk.
- **Inbox** — the user dropped files into `inbox/` (the shared intake queue). Anything in
  `inbox/` is unprocessed by definition.

With no named file and no clear instruction, run `ls inbox/`, show the pending files, and
ask which to process (default: all).

## Branch on file type

Check the extension and route each file:

- **Image** — `.jpg` / `.jpeg` / `.png` / `.gif` / `.webp` → **Image path** (extract, no
  source, drop the file; the pixels are low-value, the note is what matters).
- **Document** — `.pdf` / `.html` / `.htm` → **Document path** (synthesize, link to the
  source URL, drop the file). A PDF is a document even if it looks scanned.

---

## Image path (per image)

1. `Read` the image file.
2. Decide a title and kebab-case slug from its content; pick tags.
3. Choose the note path: `wiki/<slug>.md` (or a topic subfolder if one fits). Check `wiki/`
   for an existing note on the same topic — update instead of duplicating, and cross-link.
4. Write the note:
   - Frontmatter: `type: Image`, `title`, `tags`, `timestamp` (today). **No `source`** —
     the image is not retained.
   - Body: extract everything useful — text, table data, key points — as clean markdown,
     in your own words. Cross-link related notes.
   - **Visuals:** if the image is a diagram/flow/stack/cycle where a picture genuinely
     helps, recreate it as a **mermaid** diagram (appropriate chart type). Only when it
     helps — for a table or list of points, words are enough. Never embed the pixelated
     original.
   - No `## References` section (no stored file, no URL).
5. **Delete the image:** `rm inbox/<file>` (or, for a named file elsewhere, leave the
   user's own file where it is — just don't copy it into the repo).
6. Append a pointer line to the nearest `index.md`.

## Document path (per document)

1. Read the content:
   - PDF: `Read` with the `pages` param (required over 10 pages; max 20/call — page
     through longer files). If page rendering is unavailable, extract text in a sandbox
     (e.g. `pypdf`) instead of reading raw bytes into context.
   - HTML: `ctx_execute_file` to strip tags to text (keeps markup out of context); fall
     back to `Read`.
2. Decide a title, kebab-case slug, and tags. Check `wiki/` for an existing note on the
   same topic — update it instead of duplicating, and cross-link.
3. Determine the `source`:
   - **Book / paper / course / any copyrighted work, or anything with a canonical URL:**
     find that URL (publisher/book website, arXiv abstract page, course page, …). The note
     links to it; the file is **not** kept.
   - **Non-copyrighted local file with no URL:** omit `source`. When in doubt about
     copyright, treat it as copyrighted and find its website.
4. Choose the note path: `wiki/<slug>.md` (or a topic subfolder if one already holds
   related notes).
5. Write the note:
   - Frontmatter: `type: Reference`, `title`, `tags`, `timestamp` (today), and `source`
     (the canonical URL, or omitted if a non-copyrighted local file with no URL).
   - Body: a clean synthesis **in your own words** — key ideas, definitions, takeaways.
     Not a transcript. Cross-link related notes.
   - **Visuals:** if the document explains an inherently visual concept — a layered stack,
     a loop/cycle, a flow, an architecture — recreate it as a **mermaid** diagram (GitHub
     renders it) with an appropriate chart type. Only when it aids understanding; for
     prose, tables, or lists, words are enough.
   - `## References`: link to the `source` URL. Omit the section entirely if there is no
     URL (dropped local file).
6. **Remove the local file** — nothing is stored:
   - Inbox file: `rm inbox/<file>`. (Same for books/copyrighted PDFs: ingest, then remove
     and link.)
   - Named file elsewhere on disk: leave the user's own file where it is; just don't copy
     it into the repo.
7. Append a pointer line to the nearest `index.md`.

## Finish

Report each note path and, for documents, its source URL (or "notes-only, file dropped").
For inbox runs, confirm the inbox is empty (`ls inbox/`) — every processed file should be
gone.
