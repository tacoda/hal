---
type: Reference
title: Agentic Coding and Persistent Returns to Expertise
tags: [anthropic, claude-code, expertise, domain-knowledge, labor-market, research]
timestamp: 2026-07-14
source: https://www.anthropic.com/research/claude-code-expertise
---

# Agentic Coding and Persistent Returns to Expertise

Anthropic's economic-research analysis of **~400,000 Claude Code sessions** from
~235,000 people (Oct 2025–Apr 2026), studying task composition, human-AI collaboration,
and success rates. The headline: **domain expertise — not coding proficiency — is what
amplifies the tool.**

## Key findings

- **Division of labor.** In a typical session the human makes most of the *planning*
  decisions (**what** to do) and Claude makes most of the *execution* decisions
  (**how**). This is [from coder to orchestrator](from-coder-to-orchestrator.md) measured
  at scale.
- **Expertise is task-specific**, not job title. A classifier rates apparent expertise
  novice→expert from three signals: how precisely the user frames directions, what they
  ask Claude to verify, and whether the user corrects Claude or Claude corrects them. A
  senior engineer asking their first Rust question is a *beginner at Rust*; an accountant
  who never used Python but dictates exact reconciliation rules and catches the edge case
  is an *expert at that task*.
- **The more domain expertise, the more work Claude does per instruction**, and the more
  often the session succeeds. Expert-rated sessions reach verified success **more than
  twice as often** as novice-rated ones.
- **Novices give up.** 19% of apparent-novice sessions end *abandoned* (failed, zero
  lines written) versus 5–7% for everyone else. Steering the agent in the right direction
  is itself a product of expertise.
- **Competence beats mastery.** The gap between *intermediate* and *expert* users is
  modest — a working grasp of the domain captures most of the benefit; deep
  specialization adds only a little more.
- **Coding background is becoming less decisive.** In sessions that produce code, every
  major occupation succeeds within a few points of software engineers.
- **Trajectory over 7 months:** debugging's share of sessions fell nearly by half; usage
  shifted toward end-to-end agentic work (deploying, running code, data analysis, writing
  docs); estimated task value rose ~25%.

## The through-line

Success is set by *how well a person understands the problem they're solving*, not
whether they were trained to code. Coding agents don't substitute for domain
expertise — they **reward** it: the more understanding a worker brings, the more quality
work the agent can do. This is the complement to [comprehension debt](comprehension-debt.md)
(the study is cited there): the scarce, load-bearing resource is judgment and domain
command, and it is what [learning the craft](learning-the-craft.md) must now cultivate.

## Related

- [From Coder to Orchestrator](from-coder-to-orchestrator.md) — plan-vs-execute split,
  observed in the data.
- [Comprehension Debt](comprehension-debt.md) — why the understanding this study rewards
  is the thing at risk.
- [Learning the Craft](learning-the-craft.md) — building the domain command that pays off.

## References
- [Agentic coding and persistent returns to expertise — Anthropic](https://www.anthropic.com/research/claude-code-expertise)
