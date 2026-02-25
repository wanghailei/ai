# INTEGRATION.md

## Ownership
- This file defines shared workflow policy across projects that load `~/AI/AGENTS.md`.
- This is the default workflow, which can be overridden by repository-specific rules.
- Repository docs should keep only repository-specific profile details and reference this file for shared workflow rules.

## Branch and Scope
- Every feature or module thread must declare one scope and one branch.
- Branch preflight is a hard gate before the first file edit in every thread.
- Run `git branch --show-current` in the target repository before any write command (`apply_patch`, redirection, in-place edit, or scripted file write).
- If `git branch --show-current` returns empty output (detached HEAD), stop immediately and create/switch to `codex/<scope>` before any edits.
- If the active branch is `main` or `master`, stop immediately and create/switch to `codex/<scope>` before any edits.
- After switching, declare `Scope: <scope>; Branch: <branch>` before implementation.
- Re-run `git branch --show-current` immediately before the first write command; if it does not match the declared branch, stop and realign.
- Before edits and before commits, check branch and changed paths for scope match.
- Only commit scope-matching files; mixed files are blocked until split.
- Trigger split or re-branch planning when mixed domain or feature scope appears in one branch, multiple independent intents appear in one diff, or scope integrity is flagged by local guardrails.
- If accidental edits occur on `main` or `master`, recover immediately by reverting those edits on the protected branch and recreating them on a scoped branch.

## Commit and Push
- Keep commits small and scoped by feature or function.
- Commit splits should mainly follow business logic and feature logic.
- Docs and code may be committed together when they belong to the same domain or feature scope.
- Push each commit to GitHub immediately after commit; avoid long-lived local-only commits.
- Open PRs early and merge frequently once checks pass to prevent branch drift.
- Do not use squash merge for scoped work; preserve meaningful commit boundaries.
- Default to rebase merge for PR integration.
- For `gh pr create` and `gh pr edit`, never pass long markdown bodies directly via shell-quoted `--body` arguments.
- Always write PR title/body text to a temporary file first, then submit with `--body-file` to prevent shell expansion (for example backticks, `$()`, or backslashes).
- Use a single-quoted heredoc delimiter when preparing PR body files (for example `cat <<'EOF'`) so body content remains literal.
- Integration and delivery are separate concerns: integrate frequently, release only when delivery criteria are met.
- Do not create release-only branches or PRs solely for tagging or release publication.
- Do not include version identifiers in branch names, PR titles, or PR descriptions.
- Version identifiers include semantic-version-like or tag-like markers (for example: `v1`, `v1.2.3`, `1.2.3`, `1-2-3`).
- Keep integration naming scoped to behaviour, intent, or boundary (for example: `codex/tool/review-gate-hardening`).
- After each merge, switch to `main` and fast-forward from `github/main`.
- Houseclean branches frequently: delete merged local or remote branches and keep stash near zero.
- Never delete local main or master or remote main or master refs (`main`, `master`, `github/main`, `github/master`, `origin/main`, `origin/master`) under any circumstances.
- If a repository provides `bin/butler`, use it regularly for audit and housekeeping cadence.

## Review Workflow
- Before merge recommendation, read the current local or CI review report artifacts required by the repository workflow.
- By default for any active PR, read unresolved review threads (including Copilot, ChatGPT or Codex, Claude, and Gemini), summarise required refinements, implement agreed fixes, and reply on resolved threads with a `Codex:` prefix before merge recommendation.
- After required checks turn green, run unresolved-thread sweeps using a convergence rule: capture unresolved-thread count plus latest thread activity marker, then poll again and continue until two consecutive snapshots are identical.
- Merge only when the converged snapshot reports zero unresolved review threads and no blocking findings remain.
- Do not treat green checks or `mergeStateStatus: CLEAN` as sufficient if unresolved review threads remain.
- If review state is attention (for example unresolved review comments, failing checks, or pending required checks), stop and discuss with the user before merge recommendation.
- In contributor-facing documentation and workflow examples, prefer `~/...` style for home-relative paths instead of machine-specific absolute home paths.

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
- For PR disposition comments submitted via CLI, never use escaped newline literals (`\n`) inside the body text; they are parsed as plain characters and can break automated URL matching.
- For multi-line disposition comments, use `gh pr comment --body-file <file>` so actual newline characters are preserved.
- After posting a disposition comment, run or re-check the review gate to confirm the referenced finding URL is recognised as acknowledged.

## Governance Boundary
- AI reviews are mandatory process input for quality and risk reduction.
- Merge authority remains with GitHub rulesets/checks and explicit human judgement.

## Release and Tagging Boundary
- Release/tag delivery is downstream from integration and does not require a dedicated release PR.
- A tag/release may be created only after related integration work is hygiened:
	- related PRs are merged or explicitly closed,
	- related local and remote branches are pruned,
	- local `main` is aligned to `github/main`.
- Integration may happen many times without any release.
- Keep version identifiers in tags and release-note artefacts only, never in branch names or PR metadata.

## Delivery Integrity Protocol (Locked)
- Use a plan-then-apply gate: restate scope and exact files to change, then wait for explicit `Proceed` before editing.
- Apply a no-claim-without-proof rule: when stating a change is done, provide concrete file references with line numbers.
- Use diff-first reporting after edits: changed files, change summary per file, and verification commands with pass or fail status.
- No silent reversals: do not undo or alter previously agreed changes unless explicitly requested.
- If unexpected workspace changes are detected, stop immediately and ask how to proceed.
- Keep commits small and scoped to one logical change.
- Definition of done requires requested edits complete, checks run (or clear reason if not run), and reported output matching the actual diff.
