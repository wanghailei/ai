# AGENTS.md

Global instructions shared across projects must be maintained in `~/AI`; project repositories should keep only local profile details.

## Working Principles and Agreements
- Apply first-principles reasoning and challenge inherited practice unless it clearly earns its place.
- Design technical architecture from the North-Star end state; avoid compromised transitional architecture.
- Use British English spelling and usage in all communication and generated text.
- Ask for confirmation before editing more than 24 files in a single turn.
- Treat naming and public interfaces as high-impact decisions: always get explicit user confirmation before creating or changing names of apps, programs, CLI commands, packages, classes, modules, or public methods.
- For the `~/AI` global instruction repository, always ask explicit user permission before creating any new file.
- For supplementary files in `~/AI`, place them under a companion folder named after the owning policy file basename (for example `INTERFACE/DESIGN_GUIDELINES.md`) instead of creating standalone helper files at repository root.

## Instruction Set
- Apply `~/AI/CODING.md` for naming and coding style.
- Apply `~/AI/INTERFACE.md` for UI system and Carbon Design System implementation rules.
- Apply `~/AI/WORKFLOW.md` for execution orchestration, autonomous bug fixing, verification discipline, and core engineering principles.
- Apply `~/AI/LEARNING.md` for self-improvement loop enforcement and lesson-to-rule promotion discipline.
- Apply `~/AI/INTEGRATION.md` for branch, PR, review, and delivery workflow by default in every repository you work on, unless that repository defines stricter local rules.
- Apply `~/AI/DELIVERY.md` for test, staging, and release-validation policy.
- Apply `~/AI/PROJECT.md` for backlog, issue, and project management workflow (GitHub Issues + Projects).
- Apply `~/AI/DOCUMENTATION.md` for documentation structure and quality.

## File Map

| File | Domain |
|------|--------|
| `CODING.md` | Naming, coding style, language-specific conventions (Ruby, JavaScript, CSS) |
| `INTERFACE.md` | UI patterns (Main/Side/More, Show-to-Edit, Inline Editable), Carbon Design System, design guidelines |
| `WORKFLOW.md` | Execution orchestration, verification, bug fixing, core engineering principles |
| `LEARNING.md` | Self-improvement loop, lesson capture and promotion workflow |
| `LESSONS.md` | Append-only lesson history log |
| `INTEGRATION.md` | Branch, commit, PR, review, merge, and release-tagging workflow |
| `DELIVERY.md` | Test modes, staging, release-validation policy |
| `PROJECT.md` | Backlog, issues, GitHub Projects, labels, definitions of ready and done |
| `DOCUMENTATION.md` | Documentation surfaces, README contract, audience guidelines |

Language-specific rules in `CODING.md` and `INTERFACE.md` apply to Ruby on Rails projects by default. Other technology stacks should define local equivalents in their repository-level instructions.

## Precedence
- Apply the instruction set in the listed order.
- If rules conflict, this file wins.
