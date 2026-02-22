# UI Pattern 02: Main Side More

## Purpose

Use three stable interaction depths for dense operational workflows.

- `main`: collection and discovery context.
- `side`: active aggregate context.
- `more`: secondary/child context.

## Shell State Contract

- Open Side: `click->shell#showSide`
- Open More: `click->shell#showMore`
- Close More: `shell#hideMore`
- Close Side: `shell#hideSide`

When loading a new Side record, close stale More context first.

## Frame Ownership Contract

- Main: `main_body_frame`
- Side: `side_head_title`, `side_neck_frame`, `side_body_frame`, `side_foot_notice`
- More: `more_head_title`, `more_neck_frame`, `more_body_frame`, `more_foot_notice`

Rule:

- Turbo Stream responses patch owned frames only.
- Avoid full-page replacement in normal panel workflows.

## Trigger and Routing Contract

- In-panel clicks (`#main`, `#side`, `#more`) should use stream-first routes (`format: :turbo_stream`).
- Links opening Side/More must include explicit shell action triggers.
- Fallback HTML may exist, but it must not introduce a different UX model.
