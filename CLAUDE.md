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

- `Reference` — synthesized from an external URL (via `/hal-url`)
- `Image` — extracted from a pasted image (via `/hal-image`)
- `Note` — a small freeform note I wrote (via `/hal-note`)
- `Index` — a catalog file (`index.md`)

## Frontmatter template

```yaml
---
type: Reference          # required
title: Attention Is All You Need
tags: [transformers, attention, nlp]
timestamp: 2026-07-14
source: https://arxiv.org/abs/1706.03762   # URL, or sources/images/<slug>.png
---
```

Omit `source` for `Note`. Use ISO dates for `timestamp`.

## Where files go

- Notes live in `wiki/`. Filename is a kebab-case slug of the title:
  `wiki/attention-is-all-you-need.md`.
- When a topic accumulates several notes, group them in a subfolder
  (`wiki/transformers/…`) and give it its own `index.md`. Don't create subfolders
  speculatively — flat until it earns a folder.
- Stored images go in `sources/images/<slug>.png`. Never edit files under `sources/` —
  they are the immutable originals.

## Note body

1. Synthesized content in your own words — the point is a clean, queryable summary, not
   a copy of the source.
2. Cross-links to related notes where relevant.
3. A final `## References` section linking to the source (URL) or the stored image path.

## Maintaining the catalog

On every add, append a one-line pointer to the nearest `index.md`:
`- [Title](path.md) — one-line hook`. The pointer is a hook, never the content.

## Querying

Answer from the notes only. Cite every claim with a markdown link to the note it came
from (`[title](wiki/…md)`) and follow the note's `source` back to the origin when the
user wants the primary reference. After answering, offer related notes/topics — but
only expand on them if the user asks.
