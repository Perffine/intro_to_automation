# Reveal Authoring Guide

Quick cookbook for editing the deck in `site/reveal/slides.md`.

## Core Idea

- Use Markdown for normal slide writing.
- Use small bits of HTML when you need layout or reusable components.
- Reuse existing slide classes and CSS utilities before inventing new ones.

## Slide Separators

- `---` starts a new horizontal slide.
- `--` starts a vertical child slide under the current horizontal slide.

Example:

```md
## Main slide

---

## Next main slide

--

### Child/source slide
```

## Slide Metadata

Add metadata comments directly above the slide content.

```html
<!-- .slide: class="content-slide dense" -->
## Dense content slide
```

```html
<!-- .slide: class="hero-bg hero-bg-clear hero-top-10" data-background-image="/images/example.png" -->
<h1>Big visual slide</h1>
```

Common slide classes already used in this deck:

- `content-slide`
- `content-slide-centered`
- `content-slide-larger`
- `dense`
- `compact`
- `concise`
- `source-page`
- `hero-bg`
- `hero-bg-clear`
- `hero-top-10`
- `title-splash`

## Good Defaults

For normal slides, this pattern is a safe starting point:

```html
<!-- .slide: class="content-slide" -->
## Slide Title

Short intro sentence.

- Point one
- Point two
- Point three
```

For text-heavy slides:

```html
<!-- .slide: class="content-slide dense" -->
## Slide Title

Longer body copy here.
```

## Markdown vs HTML

Use Markdown when possible:

- Headings
- Paragraphs
- Normal bullet lists
- Links

Use HTML when you need:

- Classes on elements
- Image positioning
- Custom layout blocks
- Reusable components like pills or emoji lists

## Images

Basic centered image:

```html
<img src="/images/example.png" alt="Example" class="spot-image" />
```

Flow image beside text:

```html
<img src="/images/example.png" alt="Example" class="img-flow-right img-sm" />
```

Pinned image near a corner:

```html
<img src="/images/example.png" alt="Example" class="img-top-right img-md" />
```

Available image helpers:

- `img-flow-right`
- `img-flow-left`
- `img-top-left`
- `img-top-center`
- `img-top-right`
- `img-sm`
- `img-md`
- `img-lg`
- `spot-image`
- `clear-floats`

If text needs to continue below a floated image, add:

```html
<div class="clear-floats"></div>
```

Important:

- Do not combine flow and pin styles on the same image.
- Use site-root image paths like `/images/example.png`.

## Emoji Lists

Use `emoji-list` when every line should have the same emoji marker.

```html
<ul class="emoji-list" style="--emoji:'&#x1F919;&#x1F3FD;';">
  <li>First point</li>
  <li>Second point</li>
  <li>Third point</li>
</ul>
```

Change the emoji by changing the `--emoji` value.

Examples:

```html
<ul class="emoji-list" style="--emoji:'&#x1F645;&#x1F3FD;&#x200D;&#x2642;&#xFE0F;';">
```

```html
<ul class="emoji-list" style="--emoji:'&#x2705';">
```

## Pills

Useful for short labels on title or intro slides.

```html
<div class="pill-row">
  <span class="pill">Fast edit</span>
  <span class="pill">Reveal nav</span>
  <span class="pill">Markdown first</span>
</div>
```

## Source Slides

This deck often uses a vertical child slide for sources:

```md
## Main claim slide

Key point here [[1]](https://example.com)

--

<!-- .slide: class="source-page compact" -->
### Sources

- [example.com](https://example.com)
- [another-source.org](https://another-source.org)
```

## Hero Slides

Use this when the image is the main event:

```html
<!-- .slide: class="hero-bg hero-bg-clear hero-top-10" data-background-image="/images/hero.png" data-background-size="contain" data-background-position="center" data-background-repeat="no-repeat" data-background-color="#000" -->

<h1 class="red-font">intro</h1>
<h1 class="red-font">to</h1>
<h1 class="red-font">automation</h1>
```

## Repo-Specific Gotchas

- Headings are visually large. Do not use `##` or `###` for normal body text.
- Reveal Markdown often turns standalone images into their own paragraph blocks.
- If layout gets weird, inspect whether the issue is the Markdown structure before adding more CSS.
- Reuse existing classes in `site/reveal/assets/whimsy-theme.css` before adding one-off rules.

## Editing Workflow

1. Edit `site/reveal/slides.md`.
2. If needed, update `site/reveal/assets/whimsy-theme.css`.
3. Preview in desktop and mobile widths.
4. If you introduced a reusable pattern, note it in this file.

## Handy Starting Templates

Standard content slide:

```html
<!-- .slide: class="content-slide" -->
## Title

Short setup sentence.

- Point one
- Point two
```

Dense content slide:

```html
<!-- .slide: class="content-slide dense" -->
## Title

Paragraph text here.

Paragraph text here.
```

Image + text slide:

```html
<!-- .slide: class="content-slide" -->
## Title

<img src="/images/example.png" alt="Example" class="img-flow-right img-sm" />

- Point one
- Point two
- Point three

<div class="clear-floats"></div>
```
