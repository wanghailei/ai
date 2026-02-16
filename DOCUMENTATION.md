# DOCUMENTATION.md

## Purpose

This file defines the default documentation standards for Codex work across projects.
It keeps business understanding, schema decisions, and implementation boundaries aligned.

## Core Principles

- Document business domain first, then implementation.
- Structure by feature ownership, not by technical layer.
- Keep schema details attached to the feature they support.
- Prefer clear operational language over abstract prose.

## Required Structure

Use this sequence unless a project has an explicit exception:

1. Purpose
2. Scope and boundaries
3. Module relationships
4. Core flow
5. Feature sections (`## Feature: ...`)
6. Delivery phases (only when needed)
7. References (always last)

Rules:

- Each feature must be a `##` heading.
- Do not wrap features under a generic `## Feature Requirements` section.
- Do not create a dedicated standalone schema section.
- Put each table definition under its owning feature.
- Keep `## References` as the final section in the file.
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

## Workflow

Before coding:

1. Prepare or update the relevant documentation first.
2. Ensure feature-first structure and schema commentary compliance.
3. Get user confirmation when requested by working agreements.

After coding:

1. Re-check documentation and schema sync.
2. Ensure references remain the final section.
3. Update only the feature sections affected by the change.
4. If design decisions changed during discussion, record them in the documentation as conversation insights.

## Quality Checklist

- Feature sections are `##` headings.
- No detached global schema section.
- Every key attribute has explanatory comments.
- Constraints and indexes include intent, not just definitions.
- References section is present and last.
- Documentation references use filename style, not absolute local paths.
- Key conversation insights are merged into related sections and highlighted with `==...==` where useful.
