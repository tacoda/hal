---
name: hal-image
description: Ingest a pasted image into HAL. Stores the image as a PNG under sources/images/, extracts the information into an Image note under wiki/, and links the stored PNG at the bottom. Use when the user pastes or attaches an image to save.
---

# hal-image

Ingest an image into the HAL knowledge base. Read `CLAUDE.md` for the schema first.

## Steps

1. Read the pasted/attached image.
2. Decide a title and kebab-case slug from its content.
3. Store the original PNG at `sources/images/<slug>.png` (immutable — never edited
   later). If the harness gives you a file path for the paste, copy it there; if you
   cannot write the binary directly, ask the user to save it to that exact path.
4. Choose the note path: `wiki/<slug>.md` (or a topic subfolder if one fits).
5. Write the note:
   - Frontmatter: `type: Image`, `title`, `tags`, `timestamp` (today),
     `source: sources/images/<slug>.png`.
   - Body: extract everything useful from the image — text, diagrams described,
     data in tables, key points — as clean markdown. Cross-link related notes.
   - End with:
     ```
     ## References
     - ![<title>](../sources/images/<slug>.png)
     ```
     (adjust the relative path to the note's depth).
6. Append a pointer line to the nearest `index.md`.
7. Report the note path and the stored image path.
