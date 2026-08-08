# Albums Page — Design

**Date:** 2026-08-08
**Status:** Approved

## Purpose

Add a music section to the blog. Each release — album or single — gets its own
page showing album cover art and, for every track, its own cover art, an MP3
player, a liner note, links to the blog posts the song draws on, and the full
lyrics. An index page lists every release as a cover-art card.

The first entry is the single **Get Off the Pavement**, an arena-metal track
sung in the voice of Orëveriel, drawn from the Vanyanan Cantos. Its MP3 does
not exist yet, so the page must render correctly with audio absent.

## Build Constraint

`Gemfile` uses the `github-pages` gem, there is no Actions workflow, and
`_site/` is gitignored. GitHub Pages therefore builds this site remotely and
**custom plugins are unavailable**. This rules out generating per-release pages
from `_data/*.yml`, which needs a plugin. Collections are natively supported
and are the only plugin-free route to a page per release.

Docker (`docker-compose.yml`) exists for local preview only and is the
verification harness for this work.

## Architecture

| Piece | Path | Purpose |
|---|---|---|
| Collection config | `_config.yml` | `albums` collection, `output: true`, `permalink: /albums/:name/` |
| Release files | `_albums/<slug>.md` | One file per album or single |
| Index page | `albums.html` | `layout: page`, `permalink: /albums/`, `group: navigation` |
| Release layout | `_layouts/album.html` | Renders album header and tracklist |
| Lyrics | `_includes/lyrics/<slug>-NN.txt` | One plain-text file per track |
| Album/track art | `/assets/images/albums/` | Cover images |
| Audio | `/assets/audio/` | MP3 files |
| Styles | `assets/css/terminal.css` | New section appended |

`group: navigation` on `albums.html` makes the nav link appear automatically
via the existing loop in `_layouts/default.html`. No layout edits are needed
elsewhere. Setting `permalink: /albums/` on the index keeps it from colliding
with the collection's `/albums/<name>/` release URLs.

A single is not a special case in the code. It is a release with
`type: single` and one entry in `tracks`.

## Data Shape

Release front matter:

```yaml
---
layout: album
title: Get Off the Pavement
type: single                 # single | album
date: 2026-08-08
artist: Orëveriel
cover: /assets/images/albums/get-off-the-pavement.webp
tracks:
  - title: Get Off the Pavement
    art: /assets/images/albums/get-off-the-pavement-01.webp
    mp3:                     # blank until the file exists
    lyrics_file: get-off-the-pavement-01.txt
    note: >
      Orëveriel heckling Vanyanan on the paved Fish Creek Trail —
      the accusation that he chose the safe surface on purpose.
    sources:
      - title: A Walk With Orëveriel
        url: /2019/07/oreveriel-at-the-park
---

Optional release notes, in Markdown, rendered under the header.
```

Field reference:

- `title`, `type`, `date`, `artist` — release metadata. `type` is `single` or
  `album` and is displayed verbatim, capitalized in CSS.
- `cover` — album art path.
- `tracks` — ordered list. Track order on the page is array order.
- `tracks[].mp3` — path under `/assets/audio/`. Blank or absent means the
  audio does not exist yet.
- `tracks[].lyrics_file` — filename only, resolved under `_includes/lyrics/`.
- `tracks[].note` — one or two sentences of commentary.
- `tracks[].sources` — list of `{title, url}` pointing at blog posts.

Lyrics files are plain text containing Suno-style section tags, e.g.:

```
[Verse 1]
Fifteen colors in my hair tonight
Two of them have never been and never will again
```

They render inside `<pre class="lyrics">`, so line breaks are preserved exactly
and bracketed tags render literally with no Markdown processing.

## Page Behavior

**Index (`/albums/`)** — releases sorted newest first by `date`. Each is a card
linking to its release page showing cover art, title, `Single · 2026`, and
track count. Two-column grid, one column under 768px, matching the existing
`.showcase` idiom and reusing the `:root` design tokens already in
`terminal.css`.

**Release page (`/albums/<slug>/`)** — album art and title block; the Markdown
body as release notes if present; then one section per track containing track
art, title, player, liner note, source links, and lyrics.

**Audio** — native `<audio controls>` with no JavaScript, consistent with the
rest of the site.

**Missing MP3** — when `mp3` is blank or absent, a muted `Audio coming soon`
block renders in the player's place. This is the state Get Off the Pavement
ships in.

## Failure Modes

- **Dynamic include.** `{% include lyrics/{{ track.lyrics_file }} %}` is the
  one uncertain mechanic and must be verified against a local docker build
  before the rest of the work is considered done. If it does not resolve, the
  fallback is a `_lyrics` collection with `output: false`, looked up with
  `where` on a slug field — plugin-free, same one-file-per-song shape, and the
  only front-matter change is renaming `lyrics_file` to `lyrics_id`.
- **Missing `cover`** — falls back to the first track's `art`, then to a CSS
  placeholder tile. Never a broken image.
- **Missing `lyrics_file`** — lyrics block is omitted rather than emitting a
  broken include.
- **Missing `note` or `sources`** — those blocks do not render.
- **Art files not yet uploaded** — referenced paths may not exist yet. The
  placeholder tile covers the album cover case; track art uses the same
  treatment so nothing 404s visibly before the images land.

## Testing

Manual verification via `docker compose up`, since the site has no test suite:

1. `/albums/` renders, shows one card, and the card links correctly.
2. `Albums` appears in the site nav and is marked active on both pages.
3. `/albums/get-off-the-pavement/` renders album header and one track.
4. Lyrics preserve line breaks and show `[Verse 1]` literally.
5. Blank `mp3` produces the `Audio coming soon` block, not a broken player.
6. Source links resolve to the real post URL.
7. Single-column layout under 768px.
8. Build emits no Liquid warnings.

## Scope

**In scope:** collection config, index page, release layout, CSS, and the
Get Off the Pavement single with lyrics, liner note, source links, and both
art paths wired up.

**Out of scope:** the MP3 file itself, streaming-service links, playlists,
per-song pages, Suno production metadata (style prompt, BPM, exclude tags),
and any edit to existing pages beyond the nav link appearing automatically.
