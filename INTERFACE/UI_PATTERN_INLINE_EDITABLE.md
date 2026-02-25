# UI Pattern 03: Inline Editable

## Purpose

Enable precise single-attribute correction without leaving read context.

## Contract

- Reuse the shared editable component stack (helper + partial + Stimulus).
- Keep a clear read state and edit state in one field container.
- Editor type must match field type (text, textarea, date, relation lookup, numeric, multi-select).

## Turbo Stream Contract

- Submit includes edited attribute metadata.
- Success: replace field container in read mode; optionally refresh related list row/card.
- Failure: keep field in editing mode and render local validation errors.

## Interaction Rules

- `Escape`: cancel local edit state.
- `Enter`: save text input.
- `Ctrl/Cmd + Enter`: save textarea.

## Guardrails

- Inline editing is not a replacement for full-form aggregate edits.
- Non-editable readable fields must have explicit visual state.
- Keep patches minimal and local first.
