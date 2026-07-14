---
name: hal-output
description: Build a requested artifact — a plan, summary, roadmap, brief, proposal, checklist, ADR, runbook, etc. — grounded in the HAL wiki as the corpus of expertise. Pulls the relevant notes (ops, development, or business), applies them to the scenario, and writes a rich, self-contained HTML page to output/ (gitignored). Always HTML — no markdown files. Use when the user asks to generate/build/draft a deliverable from what HAL knows.
---

# hal-output

Generate a deliverable **grounded in the HAL wiki**. The `wiki/` folder is the corpus of
expertise — every artifact is built by retrieving and applying the relevant notes, not from
general knowledge. Read `CLAUDE.md` for the schema first. Output goes to `output/`, which is
**gitignored** — artifacts are local and disposable, never committed.

**Every artifact is a single, rich, self-contained HTML page.** No markdown files.

## What this produces

Whatever the user asks for: a **plan, summary, roadmap, brief, proposal, checklist, ADR,
runbook, comparison, one-pager**, etc. The request names the artifact; optional additional
context describes the situation that triggered it (a repo, a decision, a goal, a problem).

## Steps

1. **Frame the artifact.** Identify: the *type*, the *audience*, the *scope*, and the
   *triggering situation* (from any context the user gave). If a genuinely blocking detail
   is missing, ask one or two quick questions — otherwise pick sensible defaults and note
   them. Don't over-consult.
2. **Retrieve from the corpus.** Decide which domain(s) the artifact draws on — **ops,
   development, business** — and pull the relevant `wiki/` notes:
   - Use `ctx_search` if the wiki is indexed; otherwise `Grep`/`Glob` over `wiki/`.
   - Read the matching notes. Follow their cross-links to gather the connected material.
   - The wiki is authoritative: **ground the artifact in what the notes actually say.**
3. **Build the artifact**, applying that knowledge to the situation. Shape it to the type:
   - *Plan* → goal, ordered steps each with a verification, risks, done-criteria.
   - *Roadmap* → phases/milestones with sequencing and dependencies.
   - *Summary* → the key points, distilled, in priority order.
   - *Proposal/brief* → problem, options, recommendation, rationale, next step.
   - *Checklist/runbook* → the concrete actions in order.
   Be specific and actionable — real steps, real trade-offs from the corpus, not filler.
4. **Render a rich, self-contained HTML page** → `output/<slug>.html`. Always HTML,
   always one file. Requirements:
   - **Self-contained:** everything inline — CSS in a `<style>` tag, any JS in a
     `<script>` tag. **No external requests, no CDN links, no web fonts, no remote images.**
     It must open correctly by double-clicking with no network.
   - **Rich, not a bare document.** Treat it as a designed page: a clear visual hierarchy,
     considered typography and spacing, a system-font stack, a restrained color palette
     with light/dark support (`prefers-color-scheme`), and layout that fits the artifact —
     a header/title block, sectioned content, and where they help: cards, callouts,
     tables, badges/pills, a timeline or phase track for roadmaps, a checklist with
     styled checkboxes, a summary/metric strip. Make it readable and responsive
     (`max-width` body, sensible margins, works on a laptop and a phone).
   - **Diagrams stay inline:** hand-write **inline SVG** or lay it out with HTML/CSS. Do
     not pull mermaid or any library from a CDN (breaks self-containment); a small amount
     of vanilla inline JS is fine if it genuinely adds value (collapsible sections, a
     filter), but the page must be fully legible with JS disabled.
   - **Print-friendly:** a light `@media print` block so it exports cleanly to PDF.
   - Keep it hand-authored and legible — no build step, no framework, no minified blobs.
5. **Cite the corpus.** End the page with a **Sources** section linking the wiki notes it
   drew on — relative links back into the repo, e.g. `<a href="../wiki/loop-engineering.md">`.
   Where the corpus is thin on something the artifact needs, say so on the page; if you
   fill a gap with general knowledge, mark it **not-from-HAL** so the reader knows what is
   and isn't grounded.
6. **Write to `output/<slug>.html`** and report the path + a one-line description. Do not
   commit it (it's gitignored by design).

## Style

- Corpus first: if HAL covers it, use HAL; cite it. General knowledge is a labeled
  fallback, not the default.
- Match the artifact to the ask — a plan is steps+verification, a roadmap is phases, a
  summary is distilled points. Don't hand back an essay when a checklist was asked for;
  shape the HTML layout to the artifact type.
- Rich means designed and readable, not decorated: whitespace and hierarchy over gradients
  and noise. Every visual element earns its place.
- Self-contained means *self-contained*: no external fonts, scripts, styles, or images.
- If notes conflict, surface the conflict on the page rather than silently picking one.
