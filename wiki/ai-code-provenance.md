---
type: Reference
title: AI-Code Provenance
tags: [ai-assisted-development, provenance, attribution, git, compliance, metrics, quality]
timestamp: 2026-07-14
source: https://tessl.io/patterns/quality-security/ai-code-provenance/
---

# AI-Code Provenance

**Recording what produced a change** — which agent, model, prompt, or spec — and
keeping that record **attached to the code**, so review, metrics, and compliance
can treat agent-authored work differently from hand-written work. *Tag commits,
PRs, or regions as agent-authored and keep the metadata with the code.*

## Where to capture it

The cheapest place is the **commit**. Jamie Tanna settled on a Git
`Co-authored-by` trailer naming the model —

```
Co-authored-by: gpt-oss:20b <...>
```

— over inline comments or PR descriptions, because the trailer is **durable**:
commit metadata survives platform migrations and code churn, whereas comments
rot and PR threads get lost when a project moves hosts. Reasons are mundane:
honest context for reviewers, and *"making it easier for my colleagues in
legal."* Some projects now require it — Ghostty asks contributors to disclose AI
assistance on PRs.

Two capture points trade off:

| Capture point | Pro | Con |
|---|---|---|
| **Commit trailers** | Permanent, survive migration | Only as honest as the tooling that writes them |
| **PR-level disclosure** (Ghostty style) | Easy to mandate | Coarse, easy to forget |

Either way: **capture at the moment of generation, not after** — same as
tracking origin or license for any other code.

## Why it matters

**You cannot review, measure, or govern what you cannot distinguish.** Provenance:

- **Routes [review](automated-review-verification.md) attention** to where it's
  needed.
- **Keeps productivity metrics honest** — machine-generated volume is not human
  output.
- **Answers licensing and audit questions** as more of the codebase becomes
  machine-written.
- **Speeds incident response** — AI code raises incident rate; without
  root-cause attribution, incidents "pile up" on on-call engineers who can't
  tell which changes a human reasoned about (SRE Roxane Fischer).

Vendor framing pushes further — Beyond Identity argues provenance should be a
**cryptographic link between every commit and a verified human-or-machine
identity** (citing ~41% of new code as AI-generated — *directional self-reported
marketing*, but the direction is real). That link ties provenance to
[agent identity & access](agent-identity-access.md).

## The honest caveat: plumbing, not policy

Provenance is only worth anything if captured **automatically and truthfully at
generation time.** A `Co-authored-by` trailer written by an honest tool is
evidence; one a developer can silently strip — or that never fires when someone
pastes from a chat window — is **theater.** Mandating disclosure doesn't make it
accurate; bolting attribution on after the fact is guesswork. **The value is in
the plumbing, not the policy.**

## Related

- [Agent Identity & Access](agent-identity-access.md) — cryptographic
  commit↔identity linkage is the strong form of provenance.
- [Automated Review & Verification](automated-review-verification.md) — where
  provenance routes attention.
- [Agent Observability](agent-observability.md) — the runtime-trace counterpart
  to source-level attribution.

## References
- [AI-Code Provenance — Tessl Patterns](https://tessl.io/patterns/quality-security/ai-code-provenance/)
