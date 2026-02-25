# UI Pattern 01: Show to Edit

## Purpose

Keep read and edit in one continuous entity surface.

- Edit is a mode, not a different page.
- Operators keep record context while correcting data.

## Contract

- One aggregate owns one `_entity` partial.
- `_entity` accepts `editing` and renders read or form mode.
- `new` and `edit` render `_entity` in editing mode.
- `show` and successful `create/update` render `_entity` in read mode.
- Validation failure keeps the same `_entity` in editing mode with errors.

## Turbo Stream Response Shape

- `show.turbo_stream`: render read mode surface, clear transient notices.
- `new/edit.turbo_stream`: render editing surface.
- `create/update` success: render read surface, sync main list item, show success notice.
- `create/update` failure: keep editing surface, show local errors, show error notice.

## Guardrails

- Do not split normal flow into separate conceptual “view page” and “edit page”.
- Keep HTML fallback behaviour semantically identical.
- If a field is readable but non-editable, render explicit non-editable state.
