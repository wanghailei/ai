# PROJECT.md

## Purpose
This document defines how backlog, issues, and projects are managed across repositories.

Primary goal:
- Keep work items clear, small, and traceable from discovery to release result.

## Scope and boundaries
In scope:
- Backlog shaping
- GitHub Issues lifecycle
- GitHub Project workflow
- Labels, priority, size, and status conventions

Out of scope:
- Repository-specific coding rules
- PR review detail (covered by integration workflow)

## Core principles
- Issues are the source of truth for work.
- Projects are the operational view for planning and flow.
- ==Versioning describes release outcome, not feature naming.==
- One issue should represent one coherent outcome.
- Keep taxonomy light; avoid label sprawl.

## Backlog workflow
1. Capture:
- Record ideas as issues with clear problem statements.
- Avoid vague placeholders with no acceptance signal.

2. Refine:
- Add scope boundaries and acceptance criteria.
- Split oversized issues before implementation begins.

3. Prioritise:
- Use project fields (`Priority`, `Size`, `Status`) for sequencing.
- Keep priority decisions visible in the project board, not hidden in issue text.

4. Deliver:
- Move status from `Backlog` to `Work in progress` only when active.
- Move to `Done` only when merged and verified.

## Issue standard
Each feature issue should contain:
- Goal: why the work matters.
- Scope: what is in and out.
- Acceptance criteria: observable completion checks.
- Notes: optional dependencies, references, and constraints.

Issue title guidance:
- Use concise domain language.
- Do not include release tags such as `V1` in titles.
- Prefer outcome wording, not implementation wording.

## Dedicated section: Using GitHub Projects and Issues
### Role split
- `GitHub Issue`: durable record of intent, discussion, decisions, and completion.
- `GitHub Project`: planning and execution board for ordering and flow.

### What belongs in Issues
- Problem statement
- Scope and acceptance criteria
- Architecture or UX notes
- PR links and closing references

### What belongs in Project fields
- `Status` (for example: `Backlog`, `Work in progress`, `Done`)
- `Priority` (`P0` to `P3`)
- `Size` (`XS` to `XL`)
- Optional `Iteration` for time-boxed planning

### Label policy
Use a minimal, stable set:
- `feature`
- `ui`
- `design`
- `refactoring`
- `framework`
- `shell`
- `fix`

Rules:
- Labels describe work type or domain flavour.
- Do not use labels for release versions.
- Keep label count low and reusable across repositories.

### Milestones and release versioning
- Use milestones only when they reflect actual release packaging.
- Do not encode planned version in issue titles.
- Re-scope milestone assignment as release reality changes.

## Project board operating policy
- Default statuses: `Backlog`, `Work in progress`, `Done`.
- No item stays in `Work in progress` without an active owner.
- Re-evaluate `Priority` and `Size` during backlog grooming.
- Archive stale items or rewrite them with clearer outcomes.

## Definition of ready
An issue is ready when:
- Goal is explicit.
- Scope is bounded.
- Acceptance criteria are testable.
- Dependencies are known or explicitly unknown.

## Definition of done
An issue is done when:
- Implementation is merged.
- Acceptance criteria are satisfied.
- Relevant documentation is updated.
- Project status is updated to `Done`.

## Weekly cadence
1. Backlog review:
- Remove duplicates and stale items.
- Re-rank priorities.

2. Delivery review:
- Ensure active items have owners.
- Close or re-scope blocked work.

3. Release review:
- Confirm which completed items form release result.
- Update milestone/release notes from completed issues.

## Anti-patterns to avoid
- Version prefixes in feature titles.
- Large umbrella issues with no measurable completion.
- Using project fields and labels to store the same signal twice.
- Letting project status drift from actual engineering state.

## References
- `AGENTS.md`
- `INTEGRATION_WORKFLOW.md`
- `DOCUMENTATION.md`
