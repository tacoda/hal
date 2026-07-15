# HAL — Holistic AI Learning

A personal knowledge base for learning — AI/ML first, but broad. Built to be **queried**:
you feed it sources, it turns them into linked notes, and later you ask it questions and
get cited answers, or reason with it.

HAL follows the [LLM-wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)
and is an [Open Knowledge Format (OKF) v0.1](https://cloud.google.com/blog/products/data-analytics/how-the-open-knowledge-format-can-improve-data-sharing)
bundle: just markdown files with a little YAML frontmatter. Readable in any editor,
renderable on GitHub, portable as a tarball. No runtime, no SDK.

## Structure

```
hal/
├── README.md          # this file (for humans)
├── CLAUDE.md          # the schema — how the agent reads/writes HAL
├── wiki/              # the knowledge
│   ├── index.md       # root catalog — the field folders, start here
│   ├── ai/            # a field folder: index.md hub + Concept & Reference notes
│   │   ├── index.md   # the field's survey + catalog
│   │   ├── deep-learning.md             # a Concept note
│   │   └── attention-is-all-you-need.md # a Reference note (canonical work)
│   ├── software-engineering/
│   ├── distributed-systems/
│   ├── personal-development/
│   └── …              # ~20 field folders in all
├── inbox/             # transient intake queue for local files to ingest
└── .claude/skills/    # the hal-* skills that read and write HAL
```

**Nothing is stored as an asset.** Every source is either a **URL** the note links to, or
a **local file** (image / PDF / HTML) dropped in `inbox/` that gets ingested into a note
and then **deleted**. Books and other copyrighted material are ingested and linked to the
work's website — the file is never committed. Inherently visual concepts are redrawn as
**mermaid** diagrams (GitHub renders them), not stored as images.

## How it's organized

Each note is one file. Notes link to each other with normal markdown links, so the wiki
is really a **graph** — the cross-links are the value: any idea can be reached from a
related one, including across fields.

Notes are grouped into **field folders** (`wiki/<field>/`), each with its own `index.md`
hub (a survey + catalog). Folders split HAL's applied-AI corpus (harness engineering,
agentic coding, AI platform, governance, org, business) from the broader canon (software
engineering & architecture, distributed systems, DevOps/SRE, computer science, systems
thinking, UX, personal development, and academic fields such as AI). The root
[`wiki/index.md`](wiki/index.md) is the catalog of folders.

### Note types

- **Reference** — synthesized from one external source (a URL, video, or an ingested-then-deleted local file); `source:` links the canonical work.
- **Concept** — a synthesized, college-level explanation of a canonical idea (e.g. `backpropagation`), drawn from a field rather than one source; no single `source`, cross-linked to the `Reference` works that anchor it.
- **Note** — a concrete note on how I apply a general idea already in the wiki (my workflow); no source.
- **Image** — extracted from a dropped image (then deleted); no source.
- **Index** — a folder's `index.md` hub.

## The skills

| Skill          | When                                  | What it does                                                               |
|----------------|---------------------------------------|----------------------------------------------------------------------------|
| `/hal-url`     | I paste a URL (page or video)         | Fetches/transcribes it, writes a Reference note, links the source          |
| `/hal-doc`     | A PDF / HTML / image in `inbox/`      | Ingests it into a note, links the URL (or drops it), deletes the file      |
| `/hal-note`    | An implementation note                | Concrete note on how I apply a general idea already in the wiki            |
| `/hal-query`   | A pointed question                    | Answers the fact from the wiki with citations, offers related topics       |
| `/hal-explain` | I want a concept explained            | Builds a layered explanation from the wiki with citations                  |
| `/hal-ponder`  | A hard / open / hypothetical question | Deep multi-pass reasoning across many notes, grounded and cited            |
| `/hal-propose` | I want to test an idea                | Stress-tests a proposal against HAL — support, tension, precedent, verdict |
| `/hal-quiz`    | I want to be tested                   | Quizzes me from the notes, grades against them, cites                      |
| `/hal-suggest` | What should I learn next?             | Surfaces recent / under-read notes to pull next                            |
| `/hal-output`  | I need a deliverable                  | Builds an artifact (plan, brief, roadmap…) as HTML, grounded in the wiki   |

Adding is capture; querying, reasoning, and building are retrieval. The wiki holds general
standards and ideas (from URLs and documents), synthesized field knowledge (Concept notes),
and my concrete **implementation notes** — how I apply those ideas in my own work.

## Provenance

A note ends with a `## References` link to its source **URL** when there is one (the usual
case, including books and papers linked to their website). Concept notes cite the canonical
works that anchor them. Notes built from a non-copyrighted local file have no reference —
the file was ingested and dropped. Notes that are my own thinking have no source at all.
Nothing is stored under version control except the notes themselves and a transient
`inbox/`.
