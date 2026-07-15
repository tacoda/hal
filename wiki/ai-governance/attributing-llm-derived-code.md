---
type: Reference
title: "How and Why I Attribute LLM-Derived Code (Jamie Tanna)"
tags: [ai-code-provenance, ai-assisted-development, git, licensing, workflow]
timestamp: 2026-07-14
source: https://www.jvt.me/posts/2026/02/25/llm-attribute/
---

# How and Why I Attribute LLM-Derived Code

Jamie Tanna — a self-described "cautious skeptic" of AI — documents LLM usage much
more visibly than most, down to the **commit level**. His motivation is the still-
unknown **legal risk** of AI-generated code and a former stint on Elastic's Open
Source Working Group (Engineering + Legal). This is a concrete, human-scale
practice of [AI code provenance](ai-code-provenance.md) — attribution at authorship
time, not reconstructed after the fact.

## The legal hook: indemnity requires records

GitHub **Copilot Enterprise** (only that tier) offers copyright-infringement
indemnity — but **only if you follow the terms**, which include keeping records of
which lines are LLM-derived (and possibly which models). Most code in the ecosystem
won't have that level of detail; Tanna's habit is to actually keep it.

## The mechanism: the `Co-authored-by` Git trailer

He settled on **per-commit attribution** using the long-standing `Co-authored-by`
trailer (Git forges render multiple authors, so it's visible). The trick: **put the
model name in the author-name slot and the provider in the email.** The trailer
supports many co-authors, so multiple models in one commit are all disclosed.

```
Co-authored-by: gpt-oss:20b <ollama@...>
Co-authored-by: Claude Sonnet 4.5 <jamie.tanna+github-copilot@...>
```

The first tells him it was GPT-OSS, the 20B variant, via Ollama. The second uses a
`+` email alias to tag GitHub Copilot. When it matters, he also explains *where*
LLM-derived data was used in the commit body.

### Not a generic `Co-authored-by`

He deliberately avoids the generic `Co-authored-by: Claude/Crush` trailer that
tools auto-add (whose value the Go team has debated). His is **specific and tied to
his own email** — so *he* can sign the CLA, explicitly taking on the burden of
authorship rather than diffusing it.

### Commit-level over inline comments

He used to mark LLM lines with inline code comments, but that fights the **Ship of
Theseus**: as code evolves the original lines vanish and the comments rot.
Commit-level attribution (with squash-merge on Renovate) keeps the "tainting" scoped
to the smallest unit of work and has **better longevity than PR-level** metadata,
which lives on the forge rather than in the repo.

## Why bother

- **For himself** — attention to detail; capturing metadata that may matter later.
- **A small barrier to usage** — a psychological nudge: *do I actually need an LLM
  for this?*, plus a prompt to give the generated code real thought when writing the
  message.
- **For legal-minded folks** — makes it easy to locate LLM-derived code later.
- **For reviewers** — being up front about AI usage, whatever the review-bar debate.

He remains human-in-the-loop: agents may write to files, but he commits when he's
happy and rewrites commit messages himself.

## Related

- [AI code provenance](ai-code-provenance.md) — the general principle this workflow implements.
- [Code provenance is non-negotiable in the age of AI](code-provenance-non-negotiable.md) — the cryptographic/identity side of the same concern.

## References
- [How and why I attribute LLM-derived code — Jamie Tanna](https://www.jvt.me/posts/2026/02/25/llm-attribute/)
