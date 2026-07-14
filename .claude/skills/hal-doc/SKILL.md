---
name: hal-doc
description: Ingest local PDF or HTML document files into HAL — a single file you name, or a batch dropped in sources/inbox/. Stores each original under sources/docs/, synthesizes a Reference note under wiki/, links the stored file, and clears the inbox. Use for a .pdf or .html/.htm file on disk. For a web URL, use hal-url instead; for an image, hal-image.
---

# hal-doc

Ingest local PDF/HTML document(s) into the HAL knowledge base. Read `CLAUDE.md` for
the schema first.

## Two modes

- **Named file** — the user points at one `.pdf` / `.html` / `.htm` file on disk.
- **Inbox** — the user dropped document files into `sources/inbox/` (the shared intake
  queue). Anything in `sources/inbox/` is unprocessed by definition.

Pick the mode from the request. With no named file and no clear instruction, run
`ls sources/inbox/`, show the pending documents, and ask which to process (default: all).

## Steps (per document)

1. Read the content:
   - PDF: `Read` the file with the `pages` param (required for PDFs over 10 pages;
     max 20 pages per call — page through longer files).
   - HTML: `ctx_execute_file` to strip tags to text (keeps raw markup out of context);
     fall back to `Read`.
2. Decide a title and kebab-case slug from the content. Pick tags. Check `wiki/` for an
   existing note on the same topic — if one exists, update it instead of duplicating,
   and cross-link.
3. **Decide whether the document may be stored.** If it is a book, paper, or other
   copyrighted third-party work (see the copyright rule in `CLAUDE.md`), do **not** store
   it — find its canonical online URL (arXiv abstract page, publisher page, course page,
   etc.), and `rm sources/inbox/<file>` to clear it from the queue. When in doubt, treat
   it as copyrighted. Only documents you own or that are freely licensed get stored:
   - Inbox file: `git mv sources/inbox/<file> sources/docs/<slug>.<ext>` (also clears it).
   - Named file elsewhere on disk: `cp` it to that path. (`sources/` is immutable.)
4. Choose the note path: `wiki/<slug>.md` (or a topic subfolder if one already holds
   related notes).
5. Write the note:
   - Frontmatter: `type: Reference`, `title`, `tags`, `timestamp` (today), and `source`:
     the canonical URL for copyrighted/linked docs, or `sources/docs/<slug>.<ext>` for a
     stored one.
   - Body: a clean synthesis **in your own words** — key ideas, definitions, takeaways.
     Not a transcript. Cross-link related notes with markdown links.
   - End with a `## References` link: the canonical URL for copyrighted/linked docs, or
     `[<title>](../sources/docs/<slug>.<ext>)` for a stored one (adjust the relative path
     to the note's depth).
6. Append a pointer line to the nearest `index.md`:
   `- [Title](slug.md) — one-line hook`.

## Finish

Report each note path and stored document path. For inbox runs, confirm the inbox is
empty (`ls sources/inbox/`) — every processed document should have moved out.
