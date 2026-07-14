---
name: hal-output
description: Build a requested artifact — a plan, summary, roadmap, brief, proposal, checklist, ADR, runbook, etc. — grounded in the HAL wiki as the corpus of expertise. Pulls the relevant notes (ops, development, or business), applies them to the scenario, and writes the artifact to output/ (gitignored). Markdown by default; a self-contained HTML page when a standalone rendered artifact fits. Use when the user asks to generate/build/draft a deliverable from what HAL knows.
---

# hal-output

Generate a deliverable **grounded in the HAL wiki**. The `wiki/` folder is the corpus of
expertise — every artifact is built by retrieving and applying the relevant notes, not from
general knowledge. Read `CLAUDE.md` for the schema first. Output goes to `output/`, which is
**gitignored** — artifacts are local and disposable, never committed.

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
4. **Choose the format:**
   - **Markdown** (default) → `output/<slug>.md`. Right for plans, summaries, briefs, docs.
   - **Self-contained HTML** → `output/<slug>.html` when a standalone rendered page is
     wanted (a visual roadmap, dashboard, shareable one-pager). **One file, everything
     inline** — CSS in a `<style>` tag, any JS in a `<script>` tag, no external requests,
     no CDN links. It must open correctly by double-clicking with no network.
5. **Cite the corpus.** End the artifact with a short **Sources** list linking the wiki
   notes it drew on (`[title](../wiki/…md)` from `output/`). Where the corpus is thin on
   something the artifact needs, say so plainly; if you fill a gap with general knowledge,
   flag it as **not-from-HAL** so the reader knows what is and isn't grounded.
6. **Write to `output/`** and report the path + a one-line description of what was built.
   Do not commit it (it's gitignored by design).

## Style

- Corpus first: if HAL covers it, use HAL; cite it. General knowledge is a labeled
  fallback, not the default.
- Match the artifact to the ask — a plan is steps+verification, a roadmap is phases, a
  summary is distilled points. Don't hand back an essay when a checklist was asked for.
- Self-contained HTML means *self-contained*: no external fonts, scripts, or styles.
- If notes conflict, surface the conflict rather than silently picking one.
