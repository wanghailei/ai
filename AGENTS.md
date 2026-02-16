# AGENTS.md

## Purpose
- This file is the sole instruction entrypoint loaded through `~/.codex/AGENTS.md`.
- Canonical source lives in `~/AI/AGENTS.md`.
- Default behaviour: apply `~/AI/INTEGRATION_WORKFLOW.md` in every repository you work on, unless a repository defines stricter local rules.
- Global instructions shared across projects must be maintained in `~/AI`; project repositories should keep only local profile details.

## Working Principles and Agreements
- Apply first-principles reasoning and challenge inherited practice unless it clearly earns its place.
- Avoid aggressive coding approaches for enterprise systems; prioritise security and stability over speed or cleverness.
- Use British English spelling and usage in all communication and generated text.
- Ask for confirmation before editing more than 10 files in a single turn.
- Never modify vendor libraries or minified files.
- At the start of each thread, declare one scope and map it to one branch.

## Instruction Set
- Apply `~/AI/CODING.md` for naming and coding style.
- Apply `~/AI/INTEGRATION_WORKFLOW.md` for branch, PR, review, and delivery workflow.
- Apply `~/AI/DOCUMENTATION.md` for documentation structure and quality.

## Precedence
- Apply the instruction set in the listed order.
- If rules conflict, this file wins.
