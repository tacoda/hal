---
type: Reference
title: Tiny Teams — Oleve ($6M ARR, 5M users, 4 employees)
tags: [tiny-teams, ai-native-org, consumer-ai, agentic-workflows, ai-engineering, lean-team]
timestamp: 2026-07-14
source: https://www.youtube.com/watch?v=aDiEQngFsFU
---

# Tiny Teams — Oleve ($6M ARR, 5M users, 4 employees)

Sid Bendre (CTO, Oleve — formerly Quizard) on Latent Space. Oleve runs a portfolio
of consumer AI apps — **Quizard** (photo-scan homework tutor) and **Unstuck AI** —
doing **~5M users, $6M ARR, profitable since month nine, with four employees.** A
concrete data point on the [tiny teams / dark factory](dark-factory.md) thesis:
AI-native leverage lets a handful of people operate at a scale that used to need a
company. Cited as a source in [org shape & team size](org-shape-team-size.md).

## Org shape: product engineers + a platform team

The company splits into two orgs:

- **Product engineers** each "CEO" one or two apps — living in the metrics, owning
  revenue, retention, churn, and UX. They *are* the revenue lines.
- **A platform team**, deliberately detached from any single product, builds the
  reusable systems — AI infrastructure, referral and notification mechanisms,
  growth tooling — so brands scale "from zero to a million as deterministically as
  possible." The platform is the intended **moat**: turning repeatable growth
  playbooks into automation. The eventual aim is an internal "shadow org run by
  agents," hiring humans for taste and strategy while agents run operations
  (starting with growth/marketing research — e.g. automating what a marketer does
  scrolling TikTok all day). Their build order: **basic automation first, agent
  only if it needs to scale** — don't over-invest in standing up an agent when a
  script or better dashboard suffices.

## AI engineering lessons

- **Prompt routing, not model routing.** They found model routing's return
  marginal. Instead a fine-tuned **feature extractor** up front classifies the
  question (subject, sub-topic, intent), then routes to the **right prompt / tools /
  examples**. This *rides* base-model improvements instead of competing with the
  labs — as models get better, the system compounds on top.
- **Reliability over raw agency.** Rather than an agent stitching together axiomatic
  tools (search, summarize) — impossible to debug at scale — they shipped pure
  vector search to a beta audience, watched what users actually did, **categorized
  the intents**, then built a **deterministic LLM-driven workflow per intent.** The
  LLM only classifies intent and fills parameters; the workflow is predetermined.
  This gives consistent UX ("no magic one moment, none the next") *and* a lever:
  a high-volume, poorly-performing intent has a known expected value, so you know
  where to point engineers. He'd call it **reliable**, not fully deterministic.
- **De-emphasize prompt tuning.** Models keep getting better at bad prompts; the
  higher-leverage work is **orchestration** — building determinism into a
  non-deterministic system. He likens prompt engineering to programming-language
  design: decide where the typing/constraints are and how expressive it can be.
- **Model taste:** Claude is notably better at human/Gen-Z-sounding text (OpenAI
  "throws in hashtags and emojis"); OpenAI/Claude are the two workhorses, Gemini
  under evaluation. Multi-model means you need a gateway, not just Azure credits.
  (See [models](models.md), [model router](model-router.md).)

## Scrappy infra hacks (lean-team tells)

- **Vector-index de-indexer:** consumer AI has a "novelty test" — users upload
  something once and never return to it. Since Azure AI Search prices on stored
  index size, a job periodically **de-indexes** stale content and **reloads on
  demand** when re-triggered — data is kept, only active content is charged.
- **LaunchDarkly as a load balancer:** stage-rollout flags are "just a router," so
  they route traffic across multi-region Azure OpenAI endpoints via feature-flag
  percentages — load-balancing and cross-product model switching **without
  redeploys.** They run so much on it that "if LaunchDarkly goes down, we're
  cooked." Experiments run on **RevenueCat paywall metadata** and **Mixpanel**, not
  LaunchDarkly (which they use purely as flags, off its priced dimension).
- **AI tooling is native SDKs, no frameworks** (no LangChain) — because knowing
  exactly what goes into the prompt is critical, they own the integrations.

## Distribution as the real moat

Thesis: consumer software now looks less like classic tech and more like **CPG** —
distribution- and brand-first, because users have refined taste from years of paying
online. Growth came from TikTok/Instagram: a viral launch (Quizard hit 10k users in
30 hours; Unstuck 250M views in a month off a copied "sticky note" format), then
influencer/UGC campaigns. They aim to make going viral "more of a science" —
deterministic distribution — since natural churn is baked in (students graduate
every four years).

## Related

- [Org Shape & Team Size](org-shape-team-size.md) — this is a primary data point for it.
- [Dark Factory](dark-factory.md) — the tiny-team / AI-native production thesis.
- [Model Router](model-router.md) / [Models](models.md) — contrast with their prompt-routing choice.

## References
- [Tiny Teams: $6m ARR, 5m users with 4 employees — Sid Bendre, Oleve — Latent Space](https://www.youtube.com/watch?v=aDiEQngFsFU)
