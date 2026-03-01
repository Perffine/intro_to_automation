# Teachable Moments

Case-study notes for teaching agentic engineering from this project. 

## Session Log Suggested Format
### YYYY-MM-DD

[*NOTE TO AGENT*: Feel free to distil where suitable, populate these suggested headers, add/remove as needed]

Agent version: 
Human goal:
Observations:
Issue's root cause:
Initial implementation delivered:
Human Input:
Agent reaction and rationalle:
Resolution and Method:
Final Fixes:
What succeeded:
What Failed:

### 2026-02-28

Agent version: Codex (GPT-5)
Human goal: downgrade to a very simple website where each slide is its own page, with table of contents and clickable source links.
Observations: a lower-complexity architecture improved maintainability and made source-citation behavior easier to reason about.
Issue's root cause: the first generator script was placed inside the generated output folder (`site/`), so rebuilds deleted the script itself.
Initial implementation delivered: generated `site/index.html` plus one HTML page per slide, with Home/Previous/Next navigation and source chips beside URLs.
Human Input: requested direct source hotlinks from slide text and a simple badge-like domain indicator (Perplexity-style reference).
Agent reaction and rationalle: prioritized static generation and zero-runtime JS dependencies to keep the stack aligned with HTML/CSS/JS basics.
Resolution and Method: moved generator to `scripts/generate_site.py`, added URL cleanup for trailing punctuation/quotes, and regenerated all pages.
Final Fixes: working static site with 44 slide pages, table of contents, inline source links opening in new tabs, and deduplicated source chip list per slide.
What succeeded: rapid conversion from deck data to browsable static pages with visible citation UX.
What Failed: placing build logic in an output directory caused self-deletion during regeneration.

### 2026-02-28

Agent version: Codex (GPT-5)
Human goal: convert from slide-image pages to web-native text pages and make in-text citation numbers clickable.
Observations: references were present as numbered bibliography entries on later slides, while earlier slides used only numeric citation markers like `(1)` and `(45)`.
Issue's root cause: URL-only linking misses numbered citations when URLs are centralized in a separate sources section.
Initial implementation delivered: source-chip links for explicit URLs only.
Human Input: requested direct citation linking from numbered markers in body text to their corresponding source URL.
Agent reaction and rationalle: added a reference-map parser from bibliography lines and citation token replacement so evidence links are reachable exactly where cited.
Resolution and Method: generator now builds a `reference_number -> URL` map, rewrites `(n)`/`[n]` to clickable `[n]` badges, and renders per-slide cited-reference lists.
Final Fixes: removed slide image embeds from generated pages; preserved simple Home/Previous/Next flow and TOC while making citations live.
What succeeded: citations now resolve directly from narrative text.
What Failed: initial trailing-punctuation handling for URLs risked clipping some URL endings and required parser refinement.

### 2026-02-28

Agent version: Codex (GPT-5)
Human goal: aggregate distributed source links into one canonical page now that the site is no longer slide-centric.
Observations: source references were spread across pages 35-44 and hard to review as a single bibliography artifact.
Issue's root cause: source metadata was parsed but only rendered in per-slide contexts.
Initial implementation delivered: per-slide sources + in-text citation links.
Human Input: requested one concatenated source page.
Agent reaction and rationalle: added a generated `sources.html` from parsed references in slides 35-44 while preserving in-text citation behavior.
Resolution and Method: generator now collects ordered bibliography entries from slide IDs 35-44 and writes them as one page; navigation links point to `All Sources`.
Final Fixes: added index and slide-level links to consolidated sources page; generator now writes in-place to avoid lock issues during rebuild.
What succeeded: one canonical bibliography page now exists for the entire class.
What Failed: initial full-folder delete failed due file lock from active process, requiring a safer write strategy.

### 2026-02-28

Agent version: Codex (GPT-5)
Human goal: make `site/` the only source of truth and remove old generation pipeline.
Observations: once static pages stabilized, keeping extraction/generation code increased cognitive load and maintenance branches.
Issue's root cause: the repo still reflected a transitional architecture (build pipeline + generated output).
Initial implementation delivered: functional static site plus generation scripts.
Human Input: explicitly confirmed `site/` should be source-of-truth going forward.
Agent reaction and rationalle: removed non-essential pipeline folders and simplified onboarding docs to reduce future ambiguity.
Resolution and Method: deleted `web_interactive/` and `scripts/`; rewrote `README.md` for direct static-site usage.
Final Fixes: repo now centers on `site/` artifacts only for delivery workflow.
What succeeded: simpler mental model and easier contribution path.
What Failed: n/a.

### 2026-03-01

Agent version: Codex (GPT-5)
Human goal: remove slide pages `004` and `005` and all links to them.
Observations: in a static-only repo, "delete content" tasks still require link-graph updates to avoid dead navigation.
Issue's root cause: slide nav and TOC are hardcoded HTML, so deleting files alone would create broken links.
Initial implementation delivered: direct file deletion request.
Human Input: asked for pages + links removal only.
Agent reaction and rationalle: used minimal edits (2 nav links, TOC entries, file deletions) instead of renumbering all slides.
Resolution and Method: rewired `003 -> 006`, `006 <- 003`, removed TOC entries for 004/005, deleted `site/slides/004.html` and `site/slides/005.html`.
Final Fixes: site no longer references the removed pages.
What succeeded: change stayed surgical and low-risk.
What Failed: n/a.

### 2026-03-01

Agent version: Codex (GPT-5)
Human goal: evaluate and prototype migration from per-slide HTML pages to Reveal.js + Markdown for easier maintenance and a more playful look.
Observations: existing architecture is stable but repetitive for content updates; Reveal can reduce edit friction while still allowing custom HTML/CSS when slides need bespoke layouts.
Issue's root cause: "easy to edit" and "visually expressive" were treated as a single format choice, but practical delivery needs both structured authoring and selective design freedom.
Initial implementation delivered: created `site/reveal/index.html`, `site/reveal/slides.md`, and `site/reveal/assets/whimsy-theme.css` as a standalone pilot.
Human Input: approved trying the migration and requested brief framing around React.js confusion.
Agent reaction and rationalle: implemented a hybrid approach (Markdown-first, HTML-enabled) to avoid a full rewrite while validating authoring speed and style flexibility.
Resolution and Method: linked pilot from `site/index.html`, added README run/edit instructions, and left existing `site/slides/*.html` untouched for low-risk parallel iteration.
Final Fixes: project now supports two coexisting delivery formats: classic static slides and Reveal pilot deck.
What succeeded: achieved migration proof-of-concept without breaking current course pages.
What Failed: full citation automation parity is not yet implemented in the Reveal pilot.

### 2026-03-01

Agent version: Codex (GPT-5)
Human goal: perform full migration so Reveal.js + Markdown becomes the main class delivery format.
Observations: converting many static pages manually would be high-friction and error-prone; deterministic transformation from existing HTML can preserve breadth fast.
Issue's root cause: architecture still split between legacy static pages and a small pilot deck, causing dual-maintenance overhead.
Initial implementation delivered: full extraction from `site/slides/*.html` into `site/reveal/slides.md`, including vertical per-slide source panels.
Human Input: confirmed intent to migrate whole site after validating Reveal authoring workflow.
Agent reaction and rationalle: used scripted transformation to keep scope reliable and to preserve legacy pages as rollback/archive.
Resolution and Method: generated Reveal markdown from legacy pages, switched `site/index.html` to Reveal-first landing, copied old TOC to `site/legacy.html`, tuned theme for dense content readability.
Final Fixes: Reveal deck is now primary, with archive fallback still accessible.
What succeeded: complete migration without deleting legacy material.
What Failed: some inherited text encoding artifacts from source content remain and should be cleaned in a later editorial pass.

### 2026-03-01

Agent version: Codex (GPT-5)
Human goal: initialize Git and publish repository to GitHub with browser-friendly auth workflow.
Observations: local folder was not a Git repo; GitHub CLI auth was already active on account `Perffine`.
Issue's root cause: pushing without preprocessing would fail because `media/` included files above GitHub's 100 MB limit.
Initial implementation delivered: initialized repo (`main`), added `.gitignore` for `media/`, committed project contents, created remote repo, and pushed.
Human Input: indicated browser sign-in preference due multiple accounts on same machine.
Agent reaction and rationalle: used existing authenticated session to avoid extra login friction while preserving publishability constraints.
Resolution and Method: `gh repo create Perffine/intro_to_automation --public --source . --remote origin --push`.
Final Fixes: repository now tracks `origin/main` with initial commit `ed282e6`.
What succeeded: end-to-end publish completed in one run.
What Failed: n/a.
