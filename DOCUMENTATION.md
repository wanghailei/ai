# DOCUMENTATION.md

## Purpose

This file defines default documentation standards for Codex work across projects.
It establishes a user-facing documentation surface and a separate internal maker surface.
These standards are defaults for downstream project or product repositories that consume `~/AI` instructions.
They are not a structural requirement for the `~/AI` global instruction repository itself.

## Core Principles

- README-first onboarding: `README.md` is the only mandatory first read for new users.
- Two-surface model: keep user docs at repository root, keep internal maker docs in `/docs`.
- Audience clarity: each document has one primary audience and one clear purpose.
- Boundary discipline: do not mix internal technical implementation detail into user docs.
- Concise value communication: opening docs should explain value quickly and clearly.

## Documentation Surfaces

### Public user surface (repository root)

Required files:

- `README.md`: user entrypoint and essential orientation.
- `MANUAL.md`: user how-to and operational guidance.
- `API.md`: user-facing API or interface reference.
- `RELEASE.md`: user-oriented release notes and release communication.

### Internal maker surface (`/docs`)

Required files:

- `docs/define.md`: product definition, feature scope, and outcome expectations.
- `docs/design.md`: UX and brand design intent only.
- `docs/develop.md`: technical architecture, implementation constraints, and developer workflow.

## Naming and Location Rules

- Keep public user documents at repository root with exact names: `README.md`, `MANUAL.md`, `API.md`, `RELEASE.md`.
- Keep internal maker documents in `/docs` using lower-case single-word names: `define.md`, `design.md`, `develop.md`.
- Do not expose internal `/docs` documents in public README navigation.
- Do not include `VERSION` in README by default unless a repository explicitly requires it for users.

## README Contract (Mandatory)

`README.md` must start with:

1. A one-sentence brief directly under the title, stating what the product is and who it is for.
2. An `## Introduction` section that concisely explains:
- the user problem,
- how the product solves it,
- why this solution is effective.

Tone requirements for `Introduction`:

- Use light credibility and concise promotional wording.
- Keep claims factual and verifiable.
- Avoid aggressive marketing language.

## Required README Structure

Use this sequence unless a project has an explicit exception:

1. Project title
2. One-sentence brief
3. `## Introduction`
4. `## Quickstart`
5. `## Where to Read Next`
6. `## Core Capabilities`
7. `## Support`

`## Where to Read Next` must link only:

- `MANUAL.md`
- `API.md`
- `RELEASE.md`

Do not link internal maker documents from this section.

## README Template (Inline)

Use the following template directly when defining project README content:

~~~md
# <Project Name>

<One sentence: what this project is and who it is for.>

## Introduction
<Concise introduction that explains:>
- <the user problem>
- <how this product solves it>
- <why this solution works well>

## Quickstart
Prerequisites:
- <minimum prerequisite 1>
- <minimum prerequisite 2>

```bash
<minimum command path to first success>
```

Expected result:
- <observable success signal>

## Where to Read Next
- User manual: `MANUAL.md`
- API reference: `API.md`
- Release notes: `RELEASE.md`

## Core Capabilities
- <capability 1>
- <capability 2>
- <capability 3>

## Support
- <issues/contact/runbook link>
~~~

## User Guide Audience Baseline

- User-facing guides must assume no prior project context.
- Define prerequisites, required tools, inputs, outputs, and expected results explicitly.
- Keep first-run onboarding short: minimum viable command path first, advanced usage later.
- Use generic path placeholders in user-facing examples:
- local: `/local/path/of/repo`, `/local/path/of/tool`
- remote: `<owner>/<repo>`

## Internal Maker Document Boundaries

- `docs/design.md` is dedicated to user experience and brand direction; avoid low-level technical architecture details.
- Put technical architecture and implementation constraints in `docs/develop.md`.
- Keep product-level intent and feature outcome definitions in `docs/define.md`.

## Workflow

Before coding:

1. Confirm which surface is being updated (public root or internal `/docs`).
2. Confirm audience and document purpose before writing.
3. For user-facing changes, start from `README.md` and ensure navigation remains accurate.

After coding:

1. Re-check link integrity for `README.md` and root user docs.
2. Ensure internal docs stay unlinked from user navigation unless explicitly required.
3. Ensure content boundaries are preserved (`design` UX/brand, `develop` technical).
4. Update only the sections affected by the actual change.

## Quality Checklist

- `README.md` contains one-sentence brief under title.
- `README.md` contains an `## Introduction` section with problem, solution, and why it works.
- `README.md` quickstart is runnable and has an expected result.
- `README.md` links `MANUAL.md`, `API.md`, and `RELEASE.md`.
- `README.md` does not expose internal `/docs` links by default.
- Root user docs exist with exact names and expected purpose.
- Internal docs exist in `/docs` with expected boundaries.
- User-facing examples avoid machine-specific absolute paths.

## Project Documentation Template (Memory)

Default project documentation template:

- Public user surface at root: `README.md`, `MANUAL.md`, `API.md`, `RELEASE.md`.
- Internal maker surface in `/docs`: `define.md`, `design.md`, `develop.md`.
- `README.md` opening contract: title -> one-sentence brief -> `## Introduction` (problem, solution, why it works).
- `README.md` user navigation contract: link only `MANUAL.md`, `API.md`, and `RELEASE.md` in the primary read-next section.
- Canonical template source: inline template under `## README Template (Inline)` in this file.

## AI Governance File Exception

For AI governance and policy files in `~/AI` (`AGENTS.md`, `WORKFLOW.md`, `LEARNING.md`, `LESSONS.md`, `INTEGRATION.md`, `DELIVERY.md`, `PROJECT.md`, `DOCUMENTATION.md`, `INTERFACE.md`):

- Do not force application feature/module templates.
- Prefer lean policy structure with operationally useful headings.
