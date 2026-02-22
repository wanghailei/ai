# LEARNING.md

## Purpose
This document enforces the self-improvement loop for repositories that load `~/AI/AGENTS.md`.

Primary goal:
- Convert corrections and escaped defects into durable, reusable rules that reduce repeat mistakes.

## Scope and boundaries
In scope:
- Learning event detection
- Lesson distillation
- Rule promotion workflow
- Completion gate for learning actions

Out of scope:
- Repository-specific coding conventions (covered by `CODING.md`)
- Branch and PR governance (covered by `INTEGRATION.md`)
- Release validation standards (covered by `DELIVERY.md`)

## Learning trigger events
A learning event is triggered when any of the following occurs:
- A user correction changes approach, behaviour, or output expectations.
- A defect escapes and is discovered after an earlier claim of completion.
- A failed check reveals a preventable process gap.
- A review finding exposes a repeated weakness in decision-making or implementation.

## Mandatory learning workflow
1. Detect:
- Confirm whether the current task triggered a learning event.

2. Distil:
- Write the lesson in trigger-condition plus required-action format.
- Keep it specific enough to be testable in future work.

3. Place:
- Promote the lesson into the most relevant durable rule file:
  - `WORKFLOW.md` for execution and verification discipline.
  - `INTEGRATION.md` for branch, PR, and review workflow.
  - `CODING.md` for implementation and structure rules.
  - `DOCUMENTATION.md` for documentation behaviour.
  - `DELIVERY.md` for test, staging, and release validation discipline.
- If no existing file is a clean fit, add a pending promotion item to this file and propose a new topic file in `~/AI`.

4. Verify:
- Confirm the new or updated rule is clear, enforceable, and non-duplicative.

5. Report:
- State which rule file changed and why.

## Learning gate (definition-of-done extension)
- A task with a triggered learning event is not done until the lesson is either:
  - promoted into a durable rule file, or
  - logged as a pending promotion item with an explicit next action.
- Completion reporting must include a one-line learning disposition: `promoted`, `pending`, or `not-triggered`.

## Quality bar for lessons
- Root-cause aligned: addresses why the miss occurred, not only the symptom.
- Reusable: applies to future tasks with similar conditions.
- Actionable: framed as a concrete behaviour or guardrail.
- Minimal: avoids broad, vague, or contradictory rules.

## Pending promotions
- None.

## References
- `AGENTS.md`
- `WORKFLOW.md`
- `INTEGRATION.md`
- `CODING.md`
- `DELIVERY.md`
- `DOCUMENTATION.md`
