# Design Guidelines

## Goal

Keep operational UIs legible, stable, and fast under frequent edits.

## Layout

- Use consistent panel rhythm and spacing contracts.
- Keep module-specific layout rules in module/component stylesheets.
- Avoid utility-layer overrides for one module’s layout behaviour.
- Avoid semantic nesting used only for spacing hacks.

## Visual Hierarchy

- Prioritise actionable information above descriptive copy.
- Keep title, status, and primary actions visible without scroll where practical.
- Use consistent status colouring and labels across modules.

## Interaction

- Make primary actions explicit and close to their data context.
- Keep filter/search/sort controls in one predictable toolbar pattern.
- Prefer icon-only actions only when label intent is unambiguous.

## Feedback

- Show success/error notices in panel foot notice areas.
- Keep validation messages local to the edited surface or field.
- Do not silently fail state transitions.

## Data-Dense Surfaces

- Use tables/lists for operational index pages, not decorative card grids.
- Maintain stable column order and naming for repeat users.
- Optimise for scan speed over ornamental layout.
