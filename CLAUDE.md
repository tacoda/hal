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
  PDF/HTML we ingest then delete (via `/hal-doc`). `source` is the canonical URL whenever
  there is one — which is almost always, including books and papers (link to the work's
  website). Omit `source` only for a non-copyrighted local file that has no URL.
- `Image` — extracted from an image dropped in `inbox/` (via `/hal-image`). The image is
  dropped after extraction (pixelated, low-value; the note is what matters). No `source`.
- `Note` — a concrete note on how I implement the general standards and ideas already in
  the wiki: my applied workflow and work style, made specific (via `/hal-note`). No
  `source`; cross-link to the general note(s) it puts into practice.
- `Index` — a catalog file (`index.md`)

## Frontmatter template

```yaml
---
type: Reference          # required
title: Attention Is All You Need
tags: [transformers, attention, nlp]
timestamp: 2026-07-14
source: https://arxiv.org/abs/1706.03762   # canonical URL; omit only for Note, Image, or a non-copyrighted local file with no URL
---
```

Use ISO dates for `timestamp`.

## Where files go

- Notes live in `wiki/`. Filename is a kebab-case slug of the title:
  `wiki/attention-is-all-you-need.md`.
- When a topic accumulates several notes, group them in a subfolder
  (`wiki/transformers/…`) and give it its own `index.md`. Don't create subfolders
  speculatively — flat until it earns a folder.
- **Nothing is stored permanently — there is no asset store.** Every source is one of:
  - **A URL** (the standard case). Link to it; `source:` is the URL. This covers web pages
    (`/hal-url`) *and* all copyrighted material — books, papers, courses: ingest the
    content into a note, remove any inbox file, and link to the work's website. Never
    commit a copyrighted file. When in doubt about copyright, treat it as copyrighted.
  - **A non-copyrighted local file** — image, PDF, or HTML dropped in `inbox/`, with no
    URL. Ingest the content into the note, then **delete** the file; omit `source`.
- `inbox/` (top level) is the intake queue for local files: drop images, PDFs, or HTML
  there to process later. Anything in `inbox/` is unprocessed by definition; `/hal-image`
  and `/hal-doc` clear each as they write the note — dropping non-copyrighted files, and
  linking-then-dropping copyrighted ones. An empty inbox means nothing is pending.

## Note body

1. Synthesized content in your own words — the point is a clean, queryable summary, not
   a copy of the source.
2. Cross-links to related notes where relevant.
3. **Visuals when they help.** If a concept is inherently visual — a layered stack, a
   loop/cycle, a flow, an architecture — recreate it as a **mermaid** diagram (GitHub
   renders mermaid in markdown). Pick an appropriate chart type and keep it faithful. Do
   this *only* when the picture adds understanding; for a table or a short list, words are
   enough. Never embed pixelated source images.
4. A final `## References` section linking to the source URL. A note built from a
   dropped local file with no URL has no `## References` (nothing is stored, no link).

## Maintaining the catalog

On every add, append a one-line pointer to the nearest `index.md`:
`- [Title](path.md) — one-line hook`. The pointer is a hook, never the content.

## Querying

Answer from the notes only. Cite every claim with a markdown link to the note it came
from (`[title](wiki/…md)`) and follow the note's `source` back to the origin when the
user wants the primary reference. After answering, offer related notes/topics — but
only expand on them if the user asks.
