# Decision 001: Use native HTML for content, GCDS components for UI

## Status
Accepted

## Date
TBD

## Context
The project uses Eleventy templates for bilingual content and the GC Design System (GCDS) for shared UI patterns. We need a clear and maintainable approach for when to use native HTML and when to use GCDS components.

## Decision
Use native HTML elements (`h1`-`h6`, `p`, `ul`, `ol`) for content structure and static text.

Use GCDS components for interactive or structured UI patterns, including navigation, forms, buttons, alerts, and similar interface elements.

Keep Eleventy templates simple, readable, and maintainable by avoiding unnecessary web components for static content.

## Rationale
Native HTML provides clear semantics, low complexity, and strong baseline accessibility for content-heavy sections.

GCDS components provide consistent, accessible behavior and styling for interactive and structured UI elements.

This split supports an accessibility-first approach while reducing template complexity for a small team.

## Implications
Content pages should default to semantic HTML for headings, paragraphs, and lists.

Design-system components should be introduced where they materially improve usability, consistency, or accessibility.

Template reviews should check for unnecessary use of web components in static content sections.

## Notes
This decision is intended as a long-term guideline and can be revisited if project needs or GCDS patterns evolve.
