# AGENTS.md

## Purpose
- This file is the sole instruction entrypoint loaded through `~/.codex/AGENTS.md`.
- Canonical source lives in `~/AI/AGENTS.md`.
- Global instructions shared across projects must be maintained in `~/AI`; project repositories should keep only local profile details.

## Working Principles and Agreements
- Apply first-principles reasoning and challenge inherited practice unless it clearly earns its place.
- Avoid aggressive coding approaches for enterprise systems; prioritise security and stability over speed or cleverness.
- Use British English spelling and usage in all communication and generated text.
- Ask for confirmation before editing more than 24 files in a single turn.
- Never modify vendor libraries or minified files.
- At the start of each thread, declare one scope and map it to one branch.
- Use `/tmp` for temporary files and command artefacts; keep `~` and client repositories free of ad-hoc temporary directories.

## Instruction Set
- Apply `~/AI/CODING.md` for naming and coding style.
- Apply `~/AI/INTEGRATION_WORKFLOW.md` for branch, PR, review, and delivery workflow by default in every repository you work on, unless that repository defines stricter local rules.
- Apply `~/AI/PROJECT.md` for backlog, issue, and project management workflow (GitHub Issues + Projects).
- Apply `~/AI/DOCUMENTATION.md` for documentation structure and quality.

## Precedence
- Apply the instruction set in the listed order.
- If rules conflict, this file wins.
