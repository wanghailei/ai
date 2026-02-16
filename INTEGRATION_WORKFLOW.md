# INTEGRATION_WORKFLOW.md

## Ownership
- This file defines shared workflow policy across projects that load `~/AI/AGENTS.md`.
- This workflow applies by default in every repository you work on, unless that repository defines stricter local rules.
- Repository docs should keep only repository-specific profile details and reference this file for shared workflow rules.

## Branch and Scope
- Every feature or module thread must declare one scope and one branch.
- Before edits and before commits, check branch and changed paths for scope match.
- Only commit scope-matching files; mixed files are blocked until split.
- Trigger split or re-branch planning when mixed domain or feature scope appears in one branch, multiple independent intents appear in one diff, or scope integrity is flagged by local guardrails.

## Commit and Push
- Keep commits small and scoped by feature or function.
- Commit splits should mainly follow business logic and feature logic.
- Docs and code may be committed together when they belong to the same domain or feature scope.
- Push each commit to GitHub immediately after commit; avoid long-lived local-only commits.
- Open PRs early and merge frequently once checks pass to prevent branch drift.
- After each merge, switch to `main` and fast-forward from `github/main`.
- Houseclean branches frequently: delete merged local or remote branches and keep stash near zero.
- Never delete local main or master or remote main or master refs (`main`, `master`, `github/main`, `github/master`, `origin/main`, `origin/master`) under any circumstances.
- If a repository provides `bin/gatekeeper`, use it regularly for audit and housekeeping cadence.

## Review Workflow
- Before merge recommendation, read the current local or CI review report artifacts required by the repository workflow.
- By default for any active PR, read unresolved review threads (including Copilot, ChatGPT or Codex, Claude, and Gemini), summarise required refinements, implement agreed fixes, and reply on resolved threads with a `Codex:` prefix before merge recommendation.
- After required checks turn green, run unresolved-thread sweeps using a convergence rule: capture unresolved-thread count plus latest thread activity marker, then poll again and continue until two consecutive snapshots are identical.
- Merge only when the converged snapshot reports zero unresolved review threads and no blocking findings remain.
- Do not treat green checks or `mergeStateStatus: CLEAN` as sufficient if unresolved review threads remain.
- If review state is attention (for example unresolved review comments, failing checks, or pending required checks), stop and discuss with the user before merge recommendation.
- In documentation and workflow examples, prefer `~/...` style for home-relative paths instead of machine-specific `/Users/...` paths.

## AI Review Panel
- Copilot is best for repository-native automated review and quick static feedback.
- ChatGPT/Codex is best for implementation reasoning, defect surfacing, and patch proposals.
- Claude is best for adversarial edge-case and safety-oriented critique.
- Gemini is best for alternative domain reasoning and consistency checks.
- Use model disagreement as a signal to tighten requirements and test coverage.

## Finding Disposition Discipline
- Every non-trivial AI finding must be tracked as one of: `accepted`, `rejected`, or `deferred`.
- `accepted`: implemented in the current PR.
- `rejected`: not adopted, with explicit rationale.
- `deferred`: intentionally postponed, with follow-up plan.

## Governance Boundary
- AI reviews are mandatory process input for quality and risk reduction.
- Merge authority remains with GitHub rulesets/checks and explicit human judgement.

## Delivery Integrity Protocol (Locked)
- Use a plan-then-apply gate: restate scope and exact files to change, then wait for explicit `Proceed` before editing.
- Apply a no-claim-without-proof rule: when stating a change is done, provide concrete file references with line numbers.
- Use diff-first reporting after edits: changed files, change summary per file, and verification commands with pass or fail status.
- No silent reversals: do not undo or alter previously agreed changes unless explicitly requested.
- If unexpected workspace changes are detected, stop immediately and ask how to proceed.
- Keep commits small and scoped to one logical change.
- Definition of done requires requested edits complete, checks run (or clear reason if not run), and reported output matching the actual diff.
