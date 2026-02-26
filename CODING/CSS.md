# CSS Style

This file contains CSS-specific coding rules. It supplements the universal rules in `~/AI/CODING.md`.

## General

- Plain CSS only; no preprocessors (Sass, Less, PostCSS) or utility frameworks (Tailwind).
- Use tabs for indentation.
- One file per concern; each file wraps its entire contents in a single named `@layer`.

## Layers

- Declare the full `@layer` order once in the entry-point stylesheet (`application.css`).
- Every project stylesheet must wrap its rules in its assigned `@layer`.
- Vendored stylesheets (for example Carbon `styles.css` and `themes.css`) occupy their own layers at the lowest priority, so project code wins without `!important`.
- Do not use `@import` for layer composition; rely on the asset pipeline for file concatenation.

## Naming

- Use kebab-case for all class names.
- Prefix module-specific classes with the module's domain name (for example `procurement-toolbar-form`, `procurement-ai-card`).
- Use `--` suffix for state or variant modifiers (for example `procurement-ai-card--critical`, `notice--error`).
- For CSS intended to be reusable across modules or repositories, use neutral class names with no project prefix.
- Use project-prefixed names only for project-specific styles not designed for reuse.
- Keep utility classes short and single-concept (for example `.hidden`, `.sticky`, `.truncated`).

## Custom Properties

- Declare global custom properties in `:root` within the entry-point stylesheet.
- Namespace project-owned tokens with the project prefix (for example `--bos-font-data-mono`).
- Consume Carbon tokens (`--cds-*`) directly; never redefine them globally.
- Scope Carbon token overrides to the specific component that needs them, not to `:root`.
- Maintain the z-index registry as a single set of `--z-*` custom properties in `:root`, grouped by tier with comment headers.
- Use `--base-*` for project-level spacing and visual primitives (for example `--base-border`, `--base-space`).

## Carbon Design System

- Treat Carbon stylesheets as vendor layers controlled by `@layer` specificity.
- Target Carbon Web Components as element selectors (for example `cds-table`, `cds-button`), not through Carbon utility classes.
- Use `::part()` selectors to penetrate Shadow DOM when Carbon's API is insufficient.
- Use Carbon tokens for all colour, spacing, and typography values in project code to stay theme-aware.
- Selectively soften Carbon defaults where the project's visual language differs (for example lighter table borders).

## Responsiveness

- Do not use `@media` breakpoints; achieve responsiveness intrinsically.
- Use `clamp()` for fluid sizing (for example column widths, card minimums).
- Use `repeat(auto-fit, minmax(..., 1fr))` for grid layouts that reflow naturally.
- Toggle layout variants by swapping classes that change `grid-template-columns` values (using `0px` to hide columns).

## Typography

- Define `@font-face` declarations and HTML element defaults in a dedicated fonts file.
- Bundle data-oriented typeface stacks into a named custom property (for example `--bos-font-data-mono`).
- Apply `font-variant-numeric: tabular-nums` and OpenType `"tnum"` / `"zero"` features on numeric-heavy elements.
- Create semantic helper classes for data display types (for example `.code`, `.money`, `.date`).

## Comments

- Begin each file with a short overview comment stating its purpose.
- Use section-header comments with a dash or asterisk separator line for visual grouping within a layer.
- Write rationale comments explaining *why* a rule exists, not *what* it does.
- Retain commented-out alternatives with a note explaining why the approach was considered and rejected.

## Linting

- No global CSS linter is mandated yet.
- When a project adopts a linter (for example Stylelint), configure it to reflect the rules in this file.
