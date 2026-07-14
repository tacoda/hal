---
name: hal-quiz
description: Quiz the user on the HAL knowledge base to test comprehension — on a named topic, or across all content if no topic is given. Draws questions only from the notes, asks one at a time, grades each answer against the note, and cites. Use when the user wants to be quizzed, tested, or to self-check retention ("quiz me", "test me on X").
---

# hal-quiz

Quiz the user from the HAL knowledge base to build comprehension, not just
reference. Read `CLAUDE.md` for the schema first.

## Steps

1. Determine scope. A topic was given → quiz on that. No topic → quiz across
   **all** content (pick a spread of notes; favor variety over a single area).
2. Gather material. Use `ctx_search` if the wiki is indexed, otherwise
   `Grep`/`Glob` over `wiki/`. Read the notes you'll draw questions from.
3. Ask **one question at a time**. Wait for the user's answer before revealing
   the correct one or moving on — this is a quiz, not a worksheet dump.
4. Write questions **only from what the notes actually say**. Never test facts
   HAL doesn't contain. Mix difficulty: recall (what is X), connection (how does
   X relate to Y), and application (when would you use X).
5. After each answer: mark it right / partial / wrong, give the correct answer
   in one or two lines, and cite the note it came from — `[note title](wiki/…md)`.
6. Default to **5 questions** unless the user asks for more or fewer. At the end,
   give a short score line and name the one or two notes worth re-reading.

## Style

- One question per turn. Number them (e.g. `Q3/5`).
- Grade honestly — a wrong answer surfaced now is the point. No inflation.
- Prefer questions that connect notes over isolated trivia; comprehension is
  the goal, so reward seeing how ideas link.
- If a topic is thin in HAL, say so and quiz on what's there rather than
  padding from general knowledge.
