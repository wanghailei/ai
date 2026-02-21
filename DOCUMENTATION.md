# DOCUMENTATION.md

## Purpose

This file defines the default documentation standards for Codex work across projects.
It keeps business understanding, schema decisions, and implementation boundaries aligned.

## Core Principles

- Document business domain first, then implementation.
- Structure by feature ownership, not by technical layer.
- Keep schema details attached to the feature they support.
- Prefer clear operational language over abstract prose.
- Include references only when they add clear value.

## Required Structure

Use this sequence unless a project has an explicit exception:

1. Purpose
2. Scope and boundaries
3. Module relationships
4. Core flow
5. Feature sections (`## Feature: ...`)
6. Delivery phases (only when needed)
7. References (optional; if included, keep last)

Rules:

- Each feature must be a `##` heading.
- Do not wrap features under a generic `## Feature Requirements` section.
- Do not create a dedicated standalone schema section.
- Put each table definition under its owning feature.
- If `## References` is included, keep it as the final section in the file.
- In references and cross-doc mentions, use documentation file names (for example `m23_procurement.md`) rather than absolute local paths.

## Data Model Requirements

When a feature introduces or changes schema, document the table in that feature section and include:

- Table intent: why this table exists in the business domain.
- Key attributes with explanatory comments for each:
	- purpose,
	- business meaning,
	- constraint intent.
- Foreign key intent: why each relationship exists.
- Index and constraint intent: what business or performance rule it protects.
- Realistic business values where helpful (including local-language examples if useful).

## Conversation Insight Capture

When documentation is updated after design discussion:

- Capture key user and assistant insights as explicit implementation constraints.
- Merge insights into related existing sections (scope, feature, validation, or process) when the discussion changes architecture or scope.
- Highlight key insight sentences using Typora highlight syntax: `==important insight==`.
- Prefer concise, decision-oriented wording so the insight can be implemented directly.

## Writing Style

- Use domain nouns and activity names that mirror real operations.
- Keep requirements testable and implementation-neutral where possible.
- Avoid UI wording in domain-level sections.
- Prefer concise wording, but keep enough detail for implementation and review.

## User Guide Experience

- For user guides, present the simplest successful start path first (minimal commands, minimal flags).
- Defer optional flags, edge cases, and advanced variants to a later subsection (for example `Advanced options`).
- Keep first-run onboarding short and confidence-building: one clear action plus expected result.
- Optimise for easy start first, then progressive exploration.

## User Guide Audience Baseline

- User guides must be written entirely from a common end-user perspective.
- Assume zero prior project context, zero maintainer context, and zero repository-internal knowledge.
- Define prerequisites, required tools, inputs, outputs, and expected results explicitly.
- Do not require local source checkout for installation or setup unless the document is explicitly contributor-focused.
- For end-user guides, use generic local path placeholders in examples: `/local/path/of/repo`, `/local/path/of/tool`.
- Use generic remote placeholders in examples: `<owner>/<repo>`.
- Never use machine-specific local paths in user-facing docs (`/home/...`, `C:\Users\...`, or equivalent absolute home paths).
- For contributor-focused workflow or maintainer documentation, use `~/...` home-relative paths as defined in `INTEGRATION.md`.
- ==If a user guide can only be followed by the author, it is invalid and must be rewritten for a first-time user.==

## Path Naming Log

- Date: 2026-02-17
- Change: standardised user-facing path placeholders.
- Previous local path naming observed: absolute home-path style with user-name segments, `~/Dev/...`, `~/path/of/...`.
- Previous remote naming observed: `<owner>/chronicle`.
- Current local path standard: `/local/path/of/repo`, `/local/path/of/tool`.
- Current remote path standard: `<owner>/<repo>`.

## Workflow

Before coding:

1. Prepare or update the relevant documentation first.
2. Ensure feature-first structure and schema commentary compliance.
3. Get user confirmation when requested by working agreements.

After coding:

1. Re-check documentation and schema sync.
2. If references are included, ensure they remain the final section.
3. Update only the feature sections affected by the change.
4. If design decisions changed during discussion, record them in the documentation as conversation insights.

## Quality Checklist

- Feature sections are `##` headings.
- No detached global schema section.
- Every key attribute has explanatory comments.
- Constraints and indexes include intent, not just definitions.
- If a references section is present, it is last.
- Documentation references use filename style, not absolute local paths.
- Key conversation insights are merged into related sections and highlighted with `==...==` where useful.
- User guides assume no prior background and are executable by a first-time common user.
- User guides start with the minimal viable command flow, with advanced flags/options documented later.
- User-facing examples use generic local/remote placeholders, not personal machine paths.
- When path naming conventions are corrected, previous naming and replacement standards are logged.
