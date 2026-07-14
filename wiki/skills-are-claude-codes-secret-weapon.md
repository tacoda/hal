---
type: Reference
title: Skills Are Claude Code's Secret Weapon (Chris MD Parsons)
tags: [claude-code, skills, prompts, context-engineering, harness, workflow]
timestamp: 2026-07-14
source: https://chrismdp.com/skills-are-claude-codes-secret-weapon/
---

# Skills Are Claude Code's Secret Weapon (Chris MD Parsons)

January 2026. Parsons argues that most people never create skills because they do not see
the value — but once you understand what a skill can do, you start building a small,
personal collection that compounds. A skill is Claude Code's underused lever.

## What a skill is

A skill is a **reusable prompt Claude Code loads when needed** — the set of instructions you
would otherwise retype at the start of every task of a given kind. Each lives in its own
directory with a `SKILL.md` entrypoint that has two parts:

- **YAML frontmatter** — tells Claude *when* to use the skill.
- **Markdown body** — the instructions Claude follows once the skill is active.

You invoke one directly with `/skill-name`, or let Claude load it automatically when it
matches what you are doing. The power is in the *loading*: a skill only consumes context when
active, so you can keep dozens without cluttering every conversation — progressive disclosure
by design. See [Claude Skills (Willison)](claude-skills-willison.md),
[Mattpocock on Skills](mattpocock-skills.md), and [Why Cursor Ditched Rules for Skills](why-cursor-ditched-rules-for-skills.md).

## Clear descriptions matter

Because Claude decides whether to load a skill from its description, a vague description gets
ignored when it should fire, or fires when it should not. The description is written *for
Claude, not for you* — as if explaining to a colleague when to reach for this set of
instructions.

- Bad: "Writing help"
- Good: "Load before writing any blog post, LinkedIn post, or newsletter. Contains Chris's
  tone of voice, paragraph structure preferences, and British English spelling conventions."

You can also gate invocation via frontmatter: `disable-model-invocation: true` for a skill
only *you* can trigger (e.g. a deploy script), and `user-invocable: false` for background
knowledge Claude should use but users should not invoke directly. These controls stop skills
from running at the wrong time.

## Build your own

The strongest guidance: **do not import too many skills from other people.** A skill
represents *how you work*, not how someone else works — their preferences and workflow are
not yours, and the value comes from the skill matching your thinking precisely. Study others'
skills to see what is possible and how they structure instructions, but the ones you use
daily should be ones you wrote. And do not run a skill unless you know what is in it: a skill
has whatever access Claude Code has — it can read files, run commands, make changes.

This is skill-as-curated-prompt, the feedforward half of a harness. It pairs with the sensor
(feedback) side in [Maintainability Sensors for Coding Agents](maintainability-sensors-for-coding-agents.md)
and fits the broader picture in [Agent Harness Engineering](agent-harness-engineering.md),
[Skills Without a Package Manager](skills-without-a-package-manager.md), and
[Delete 90% of Your Prompt](delete-90-percent-of-your-prompt.md).

## References

- [Skills Are Claude Code's Secret Weapon — Chris MD Parsons](https://chrismdp.com/skills-are-claude-codes-secret-weapon/)
