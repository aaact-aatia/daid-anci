# Decision 002: Title-based slugs and language switching

## Status
Accepted

## Date
2026-03-23

## Context
The site is bilingual (English and French). Each page needs a URL slug and a language toggle link pointing to its counterpart in the other language.

The initial implementation hardcoded language toggle URLs in the header partial. Every new page required editing the header template to add another `if/else` branch mapping the page to its translation. This approach does not scale, is error-prone, and blocks content authors from adding pages without developer intervention.

We needed an approach that:

- Derives URLs from page titles automatically
- Generates language toggle links without a lookup table
- Requires only front matter fields that a CMS (DecapCMS) can expose as simple text inputs
- Matches the proven pattern used on the gc-da11yn Digital Accessibility Toolkit site

## Decision
Use a `stripTagsSlugify` filter to derive both the page permalink and the language toggle URL from page titles.

### How it works

1. **Permalinks** are computed in the directory data files (`en.json`, `fr.json`):
   ```
   "permalink": "/{{ lang }}/{{ title | stripTagsSlugify }}/"
   ```
   Homepages override this with an explicit `permalink` in their front matter.

2. **Language toggle URLs** are computed in the header partial from an `otherLanguageTitle` front matter field — the title of the same page in the other language:
   ```
   langHref = "/" + otherLang + "/" + (otherLanguageTitle | stripTagsSlugify) + "/"
   ```
   If `otherLanguageTitle` is not set and the page is not a homepage, the language toggle link is omitted entirely from the header. This prevents broken links for pages that don't yet have a translation.

3. **The `stripTagsSlugify` filter** strips HTML tags (via `string-strip-html`), transliterates French accented characters to ASCII, converts apostrophes (straight and curly) to spaces so they act as word boundaries, removes remaining non-alphanumeric characters, and hyphenates. This ensures the same filter produces matching, readable slugs on both sides of the language pair.

### Front matter for authors

| Field | Required | Purpose |
|---|---|---|
| `title` | Always | Page heading, slug source, `<title>` tag |
| `description` | Always | Below-heading summary text, meta description |
| `otherLanguageTitle` | Non-homepages | Other-language page title — generates the language toggle URL. If omitted, the language toggle is hidden. |
| `permalink` | Homepages only | Override to keep `/en/` and `/fr/` instead of a slugified title |

### Example

English about page (`src/en/about/index.njk`):
```yaml
title: About DAID
description: ...
otherLanguageTitle: A propos d'ANCI
```

- Permalink: `/en/about-daid/`
- Language toggle: `/fr/a-propos-d-anci/`

## Rationale
The title is the single source of truth for both the URL and the cross-language link. Adding a new page requires only setting `title`, `description`, and `otherLanguageTitle` in front matter. No template files need to be edited.

This matches the pattern used on the [gc-da11yn Digital Accessibility Toolkit](https://github.com/gc-da11yn/gc-da11yn.github.io), which uses the same `stripTagsSlugify` filter and `string-strip-html` package. Keeping the same convention across projects reduces context switching for maintainers working on both sites.

The `string-strip-html` package (v8, CommonJS-compatible) handles HTML stripping more robustly than a simple regex, which matters when titles may contain inline markup from a CMS.

## Implications
Page URLs are determined by their titles. Changing a title changes its URL. This is acceptable at this stage since the site is not yet public. Once live, title changes should be coordinated with redirects.

The `otherLanguageTitle` field must exactly match the other-language page's `title` for the slugified URLs to align. A mismatch produces a broken language toggle link. This is a trade-off for not requiring a centralized translation map.

Breadcrumbs in the header partial are now automatic for any non-homepage page, using `page.url` and `title`. No per-page breadcrumb configuration is needed.

## Notes
This decision is aligned with the planned DecapCMS integration (Phase 15+), where `title`, `description`, and `otherLanguageTitle` will be exposed as simple text widgets in the content editor.
