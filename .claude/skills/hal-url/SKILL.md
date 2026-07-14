---
name: hal-url
description: Ingest a URL into HAL. Fetches the page (or transcribes the video, for a YouTube/Vimeo link), writes a synthesized Reference note under wiki/ with a source link at the bottom, and updates the catalog. Use when the user pastes or names a URL to save.
---

# hal-url

Ingest a URL into the HAL knowledge base. Read `CLAUDE.md` for the schema first.

## Steps

1. Take the URL from the user's message. **Detect the kind:** if the host is a video
   platform — `youtube.com`, `youtu.be`, `vimeo.com` (or a link that is plainly a
   video) — use the **video branch** below. Otherwise it's a page: continue to step 2.
2. **Get the content.**
   - **Page:** fetch and read it. Prefer `ctx_fetch_and_index` (keeps raw bytes out of
     context); fall back to `WebFetch`.
   - **Video → transcribe** (get the words, not the pixels):
     1. Prefer existing **captions/subtitles** — cheapest by far. Use `yt-dlp` to pull
        them without downloading the video:
        `yt-dlp --skip-download --write-subs --write-auto-subs --sub-format vtt --sub-langs "en.*" -o '/tmp/hal-%(id)s.%(ext)s' <url>`
        (install on demand if missing: `pip install -q yt-dlp` or `brew install yt-dlp`).
        Then strip the `.vtt` to plain text in a sandbox (`ctx_execute_file`) — drop
        timestamps, cue numbers, and dedup the rolling auto-caption lines — so only the
        transcript text enters context, not the raw VTT.
     2. **No captions** (common on Vimeo): fall back to audio ASR. Grab audio only
        (`yt-dlp -x --audio-format mp3 -o '/tmp/hal-%(id)s.%(ext)s' <url>`; `ffmpeg` is
        available) and transcribe with `whisper` (install on demand:
        `pip install -q openai-whisper`, model `small` is enough). Heavier — only when
        there are no captions.
     3. If neither works (no captions, ASR unavailable, or the fetch fails), **stop and
        say so** rather than writing a note from the title alone.
     Capture the video **title and author/channel** for the note title and attribution.
3. Decide the title and a kebab-case slug. Pick tags. Check `wiki/` for an existing
   note on the same topic — if one exists, update it instead of creating a duplicate,
   and cross-link.
4. Choose the path: `wiki/<slug>.md`, or `wiki/<topic>/<slug>.md` if a topic folder
   already holds related notes.
5. Write the note:
   - Frontmatter: `type: Reference`, `title`, `tags`, `timestamp` (today), `source`
     (the URL).
   - Body: a clean synthesis **in your own words** — key ideas, definitions, takeaways.
     Not a transcript. Cross-link related notes with markdown links.
   - **Visuals:** if the page explains an inherently visual concept — a layered stack, a
     loop/cycle, a flow, an architecture — recreate it as a **mermaid** diagram (GitHub
     renders it) with an appropriate chart type. Only when it aids understanding; for
     prose, tables, or lists, words are enough.
   - End with:
     ```
     ## References
     - [<page title>](<url>)
     ```
6. Append a pointer line to the nearest `index.md`:
   `- [Title](slug.md) — one-line hook`.
7. Report the path written and a one-line summary.
