# INTERFACE.md

## Purpose

This file is the interaction entrypoint.

- It defines global interface principles.
- It points to detailed interface pattern and design files under `~/AI/INTERFACE/`.
- It should stay short; details belong in the linked files.

## Global Principles

- Prefer in-context panel interaction over page swaps.
- Use Turbo Stream as the primary transport for operational interactions.
- Keep frame ownership explicit and stable.
- Keep layout rules near their components, not in generic utility layers.
- Treat the Product module interaction architecture as the implementation baseline.

## Interface Library

UI patterns:

- [UI Pattern 01: Show to Edit](~/AI/INTERFACE/UI_PATTERN_SHOW_TO_EDIT.md)
- [UI Pattern 02: Main Side More](~/AI/INTERFACE/UI_PATTERN_MAIN_SIDE_MORE.md)
- [UI Pattern 03: Inline Editable](~/AI/INTERFACE/UI_PATTERN_INLINE_EDITABLE.md)

Design guideline:

- [Design Guidelines](~/AI/INTERFACE/DESIGN_GUIDELINES.md)

## Carbon Design System

Carbon is the design system baseline for component structure, spacing, and visual grammar:

- Use Carbon components (buttons, forms, data tables, notifications) as the default implementation layer.
- Layer the custom UI patterns (Main/Side/More, Show-to-Edit, Inline Editable) on top of Carbon primitives, not as replacements.
- Follow Carbon spacing tokens and grid conventions for layout consistency.
- When Carbon and a custom pattern conflict, the custom pattern takes precedence for interaction behaviour; Carbon takes precedence for visual styling.
- Refer to the Carbon Design System documentation for component API and accessibility standards.

## Adoption Rule

When defining or reviewing module UI architecture:

1. Read this file.
2. Apply `UI_PATTERN_MAIN_SIDE_MORE` first.
3. Apply `UI_PATTERN_SHOW_TO_EDIT` for aggregate surfaces.
4. Apply `UI_PATTERN_INLINE_EDITABLE` for field-level editing.
5. Validate against `DESIGN_GUIDELINES.md` before merge.
