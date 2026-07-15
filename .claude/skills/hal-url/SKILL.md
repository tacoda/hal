---
name: hal-url
description: Ingest a URL into HAL. Fetches the page (or transcribes the media, for a video or audio/podcast link — YouTube/Vimeo, a podcast episode, or a direct audio file), writes a synthesized Reference note under wiki/ with a source link at the bottom, and updates the catalog. Use when the user pastes or names a URL to save.
---

# hal-url

Ingest a URL into the HAL knowledge base. Read `CLAUDE.md` for the schema first.

## Steps

1. Take the URL from the user's message. **Detect the kind:**
   - **Video** — host is `youtube.com`, `youtu.be`, `vimeo.com`, or a link that is plainly
     a video → **media branch** below.
   - **Audio / podcast** — a podcast host (Apple Podcasts, Spotify, Overcast,
     Pocket Casts, transistor.fm, simplecast, buzzsprout, libsyn, …), an episode page with
     an embedded player, an RSS episode, or a direct audio file (`.mp3`, `.m4a`, `.wav`,
     `.ogg`) → **media branch** below.
   - **Page** — anything else → continue to step 2.
2. **Get the content.**
   - **Page:** fetch and read it. Prefer `ctx_fetch_and_index` (keeps raw bytes out of
     context); fall back to `WebFetch`.
   - **Media (video or audio/podcast) → transcribe** (get the words, not the pixels/waveform):
     1. **Check for an existing transcript first — cheapest by far.**
        - *Video:* pull captions/subtitles with `yt-dlp` without downloading the video:
          `yt-dlp --skip-download --write-subs --write-auto-subs --sub-format vtt --sub-langs "en.*" -o '/tmp/hal-%(id)s.%(ext)s' <url>`
        - *Podcast:* many episodes ship a transcript or full show notes on the episode
          page — fetch the page (`ctx_fetch_and_index`) and use that if it's a real
          transcript. `yt-dlp` also extracts subtitles from some podcast hosts; try it.
        Install `yt-dlp` on demand if missing (`pip install -q yt-dlp` / `brew install yt-dlp`).
        Strip any `.vtt` to plain text in a sandbox (`ctx_execute_file`) — drop timestamps,
        cue numbers, dedup rolling auto-caption lines — so only transcript text enters
        context, not raw VTT.
     2. **No transcript** (common for podcasts and Vimeo): fall back to audio ASR. Grab
        audio only — `yt-dlp -x --audio-format mp3 -o '/tmp/hal-%(id)s.%(ext)s' <url>` for
        a platform link, or download a direct audio file with `curl -L` (`ffmpeg` is
        available for any needed conversion) — and transcribe with `whisper` (install on
        demand: `pip install -q openai-whisper`, model `small` is enough). Heavier — only
        when there's no transcript. Long podcasts can run an hour+; that's expected.
     3. If none works (no transcript, ASR unavailable, or the fetch fails), **stop and
        say so** rather than writing a note from the title/description alone.
     Capture the **title and author** (channel for video; show + episode + host/guest for a
     podcast) for the note title and attribution.
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
