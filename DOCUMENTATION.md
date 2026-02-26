# DOCUMENTATION.md

## Purpose

This file defines default documentation standards for AI-agent-assisted work across projects.
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
- For supplementary files under `~/AI`, use a companion folder named after the owning policy file basename (for example `INTERFACE/` for `INTERFACE.md`).

## README Contract (Mandatory)

`README.md` must start with:

1. A one-sentence brief directly under the title, stating what the product does and why it matters.
2. A `## The Problem` section that names the user pain the product addresses in concrete, recognisable terms.
3. A `## What <Product> Does` section that explains the solution through concrete outcome blocks — each block names a capability, states what happens for the user, and shows the command or action that delivers it.

Tone requirements:

- Lead with user outcomes, not implementation details.
- Use light credibility and concise promotional wording.
- Keep claims factual and verifiable.
- Avoid aggressive marketing language.
- Name commands and actions so readers can picture themselves using the product.

## Required README Structure

Use this sequence unless a project has an explicit exception:

1. Project title
2. One-sentence brief
3. `## The Problem`
4. `## What <Product> Does`
5. `## When to Use <Product>`
6. `## Quickstart`
7. `## Where to Read Next`
8. `## Support`

`## The Problem` presents the pain the product addresses. Keep it concrete and recognisable — the reader should see their own situation in it.

`## What <Product> Does` explains the solution through bold outcome blocks. Each block has a bold heading stating the outcome, followed by one or two sentences naming the command and what it achieves. End with a clean boundary statement if the product has an explicit separation model.

`## When to Use <Product>` lists concrete scenarios where the product fits. Each scenario names a team shape or situation and explains why the product is the right tool in that context.

`## Where to Read Next` must link only:

- `MANUAL.md`
- `API.md`
- `RELEASE.md`

Do not link internal maker documents from this section.

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
- `README.md` contains `## The Problem` with concrete, recognisable user pain.
- `README.md` contains `## What <Product> Does` with outcome-oriented capability blocks.
- `README.md` contains `## When to Use <Product>` with concrete scenarios.
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
- `README.md` opening contract: title -> one-sentence brief -> `## The Problem` -> `## What <Product> Does` (outcome blocks) -> `## When to Use <Product>` (scenarios).
- `README.md` user navigation contract: link only `MANUAL.md`, `API.md`, and `RELEASE.md` in the primary read-next section.

## AI Governance File Exception

For policy files in `~/AI/` (uppercase `.md` files at repository root):

- Do not force application feature/module templates.
- Prefer lean policy structure with operationally useful headings.
