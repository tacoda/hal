---
type: Reference
title: How I Use AI to Code (Chris MD Parsons)
tags: [agentic-coding, workflow, ai-first, verification, fundamentals, loops]
timestamp: 2026-07-14
source: https://chrismdp.com/coding-with-ai/
---

# How I Use AI to Code (Chris MD Parsons)

A working practitioner's account (April 2026 rewrite of an August 2025 piece) of shipping
production code AI-first — deliberately distinct from "vibe coding". The argument is not
that AI writes code for you and you skim the diff; it is that you build a disciplined
system around the agent so it can run, verify itself, and only surface to you when a human
judgment is genuinely needed.

## AI-first, not vibe coding

Vibe coding means generating code you never really read and approving it by feel. Parsons'
approach is the opposite: the agent generates, but the *system* — tests, types, CI, review
surfaces — decides whether the output is acceptable before it reaches your eyes. The human
stays in the loop for direction and judgment, not for rubber-stamping every diff. This
lines up with [Vibe Coding vs Spec-Driven Development](vibe-coding-vs-spec-driven-development.md)
and [No Vibes Allowed (Dex Horthy)](../harness-engineering/no-vibes-allowed-dex-horthy.md).

## Loops do the work

Once the setup is right, the agent runs in loops (see [Ralph Wiggum, Software Engineer](../harness-engineering/ralph-wiggum-software-engineer.md)
and [Loop Engineering](../harness-engineering/loop-engineering.md)) — producing, self-checking, and continuing
against a completion goal rather than stopping after one turn. The developer's leverage
comes from arranging the environment so those loops are productive, which connects to
[Agent Harness Engineering](../harness-engineering/agent-harness-engineering.md) and
[Engineer the Loop](../harness-engineering/engineer-the-loop.md).

## Feedback is the new bottleneck

Once loops are running, the constraint shifts from *generation* to *verification*: how fast
can you tell whether what was generated is right? Parsons' unfashionable answer is
fundamentals — automated tests, continuous delivery, infrastructure as code, linting, type
checking; "everything you were meant to have in 2015." Without them the agent cannot halt on
an obvious failure and you are back to approving diffs by eye, the exact job AI was supposed
to eliminate. Teams that kept their CI pipeline sharp are flying; teams that let it rot are
stuck rubber-stamping. Anyone claiming the fundamentals are obsolete is selling something.
This thread is developed in its own note, [Feedback Is the New Bottleneck](../harness-engineering/feedback-is-the-new-bottleneck.md).

A team that can generate five approaches and verify all five in an afternoon beats a team
that generates one and waits a week. So the investment shifts: build better *review
surfaces*, not better prompts. Make feedback unnecessary where you can (let the agent verify
against a realistic environment before asking a human) and instant where you cannot. He
cites the CTO Craft Con finding — 90% of developers believed they were faster with AI while
measured delivery was 20% slower — as the feedback bottleneck showing up in the numbers: the
coding got faster, the telling-whether-it's-right did not. See also
[The AI Productivity Paradox](../ai-org/ai-productivity-paradox.md) and
[Automated Review & Verification](../harness-engineering/automated-review-verification.md).

## References

- [How I Use AI to Code — Chris MD Parsons](https://chrismdp.com/coding-with-ai/)
