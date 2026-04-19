# .build/ — README generator

Single source of truth for every variation lives here. Edit `content.py`, run
`build.py`, commit the regenerated `variations/*.md`.

## Why

Each design in `variations/` is just a skin over the same facts. Without this,
changing your tagline meant editing 8 files. Now you edit one.

## Files

- **`content.py`** — name, bio, stack, projects, taglines, now-lines, quote.
  The only file you should edit day-to-day.
- **`build.py`** — one `render_vN()` function per theme. Pure Python, no deps.
- **`README.md`** — this file.

## Workflow

```bash
# 1. edit facts
$EDITOR .build/content.py

# 2. regenerate every variation
python3 .build/build.py

# 3. preview locally, then commit
git add variations/*.md
git commit -m "content: update <thing>"

# 4. if you want a different design live, swap root README.md
cp variations/V5_github.md README.md
git add README.md && git commit -m "profile: switch to V5"
```

## Design index

| file | vibe | use when |
|---|---|---|
| `V1_terminal.md` | CRT green phosphor | you want "I live in a terminal" |
| `V2_cyberpunk.md` | magenta × cyan duotone | job hunt, stand-out mode |
| `V3_brutalist.md` | black/white print | minimal, serious, portfolio-adjacent |
| `V4_retrobbs.md` | amber BBS 1987 | weird-flex energy |
| `V5_github.md` ★ | phosphor + animated SVGs | current live; highest signal |
| `V6_notebook.md` | research-notebook prose | when you want "thinker" not "hacker" |
| `VA_minimal.md` | antirez / sindresorhus | when the work should speak |
| `VC_demoreel.md` | 2×3 GIF grid | drop real demo GIFs in `assets/` first |

★ = current live root README

## Adding a new theme

1. Add `render_vX()` to `build.py`.
2. Register it in the `THEMES` dict at the bottom.
3. Run `python3 build.py`. New file appears in `variations/`.

## Editing content

Everything Claude-ish that appears on the profile lives in `content.py`:

- scalar fields — name, role, portfolio, email, bio, mantra, quote
- list fields — `rotating_taglines`, `boot_lines`, `now_lines`
- `stack` — list of dicts with `name/color/logo/text` (shields.io fields)
- `projects` — list of dicts with `name/url/emoji/short/insight/tags`

Re-run the generator and you're done.

## URL helpers

`build.py` has three helpers so theme code stays short:

- `capsule(**params)` → `capsule-render.vercel.app` banner
- `typing(lines, **params)` → `readme-typing-svg.demolab.com` animated SVG
- `shield(label, color, logo=, ...)` → `img.shields.io` static badge
- `skillicons(theme=, perline=, icons=)` → `skillicons.dev` icon row

Pass **raw** text to these helpers (not pre-URL-encoded). They encode once.
