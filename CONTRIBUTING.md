# Coding Standards & Maintainability Guidelines

This document outlines the design and coding standards for this website. Because this repository is maintained exclusively by AI agents (with human oversight), strict adherence to these rules is required to ensure long-term readability, search engine accessibility, and bug-free maintenance.

---

## 1. File & Directory Structure
- All global CSS must reside in `assets/css/`.
- All images must reside in `assets/images/`, grouped into directories matching their context (e.g. `research/`, `projects/`, `creative/`).
- All PDF files, resumes, or static documents must reside in `assets/documents/`.
- Never place loose assets at the root of the project.
- Template files reside in `templates/` and are not published.

---

## 2. HTML Coding Rules
- **Indentation**: Use exactly 2 spaces for indentation. Do not use tabs.
- **Language Attribute**: Always specify `lang="en"` (or the appropriate language code) on the `<html>` element.
- **Semantic HTML**: Use native semantic tags (`<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<footer>`, `<aside>`) instead of generic `<div>` blocks.
- **Heading Hierarchy**:
  - Exactly one `<h1>` per page.
  - Headings must descend logically without skipping levels (e.g., `h1` -> `h2` -> `h3`). Never skip from `h1` to `h3` or `h4`.
- **Navigation Bar**: Every academic page must include the complete global navigation bar in the `<header>` element. Do not omit or abbreviate it on individual pages.
- **No Inline Event Handlers**: Do not use `onclick`, `onmouseover`, or any inline JS handlers.
- **No Inline Styles**: Never use the `style="..."` attribute. Use classes defined in external CSS files.
- **Accessibility**: Include alt text for all `<img>` elements. Use descriptive text (e.g., "Illustration of UCC filing structure" instead of "image").

---

## 3. CSS Coding Rules
- **Selectors**: Use descriptive, semantic class names (e.g., `.paper-header`, `.abstract-content`) instead of styling tags directly or using ID selectors.
- **Relative Pathing**: All resource references must use relative paths (e.g., `assets/css/academic.css` instead of `/assets/css/academic.css`). This ensures the site functions locally and inside subpaths on static hosts.
- **Visual Gimmicks**: Avoid scrolling animations, flashy transition libraries, animated backgrounds, custom cursors, or heavy rendering overhead. Keep layouts fast, clean, and readable.
- **Theme Variables**: Use CSS variables at the `:root` level for colors, fonts, and grid paddings to ensure design-wide consistency.

---

## 4. Sub-page & Template Conformance
- When creating a new page, it **must** copy and adapt the appropriate template file:
  - `templates/page.html` for general static pages.
  - `templates/research-page.html` for working drafts, publications, or research overviews.
  - `templates/creative-page.html` for creative writing, poetry, or satire.
- All nested sub-pages (e.g. in `research/` or `creative/`) must include a simple text-based breadcrumb line at the top of the `<main>` area for orientation (e.g., `Home > Research > Paper Title`).

---

## 5. Print Layouts
- Every page must render cleanly when printed to paper or saved as a PDF.
- Stylesheets must include a `@media print` query that:
  - Hides navigation bars, footer links, sidebars, and warning alerts.
  - Uses high-contrast black text on a pure white background.
  - Controls page-breaking behaviour (e.g., `page-break-inside: avoid` on tables, citation blocks, and figure containers).
