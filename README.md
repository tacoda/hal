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
└── sources/
    ├── inbox/         # drop raw images here to process later (the intake queue)
    └── images/        # immutable original PNGs referenced by notes
```

Bulk images: drop files into `sources/inbox/` and run `/hal-image` — it lists what's
pending, processes each into a note, and moves it to `sources/images/`. An empty inbox
means nothing is waiting.

Every note is one file. Notes link to each other with normal markdown links, so the
folder is really a graph. Topics are just tags and (when they grow) subfolders under
`wiki/`.

## How I use it

Four skills, matching how I work:

| Skill        | When                          | What it does                                                        |
|--------------|-------------------------------|---------------------------------------------------------------------|
| `/hal-url`   | I paste a URL                 | Fetches it, writes a note, links the source at the bottom           |
| `/hal-image` | I paste an image              | Stores the PNG in `sources/images/`, extracts info into a note      |
| `/hal-note`  | I have a small note to add    | Writes a short freeform note                                        |
| `/hal-query`   | I have a pointed question   | Answers the fact from the wiki with citations, offers related topics |
| `/hal-explain` | I want a concept explained  | Builds a layered explanation from the wiki with citations           |

Adding is capture; querying is retrieval. Most entries are references; some are notes.

## Provenance

Every note ends with a `## References` section linking back to where it came from —
a URL or a stored image. Sources under `sources/` are immutable; notes are the
synthesized layer the agent maintains.
