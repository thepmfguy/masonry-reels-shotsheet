# Masonry Reels shot-sheets

Editable, visual shot-sheets for Masonry short-form reels, served via GitHub Pages.
One inspiration reel = one folder under `reels/`; they all share one editor app.

## Structure
- `index.html` , the hub. Reads `reels.json` and lists every reel as a card linking to its sheet.
- `shot.html?r=<id>` , the editable shot-sheet app (shared by every reel). Loads `reels/<id>/data.json`, renders per-beat reference frames + script. Edit any text and click Save to commit back here.
- `reels.json` , registry of all reels: `[{id, title, brand, category, status, inspiration_url, length, date}]`.
- `reels/<id>/data.json` , one reel's content (title, meta, concept, audio, storyboard, beats, notes).
- `reels/<id>/frames/` , that reel's inspiration frames (storyboard + per-beat).
- `brand-reference.html` , the standing D2C / celebrity brand catalog.

## Saving
Saving needs a GitHub fine-grained token with **Contents: Read and write** on this repo. You paste it once; it is stored only in your browser (localStorage) and works across every reel. Save commits `reels/<id>/data.json`; the live page updates within about a minute.

## Adding a reel
Create `reels/<new-id>/` with `data.json` + `frames/`, append one entry to `reels.json`, commit. The hub and per-reel page pick it up automatically. (This is the step the planned automation will do per new inspiration link.)
