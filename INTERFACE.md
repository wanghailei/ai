# INTERFACE.md

## Purpose

This file is the interaction entrypoint.

- It defines global interface principles.
- It points to detailed interface pattern and design files under `./Interface/`.
- It should stay short; details belong in the linked files.

## Global Principles

- Prefer in-context panel interaction over page swaps.
- Use Turbo Stream as the primary transport for operational interactions.
- Keep frame ownership explicit and stable.
- Keep layout rules near their components, not in generic utility layers.
- Treat the Product module interaction architecture as the implementation baseline.

## Interface Library

UI patterns:

- [UI Pattern 01: Show to Edit](./Interface/ui_pattern_01_show_to_edit.md)
- [UI Pattern 02: Main Side More](./Interface/ui_pattern_02_main_side_more.md)
- [UI Pattern 03: Inline Editable](./Interface/ui_pattern_03_inline_editable.md)

Design guideline:

- [Design Guidelines](./Interface/design_guidelines.md)

## Adoption Rule

When defining or reviewing module UI architecture:

1. Read this file.
2. Apply `ui_pattern_02_main_side_more` first.
3. Apply `ui_pattern_01_show_to_edit` for aggregate surfaces.
4. Apply `ui_pattern_03_inline_editable` for field-level editing.
5. Validate against `design_guidelines.md` before merge.
