---
name: hal-suggest
description: Suggest a topic from the HAL knowledge base for the user to learn next — surfacing recently-added notes they likely haven't absorbed yet, so new material doesn't just pile up unread. Use when the user wants a learning suggestion, a "what should I read/learn next", or to discover recent additions.
---

# hal-suggest

Suggest something from the HAL knowledge base worth learning next. The point of
HAL is reference **and** comprehension — this surfaces new material before it
rots unread. Read `CLAUDE.md` for the schema first.

## Steps

1. Find what's recent. HAL has no read-tracking, so use **recency** as the proxy
   for "not yet absorbed": the newest notes by `timestamp` frontmatter, and the
   most recently added files by git — `git -C <repo> log --diff-filter=A
   --name-only --format= -- wiki/ | head`. The freshest notes are the strongest
   candidates.
2. Read the candidate notes enough to describe them accurately.
3. Suggest **one primary topic** — the single most worth-it thing to learn next
   — with a one-to-two line hook on *why* it's interesting and how it connects to
   notes the user likely already knows (follow the cross-links).
4. Then list **2–3 alternates** as one-liners, so the user can pick a different
   direction. Each is `[note title](wiki/…md) — hook`.
5. Offer the next move: e.g. "want me to `/hal-explain` it or `/hal-quiz` you on
   it?" Don't expand into a full explanation unless the user asks.

## Style

- Lead with the single best suggestion, not a menu — a menu is the fallback,
  not the headline.
- Bias toward **recent and unconnected** notes: something new that isn't yet
  linked into what the user already understands is the highest-value gap.
- Keep it short. This is a pointer to learning, not the lesson itself.
