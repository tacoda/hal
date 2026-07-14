# HAL — Holistic AI Learning

A personal knowledge base for learning AI/ML. Built to be **queried**: you feed it
sources, it turns them into linked notes, and later you ask it questions and get
cited answers.

HAL follows the [LLM-wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
and is an [Open Knowledge Format (OKF) v0.1](https://cloud.google.com/blog/products/data-analytics/how-the-open-knowledge-format-can-improve-data-sharing)
bundle: just markdown files with a little YAML frontmatter. Readable in any editor,
renderable on GitHub, portable as a tarball. No runtime, no SDK.

## Structure

```
hal/
├── README.md          # this file (for humans)
├── CLAUDE.md          # the schema — how the agent reads/writes HAL
├── index.md           # OKF root catalog — start here to browse
├── wiki/              # the knowledge: one markdown note per concept
│   └── index.md       # catalog of notes
└── inbox/             # transient intake queue for local files to ingest
```

**Nothing is stored as an asset.** Every source is either a **URL** the note links to, or
a **local file** (image / PDF / HTML) dropped in `inbox/` that gets ingested into a note
and then **deleted**. Books and other copyrighted material are ingested and linked to the
work's website — the file is never committed. Inherently visual concepts are redrawn as
**mermaid** diagrams (GitHub renders them), not stored as images.

Every note is one file. Notes link to each other with normal markdown links, so the
folder is really a graph. Topics are just tags and (when they grow) subfolders under
`wiki/`.

## How I use it

| Skill          | When                          | What it does                                                          |
|----------------|-------------------------------|-----------------------------------------------------------------------|
| `/hal-url`     | I paste a URL                 | Fetches it, writes a note, links the source; mermaid where it helps   |
| `/hal-doc`     | A PDF/HTML in `inbox/`         | Ingests it into a note, links the URL (or drops it), deletes the file |
| `/hal-image`   | I paste / drop an image       | Extracts the info into a note, then drops the image                   |
| `/hal-note`    | An implementation note         | Concrete note on how I apply a general idea already in the wiki       |
| `/hal-query`   | I have a pointed question      | Answers the fact from the wiki with citations, offers related topics  |
| `/hal-explain` | I want a concept explained     | Builds a layered explanation from the wiki with citations             |

Adding is capture; querying is retrieval. The wiki holds general standards and ideas
(from URLs and documents) plus my concrete **implementation notes** — how I apply those
ideas in my own workflow and work style.

## Provenance

A note ends with a `## References` link to its source **URL** when there is one (the usual
case, including books and papers linked to their website). Notes built from a
non-copyrighted local file have no reference — the file was ingested and dropped. Notes
that are my own thinking have no source at all. Nothing is stored under version control
except the notes themselves and a transient `inbox/`.
