<!-- It is not necessary to directly import stylesheets in each Markdown file if `settings.json` points to the correct stylesheet. However, printing Bare HTML will not include the stylesheets in `settings.json`, so while printing, the HTML link is still needed. -->
<link rel="stylesheet" href="silver.css">

<!-- Theme toggle allows for toggling of light/dark theme in browser only. This also affects the print theme in `silverine`. -->
<input type="checkbox" class="silver-theme-toggle" enabled />

# `silver`

`silver` styles Markdown essays and is built to standardize typography and styling options between VSCode in-editor previews, HTMLs printed from Markdown, and printed PDFs from HTMLs.

`silverine` optionally provides a framework to print Markdown to slides-like PDFs and render them as slides-like HTMLs.

## Usage

Include `silver.css` to get started. In Markdown/HTML, write

```html
<link rel="stylesheet" href="../silver/silver.css">
```

or write in CSS

```css
@import "../silver/silver.css";
```

Selective styles may be included similarly.

## Options

Adjust typography options by setting CSS variables manually, either globally or for a block. The following are default values defined in `silver.css`:

```css
:root,
:host {
	/*  between <p> elements. Also affects spacing around blockquote-like and header-like elements. */
	--silver-paragraph-spacing: 2em;

	/* Paragraph indent. */
	--silver-paragraph-indent: 0ch;

	/* Line height. Also affects spacing around blockquote-like and header-like elements. */
	--silver-line-height: 1.5;

	/* <hr> elements are replaced with a centered element of this content. */
	--silver-hr-content: "❄";

	/* Transitions in the HTML page are timed around this. */
	--silver-transition-time: 0;

	/* Should be set consistent to the VSCode editor font-size. Compute this by taking font-size / 16px; i.e. 1.1875 corresponds to a VSCode font-size of 16px. */
	--silver-editor-font-size: 1.1875em;
}
```

## Classes

Additional optional styling may be applied per-element by applying classes to that element in Markdown. Classes are mostly defined in `styles/markdown.css` and `selective/silverine.css` and are all prefixed with `silver-`.

## `silverine`

`silverine` is a `beamer`-like framework to translate Markdown into presentation PDFs. Start by including the selective CSS:

```html
<link rel="stylesheet" href="../silver/selective/silverine.css">
```

```css
@import "../silver/selective/silverine.css";
```

Each slide should be wrapped in `<section>`. See `selective/silverine.css` for more styling options.

## Fonts

Select fonts are specified in `styles/fonts.css`, and are fully included in `silver` under `fonts/`. Fonts are subsetted according to a conservative set of glyphs to minimize data transfer necessary.
