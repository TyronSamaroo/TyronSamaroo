# variations/

Archive of alternative README designs for the `TyronSamaroo` profile.

Each file here is a complete, drop-in replacement for the top-level `README.md` and renders with live SVG services on GitHub. To switch styles, copy one over the root README (or ping Claude to push it).

| # | file | style | preview |
|---|------|-------|---------|
| V1 | [`V1_terminal.md`](./V1_terminal.md)   | CRT phosphor terminal · green on black · hacker vibe | click file → see rendered |
| V2 | [`V2_cyberpunk.md`](./V2_cyberpunk.md) | Duotone magenta/cyan · glitch · synthwave stats      | click file → see rendered |
| V3 | [`V3_brutalist.md`](./V3_brutalist.md) | Stark black/white · oversized type · magazine feel   | click file → see rendered |
| V4 | [`V4_retrobbs.md`](./V4_retrobbs.md)   | Amber BBS · ANSI art · `NODE 01 / 01`                | click file → see rendered |
| V5 | [`V5_github.md`](./V5_github.md)       | GitHub-native dark · live stat cards · **CURRENT**   | click file → see rendered |

## To swap the active look

```bash
# from repo root, overwrite README.md with any variation:
cp variations/V2_cyberpunk.md README.md
git add README.md && git commit -m "switch profile to V2 cyberpunk" && git push
```

Or just tell Claude: _"promote V2 to my profile"_ and it'll push via `gh api`.

The `README.md` at the repo root is what renders on [github.com/TyronSamaroo](https://github.com/TyronSamaroo). Everything in this folder is an archive.
