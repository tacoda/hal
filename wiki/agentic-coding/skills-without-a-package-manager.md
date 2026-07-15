---
type: Reference
title: The Mess of Managing Skills Without a Package Manager
tags: [agent-skills, registries, distribution, reuse, ai-assisted-development]
timestamp: 2026-07-14
source: https://www.youtube.com/shorts/ZdkHwRU6fRM
---

# The Mess of Managing Skills Without a Package Manager

A short clip (AI Native Dev) naming a specific irony in agent **skills**: they are
*built to be reusable*, but they have **no distribution system**. There's no package
manager for skills the way there is for code libraries.

The consequence is manual, brittle sharing. People **copy the markdown files and
folders by hand** and check them into their repos — and often **multiple times within
the same repo**, because different agents each want their own copy to consume. Reuse
in principle, duplication in practice.

This is the gap a **[registry](../ai-platform/registries.md)** fills for other artifacts: a canonical
place to publish, version, and pull a shared asset, instead of copy-pasting it and
letting the copies drift. Skills, as of this clip, don't have that layer yet.

## Related

- [Registries](../ai-platform/registries.md) — the missing distribution/versioning layer for shared assets.
- [Claude Skills (Willison)](claude-skills-willison.md) — what agent skills are.
- [Skills (Matt Pocock)](mattpocock-skills.md) — more on the skills format.

## References
- [The Mess of Managing Skills Without a Package Manager — AI Native Dev](https://www.youtube.com/shorts/ZdkHwRU6fRM)
