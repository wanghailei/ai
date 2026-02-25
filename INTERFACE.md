# INTERFACE.md

## Purpose

This file is the interaction entrypoint.

- It defines global interface principles.
- It points to detailed interface pattern and design files under `./INTERFACE/`.
- It should stay short; details belong in the linked files.

## Global Principles

- Prefer in-context panel interaction over page swaps.
- Use Turbo Stream as the primary transport for operational interactions.
- Keep frame ownership explicit and stable.
- Keep layout rules near their components, not in generic utility layers.
- Treat the Product module interaction architecture as the implementation baseline.

## Interface Library

UI patterns:

- [UI Pattern 01: Show to Edit](./INTERFACE/UI_PATTERN_SHOW_TO_EDIT.md)
- [UI Pattern 02: Main Side More](./INTERFACE/UI_PATTERN_MAIN_SIDE_MORE.md)
- [UI Pattern 03: Inline Editable](./INTERFACE/UI_PATTERN_INLINE_EDITABLE.md)

Design guideline:

- [Design Guidelines](./INTERFACE/DESIGN_GUIDELINES.md)

## Adoption Rule

When defining or reviewing module UI architecture:

1. Read this file.
2. Apply `UI_PATTERN_MAIN_SIDE_MORE` first.
3. Apply `UI_PATTERN_SHOW_TO_EDIT` for aggregate surfaces.
4. Apply `UI_PATTERN_INLINE_EDITABLE` for field-level editing.
5. Validate against `DESIGN_GUIDELINES.md` before merge.
