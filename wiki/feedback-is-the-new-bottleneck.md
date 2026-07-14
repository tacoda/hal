---
type: Reference
title: Feedback Is the New Bottleneck (Chris MD Parsons)
tags: [verification, feedback, code-review, ci, review-surfaces, productivity]
timestamp: 2026-07-14
source: https://chrismdp.com/feedback-is-the-new-bottleneck/
---

# Feedback Is the New Bottleneck (Chris MD Parsons)

March 2026. A follow-on to Parsons' argument that code review is dying as a gatekeeping
mechanism: pull requests take seconds to create and hours to evaluate. As generation gets
cheap, the binding constraint moves from *how fast can we build* to **how fast can we tell
whether this is right**. Feedback — verification — is the new bottleneck.

## The constraint moved

A year ago the bottleneck was code generation. Now the agent produces faster than any human
can read, so the scarce resource is the loop that tells you whether the output is correct. A
team that can generate five approaches and verify all five in an afternoon outpaces a team
that generates one and waits a week for feedback. The lever is no longer prompt quality; it
is the speed and quality of the verification surface. See
[Automated Review & Verification](automated-review-verification.md) and
[Who Verifies AI Software](who-verifies-ai-software.md).

## Two directions: instant, or unnecessary

Parsons gives two moves:

1. **Make feedback unnecessary** — have the agent verify against a *realistic environment*
   before it ever asks a human. He cites StrongDM's Software Factory, which spins up synthetic
   replicas of services like Okta, Jira, Slack, and Google Workspace so agents validate at
   scale without hitting real APIs or rate limits (see [StrongDM Software Factory](strongdm-software-factory.md)),
   and Cursor's agent computer use / video output, letting an agent run the software it built
   and send a video demonstration (see [Cursor Agent Swarm & Browser](cursor-agent-swarm-browser.md)).
2. **Make feedback instant** where it cannot be removed — build better *review surfaces*, not
   better prompts.

## The measurement problem

He points to the CTO Craft Con (March 2026) finding — reported by Will Lytle (Plandek) and
corroborated by Yigit Darcin (Trendyol) — that 90% of developers *believed* they were faster
with AI while measured delivery was **20% slower**, driven by downstream overhead. A separate
Faros.ai study of 10,000+ developers across 1,255 teams reinforces the review-cost story.
This is the feedback bottleneck surfacing in the numbers: coding got faster, verification did
not. See [The AI Productivity Paradox](ai-productivity-paradox.md),
[Does AI Boost Developer Productivity?](does-ai-boost-developer-productivity.md), and
[Before and After AI: Bottlenecks](before-and-after-ai-bottlenecks.md). Doctorow's "reverse
centaur" ("the van uses the driver up") is invoked as the failure mode when the human becomes
the slow verification bottleneck the machine feeds.

This is the same shift Parsons summarises in [How I Use AI to Code](how-i-use-ai-to-code-parsons.md),
and it is the demand side that [Maintainability Sensors for Coding Agents](maintainability-sensors-for-coding-agents.md)
answers on the supply side.

## References

- [Feedback Is the New Bottleneck — Chris MD Parsons](https://chrismdp.com/feedback-is-the-new-bottleneck/)
