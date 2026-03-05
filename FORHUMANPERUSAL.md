# AGENTIC ENGINEERING CLASS - CREATIVE IDEAS (FOR HUMAN PERUSAL)

[*Note to Agent*: this file is in very early stage, please populate as you see fit.]

Suggested format:

### YYYY-MM-DD
* Point form idea 1
* Point form idea 2
* ... 

### 2026-03-01
* Consider a tiny `site/slides-manifest.json` (ordered list of active slide files). Future add/remove operations could update one manifest and auto-build nav/TOC.
* Add a lightweight "link integrity" check script (or CI step) that scans for `.html` links and flags missing targets before publishing.
* Keep two delivery modes on purpose: `classic HTML pages` for archival traceability and `Reveal Markdown deck` for fast iteration before class.
* Try a "style packs" experiment for Reveal (`newspaper`, `comic`, `lab notebook`) by swapping only CSS variables and font families.
* Put references in speaker notes for live delivery, then auto-expand them into a handout export so slides stay clean while evidence remains explicit.
* Create a `slide archetypes` cheat sheet (`title`, `timeline`, `debate`, `case-study`, `reflection`) so building new slides feels like choosing a proven pattern, not designing from scratch each time.
* Add optional `audience mode` query params in Reveal (`?audience=library` vs `?audience=industry`) that toggle small wording differences via CSS/JS classes.
* Consider one ending slide that polls confidence change before/after class to make impact visible in real time.
* Add a tiny release script: run local preview check, commit, push, and print GitHub Pages URL so publishing becomes one command.

### 2026-03-03
* Add a small "slide lint" script that flags likely layout traps in `slides.md` (for example: heading lines over N characters, too many top-level headings per slide, missing `---` separators).
* Consider a "debug overlay" CSS class you can toggle per slide to show content bounds while positioning text over backgrounds.
* Create one optional utility class for stage-anchored notes (`.note-bottom-left`, `.note-bottom-right`) so footnotes are reusable and consistent.

### 2026-03-03 (Follow-up)
* Add a reusable `.debug-layout` mode in CSS that outlines present slide bounds and prints core computed metrics (top/left/transform) to quickly diagnose Reveal positioning bugs.

### 2026-03-05
* Consider a tiny "Markdown output map" note in the repo docs showing common Reveal render shapes (`heading + image => h2 + p > img`, lists, code blocks). This could save time when writing slide-specific CSS.
* Consider adding one "layout sandbox" slide at the end of `slides.md` where you can quickly test combinations like `img-flow-right img-sm` or `img-pin img-top-right img-md` before using them in real content.
* Consider naming conventions that encode mutually exclusive classes (`img-flow-*` vs `img-pin-*`) and adding one comment in CSS: "Do not combine flow and pin on the same image."
* Make placement utilities self-sufficient where possible (`img-top-right` should "just work"), and reserve combo classes for advanced cases only.
* Expose layout breakpoints as CSS variables (`--bp-medium`, `--bp-small`) so class behavior can be tuned once without hunting through media queries.
