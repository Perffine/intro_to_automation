# Agentic Engineering Class

## Purpose

Open source class content about Agentic Engineering, presented as a static website.

Started Feb 28 2026 by Victor Szabo (perr.ca).

## Source Of Truth

`site/` is the canonical project output and working surface moving forward.
Primary delivery format is now `Reveal.js + Markdown` at `site/reveal/`.

## Run

Option 1 (quick):
1. Open `site/index.html` in a browser.

Option 2 (local server):
```powershell
python -m http.server 5173 --directory .\site
```
Then open `http://localhost:5173`.

## Structure

### /site
- `index.html`: landing page (Reveal-first)
- `legacy.html`: legacy table of contents for archived per-slide pages
- `sources.html`: consolidated references list
- `slides/*.html`: legacy class pages (slides 001-034), retained for fallback/archive
- `assets/styles.css`: shared styling
- `reveal/index.html`: Reveal.js deck shell
- `reveal/slides.md`: editable slide content for full deck
- `reveal/assets/whimsy-theme.css`: custom Reveal theme

Note: source bibliography slides `035` to `044` are intentionally replaced by `site/sources.html`.

## Reveal Deck (Markdown + Reveal.js)

This repo uses Reveal as the primary presentation format at `site/reveal/`.

Run with local server:
```powershell
python -m http.server 5173 --directory .\site
```
Then open `http://localhost:5173/reveal/`.

Editing workflow:
1. Update slide content in `site/reveal/slides.md`.
2. Update visual style in `site/reveal/assets/whimsy-theme.css`.
3. Reload the browser.

Notes:
- The Reveal deck now mirrors all existing slide content.
- Legacy pages are still available at `site/legacy.html`.
- Reveal assets are loaded from CDN, so internet access is required unless vendored locally later.

### Supporting docs
- `AGENTS.md`
- `TEACHABLEMOMENTS.md`
- `FORHUMANPERUSAL.md`
- `CLASSBRAINSTORMING.md`
