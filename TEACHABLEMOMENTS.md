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

### 2026-03-03

Agent version: Codex (GPT-5)
Human goal: tune early Reveal slides while learning Markdown/CSS slide layout behavior.
Observations: layout regressions were caused more by content semantics than by one CSS rule; long body copy was authored as `##` headings, which bypassed dense body sizing.
Issue's root cause: Markdown heading levels (`#`, `##`, `###`) map directly to styled HTML headings, so using headings for paragraph copy creates oversized, high-margin blocks.
Initial implementation delivered: reworked Slide 3 to use one heading plus paragraph text, and Slide 4 to use compact bullet lists under two headings.
Human Input: confirmed intent to iterate slide-by-slide and asked for debugging help on visual placement.
Agent reaction and rationalle: prioritized semantic markdown fixes before adding more CSS overrides to avoid compounding style debt.
Resolution and Method: replaced heading-style body text with paragraph/list structures in `site/reveal/slides.md`.
Final Fixes: Slides 3-4 now align with the dense content model used by later slides.
What succeeded: deck behavior became more predictable with cleaner markdown structure.
What Failed: some text encoding artifacts still remain in older migrated sections and should be cleaned progressively.

### 2026-03-03 (Follow-up)

Agent version: Codex (GPT-5)
Human goal: resolve Slide 3 appearing at the bottom edge despite valid markdown content.
Observations: Reveal rendered slide content correctly in DOM, but computed style assigned `top: 700px` to present sections from Slide 3 onward.
Issue's root cause: section positioning drift in Reveal stage layout caused visible slides to be offset by one slide-height.
Resolution and Method: added a scoped position normalization in theme CSS:
` .reveal .slides > section, .reveal .slides > section > section { top: 0; } `
Final Fixes: Slide 3 and 4 render in normal viewport position again; Slide 2 hero layout remains intact.
What succeeded: replicated issue with headless browser, captured computed positions, then fixed with minimal CSS override.
What Failed: n/a.

### 2026-03-05

Agent version: Codex (GPT-5)
Human goal: place a slide image to the right of Markdown bullet text on Reveal Slide 4 while preserving Markdown-first authoring.
Observations: styling the image by `alt` selector and `:has(...)` was brittle in this render flow; image continued to appear as a full-width block above the list.
Issue's root cause: Reveal Markdown emits the image as a paragraph block directly after the heading (`h2 + p`), so targeting the generated structure is more reliable than semantic image metadata.
Initial implementation delivered: right-float selectors based on `:has(img)` and later `img[alt="..."]`.
Human Input: reported visual regression with screenshot showing image still above text.
Agent reaction and rationalle: switched to structural selectors (`.slide-4 h2 + p` and `.slide-4 h2 + p img`) to style the actual Markdown output shape.
Resolution and Method: float the first paragraph after the heading right, constrain width/height, and clear before second heading; stack on mobile via media query.
Final Fixes: Slide 4 layout now uses robust structure-based CSS and keeps slide body mostly pure Markdown.
What succeeded: faster debugging by inspecting output pattern rather than content labels.
What Failed: initial assumption that alt-based targeting would be stable.

### 2026-03-05 (Follow-up)

Agent version: Codex (GPT-5)
Human goal: make image placement reusable across slides (`top-left`, `top-center`, `top-right`, etc.) instead of one-off Slide 4 CSS.
Observations: per-slide selectors solved one case but did not scale for "move images around" authoring needs.
Issue's root cause: image placement behavior depended on local markdown order and unique selectors, which is fragile during iterative editing.
Initial implementation delivered: utility class set in theme (`img-flow-right/left`, `img-pin`, size classes, top position classes, `clear-floats`) plus Slide 4 conversion to class-based usage.
Resolution and Method: replaced slide-specific CSS with reusable utility classes and mobile-safe fallback (all utilities stack in narrow viewports).
Final Fixes: image positioning is now class-driven and portable slide-to-slide.
What succeeded: easier experimentation without writing new CSS per slide.
What Failed: pure markdown image syntax cannot carry classes, so image placement utilities require an inline `<img ... class=\"...\">`.

### 2026-03-05 (Follow-up 2)

Agent version: Codex (GPT-5)
Human goal: make Slide 4 image reliably sit beside bullets after utility rollout.
Observations: slide markup had both `img-pin` and `img-flow-right` on the same element; these are mutually exclusive paradigms.
Issue's root cause: `img-pin` removes image from normal flow via absolute positioning, so float-based wrapping cannot occur.
Resolution and Method: removed `img-pin` from Slide 4 image and tightened CSS selectors to target `img` elements directly (`img.img-flow-right`, `img.img-pin`) for clearer rule intent.
Final Fixes: Slide 4 now uses flow-only placement class stack (`img-flow-right img-sm`) with float clearing before the next heading.
What succeeded: class semantics are now explicit and less error-prone.
What Failed: combining positional and flow utilities on one image caused conflicting behavior.

### 2026-03-05 (Follow-up 3)

Agent version: Codex (GPT-5)
Human goal: make `img-top-right` work by itself (without remembering `img-pin`).
Observations: coordinate classes (`img-top-*`) set `top/left/right` but were inert unless `position:absolute` was added separately.
Issue's root cause: utility API required hidden class dependency (`img-top-*` depended on `img-pin`).
Resolution and Method: updated CSS so `img-top-left`, `img-top-center`, and `img-top-right` are self-sufficient pinning utilities (absolute position, z-index, display) and included them in shared image styling/mobile reset rules.
Final Fixes: top-position classes now work standalone; `img-pin` remains optional for custom positioned images.
What succeeded: fewer class combinations to remember and lower chance of silent layout failures.
What Failed: initial utility design had implicit dependencies.

### 2026-03-05 (Follow-up 4)

Agent version: Codex (GPT-5)
Human goal: reduce layout flip-flopping where flow images stack too early based on viewport width.
Observations: a single `max-width: 900px` rule was forcing both flow and pinned image utilities into centered stack behavior, including medium desktop windows.
Issue's root cause: one broad breakpoint treated all image modes the same, despite different readability needs for flow vs pinned layouts.
Resolution and Method: split responsive logic into two stages: at `<=900px`, keep flow images beside text but smaller; at `<=700px`, stack flow images for readability. Pinned utilities still reset earlier.
Final Fixes: flow classes now behave more consistently across medium widths while preserving mobile safety.
What succeeded: better continuity of intended "image beside text" behavior during window resizing.
What Failed: n/a.
