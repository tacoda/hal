# CLAUDE.md — HAL schema

HAL (Holistic AI Learning) is a knowledge base. This file is its **schema**: it tells
you how to read, write, and organize the notes. It follows the LLM-wiki pattern and is
an OKF v0.1 bundle.

## The format (OKF v0.1)

- The bundle is a directory of markdown files. **Each file is one concept.** The file
  path is the concept's identity.
- Every note has YAML frontmatter. **The only required field is `type`.** Everything
  else is optional.
- Notes link to each other with normal markdown links — that graph is the value, so
  link liberally to related notes.
- `index.md` files are catalogs for progressive disclosure. Keep them current.

## Note types

- `Reference` — synthesized from an external source: a URL (via `/hal-url`) or a local
  PDF/HTML document (via `/hal-doc`)
- `Image` — extracted from a pasted/ingested image (via `/hal-image`). The image itself
  is **not** retained — ingested images are pixelated and low-value; the extracted note is
  what matters. Omit `source` (there is no stored file).
- `Note` — a small freeform note I wrote (via `/hal-note`)
- `Index` — a catalog file (`index.md`)

## Frontmatter template

```yaml
---
type: Reference          # required
title: Attention Is All You Need
tags: [transformers, attention, nlp]
timestamp: 2026-07-14
source: https://arxiv.org/abs/1706.03762   # URL, or sources/docs/<slug>.<ext>; omit for Note/Image
---
```

Omit `source` for `Note`. Use ISO dates for `timestamp`.

## Where files go

- Notes live in `wiki/`. Filename is a kebab-case slug of the title:
  `wiki/attention-is-all-you-need.md`.
- When a topic accumulates several notes, group them in a subfolder
  (`wiki/transformers/…`) and give it its own `index.md`. Don't create subfolders
  speculatively — flat until it earns a folder.
- Stored originals: only PDF/HTML documents you own or that are freely licensed, in
  `sources/docs/<slug>.<ext>`. Never edit files under `sources/` — they are immutable.
  **Ingested images are not stored** — extract the information into the note and delete
  the image (it's pixelated and adds nothing over the note).
- **Copyright rule (applies to all books and copyrighted material):** never commit a
  copyrighted third-party document — books, papers, commercial/course PDFs — to the repo.
  Keep the synthesized note (a summary in our own words is fair use) but do **not** store
  the file: set the note's `source` to the canonical online URL and link to that URL in
  `## References`, exactly like a `/hal-url` note. Delete the inbox copy once the note is
  written. When in doubt about whether something is copyrighted, treat it as copyrighted.
- `sources/inbox/` is the shared intake queue: drop raw images, PDFs, or HTML files
  there to process later. Anything in `inbox/` is unprocessed by definition; `/hal-image`
  and `/hal-doc` clear each from the queue as they write the note — storing only
  self-owned/free documents in `sources/docs/`, and **deleting** images and copyrighted
  material after extracting/linking. An empty inbox means nothing is pending.

## Note body

1. Synthesized content in your own words — the point is a clean, queryable summary, not
   a copy of the source.
2. Cross-links to related notes where relevant.
3. **Visuals when they help.** If a concept is inherently visual — a layered stack, a
   loop/cycle, a flow, an architecture — recreate it as a **mermaid** diagram (GitHub
   renders mermaid in markdown). Pick an appropriate chart type and keep it faithful. Do
   this *only* when the picture adds understanding; for a table or a short list, words are
   enough. Never embed pixelated source images.
4. A final `## References` section linking to the source: a URL for linked/copyrighted
   material, or `../sources/docs/<slug>.<ext>` for a stored document. Image notes have no
   `## References` (nothing is stored).

## Maintaining the catalog

On every add, append a one-line pointer to the nearest `index.md`:
`- [Title](path.md) — one-line hook`. The pointer is a hook, never the content.

## Querying

Answer from the notes only. Cite every claim with a markdown link to the note it came
from (`[title](wiki/…md)`) and follow the note's `source` back to the origin when the
user wants the primary reference. After answering, offer related notes/topics — but
only expand on them if the user asks.
