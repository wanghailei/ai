# WORKFLOW.md

## Purpose
This document defines execution workflow standards for repositories that load `~/AI/AGENTS.md`.

Primary goal:
- Deliver correct, secure, and maintainable outcomes with clear evidence, low rework, and minimal user overhead.

## Scope and boundaries
In scope:
- Work planning and orchestration
- Execution discipline for non-trivial tasks
- Autonomous bug-fixing behaviour
- Verification and completion standards
- Core engineering principles for day-to-day decisions

Out of scope:
- Repository-specific coding style details (covered by `CODING.md`)
- Branch, PR, review, and merge governance rules (covered by `INTEGRATION.md`)
- Release validation policy (covered by `DELIVERY.md`)

## Workflow orchestration
### 1. Plan first for non-trivial work
- Use explicit planning for any task with three or more steps, architectural impact, or unclear requirements.
- State scope, branch, intended files, risks, and verification approach before implementation.
- Before any write operation, run `git branch --show-current` in the target repository as a mandatory preflight check.
- If the branch is `main` or `master`, create/switch to `codex/<scope>` first; editing on protected branches is forbidden.
- Immediately before the first write command, restate `Scope: <scope>; Branch: <branch>` and re-run the branch check.
- If new evidence invalidates the plan, stop and re-plan instead of forcing the original path.
- If a user repeats a constraint two or more times (for example "must use X pattern"), treat it as non-negotiable acceptance criteria and restate it before coding.

### 2. Keep execution focused
- Maintain one scope per branch and avoid mixed-intent diffs.
- Separate discovery, implementation, and verification; do not blur these phases.
- Parallelise independent reads or checks where practical, while keeping one accountable execution thread.
- Prefer the smallest viable change set that solves the root problem.

### 3. Run a self-improvement loop
- After each user correction or escaped defect, convert the lesson into a durable rule.
- Record behavioural guardrails in the most relevant global file (`WORKFLOW.md`, `CODING.md`, `INTEGRATION.md`, `DOCUMENTATION.md`, or `AGENTS.md`).
- Write rules as trigger-condition plus required action so they can be applied repeatedly.
- Revisit recent corrections at task start when they are relevant to the current scope.
- Enforce this loop through `LEARNING.md`, including capture, promotion, and completion-gate checks.

### 4. Verify before declaring done
- Never claim completion without proof.
- Validate behaviour with targeted checks (tests, lint, runtime checks, logs, or repro steps as applicable).
- For UI-pattern requirements, include at least one system/smoke test that asserts the interaction pattern itself, not only controller/model behaviour.
- When introducing safety bounds (for example pagination caps or retry ceilings), verify both normal completion and limit-reached paths so truncation cannot pass silently.
- Report what changed and how it was verified; if verification is blocked, state why and what risk remains.
- For non-trivial behaviour changes, inspect diff impact against mainline expectations.

### 5. Demand elegance, balanced with pragmatism
- Prefer simple, robust solutions over clever but fragile ones.
- For non-trivial changes, run one explicit quality pass: can this be made clearer or safer with equal or lower complexity?
- Avoid over-engineering simple fixes.

### 6. Autonomous bug fixing
- When a bug is reported, move directly to reproduce, diagnose, and fix.
- Start from concrete signals first: failing tests, stack traces, logs, runtime errors, and user repro steps.
- Fix root cause where feasible, not only symptoms.
- Add or update regression coverage when practical so the same defect is less likely to recur.
- Avoid asking the user to micromanage implementation steps unless blocked by missing access, missing data, or product-level decisions.

## Task management cadence
1. Define:
- Confirm scope and branch mapping.
- Confirm the exact files to touch.
- Run and record branch preflight (`git branch --show-current`) before the first write command.
- If preflight returns `main` or `master`, stop and switch to `codex/<scope>` before continuing.

2. Implement:
- Make scoped changes only.
- Keep commits small and intention-revealing.

3. Verify:
- Run relevant checks.
- Confirm outcomes against acceptance expectations.

4. Report:
- Summarise changed files, key behaviour changes, and verification evidence.
- For non-trivial review deliverables, report findings first, then strengths worth keeping with concrete evidence and a short transferable lesson.
- Call out risks, assumptions, or follow-up work explicitly.

5. Improve:
- Capture any correction-derived guardrails into global instructions.

## Core principles
- Simplicity first: choose the least complex change that satisfies the requirement.
- Root-cause first: diagnose why the issue exists before selecting a fix.
- Minimal impact: touch only what is necessary to avoid collateral regressions.
- Security and stability first: optimise for safe, predictable behaviour.
- Evidence over assumptions: base decisions and completion claims on observable proof.
- Clear accountability: keep scope, ownership, and decision rationale explicit.

## Definition of done
- Requested scope is fully implemented.
- Relevant verification has been executed, or a clear blocker and risk is documented.
- Documentation or rules are updated when behaviour or process expectations changed.
- Integration workflow requirements remain satisfied.

## References
- `AGENTS.md`
- `LEARNING.md`
- `CODING.md`
- `INTEGRATION.md`
- `DELIVERY.md`
- `PROJECT.md`
- `DOCUMENTATION.md`
