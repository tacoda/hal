---
name: hal-doc
description: Ingest a local PDF or HTML document into HAL — one you name, or a batch dropped in inbox/. Extracts the content into a synthesized note under wiki/, links to the source URL when there is one (always for books/papers/courses — link to the work's website), then deletes the local file. Nothing is stored. Use for a .pdf or .html/.htm file on disk. For a web URL, use hal-url; for an image, hal-image.
---

# hal-doc

Ingest local PDF/HTML document(s) into the HAL knowledge base. Read `CLAUDE.md` for the
schema first. **Nothing is stored** — every note either links to a URL or is a
notes-only extraction of a dropped local file.

## Two modes

- **Named file** — the user points at one `.pdf` / `.html` / `.htm` file on disk.
- **Inbox** — the user dropped document files into `inbox/` (the shared intake queue).
  Anything in `inbox/` is unprocessed by definition.

With no named file and no clear instruction, run `ls inbox/`, show the pending documents,
and ask which to process (default: all).

## Steps (per document)

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

Report each note path and its source URL (or "notes-only, file dropped"). For inbox runs,
confirm the inbox is empty (`ls inbox/`) — every processed document should be gone.
