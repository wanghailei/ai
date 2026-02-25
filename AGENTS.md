# AGENTS.md

Global instructions shared across projects must be maintained in `~/AI`; project repositories should keep only local profile details.

## Working Principles and Agreements
- Apply first-principles reasoning and challenge inherited practice unless it clearly earns its place.
- Avoid aggressive coding approaches for enterprise systems; prioritise security and stability over speed or cleverness.
- Use British English spelling and usage in all communication and generated text.
- Ask for confirmation before editing more than 24 files in a single turn.
- Never modify vendor libraries or minified files.
- At the start of each thread, declare one scope and map it to one branch.
- Use `~/.cache` for temporary files and command artefacts by default (for example `~/.cache/<tool>` or `~/.cache/tmp`); use `/tmp` only as an explicit fallback when `~/.cache` is unavailable. Keep client repositories free of ad-hoc temporary directories.
- Treat naming and public interfaces as high-impact decisions: always get explicit user confirmation before creating or changing names of apps, programs, CLI commands, packages, classes, modules, or public methods.
- For the `~/AI` global instruction repository, always ask explicit user permission before creating any new file.

## Instruction Set
- Apply `~/AI/CODING.md` for naming and coding style.
- Apply `~/AI/INTERFACE.md` for UI system and Carbon Design System implementation rules.
- Apply `~/AI/WORKFLOW.md` for execution orchestration, autonomous bug fixing, verification discipline, and core engineering principles.
- Apply `~/AI/LEARNING.md` for self-improvement loop enforcement and lesson-to-rule promotion discipline.
- Apply `~/AI/INTEGRATION.md` for branch, PR, review, and delivery workflow by default in every repository you work on, unless that repository defines stricter local rules.
- Apply `~/AI/DELIVERY.md` for test, staging, and release-validation policy.
- Apply `~/AI/PROJECT.md` for backlog, issue, and project management workflow (GitHub Issues + Projects).
- Apply `~/AI/DOCUMENTATION.md` for documentation structure and quality.

## Precedence
- Apply the instruction set in the listed order.
- If rules conflict, this file wins.
