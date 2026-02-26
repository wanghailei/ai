# LESSONS.md

## Intent
- Preserve lesson history so corrections are traceable and promotable into durable rules.

## Usage rules
- Append only; do not rewrite historical entries except to fix factual errors.
- Add one entry per learning event.
- Keep entries concise, evidence-based, and linked to rule promotion status.
- Use home-relative paths (`~/...`) when referencing files.
- Prefer GitHub PR/commit links over local filesystem paths for evidence references.
- Entries older than six months or superseded by updated rules may be moved to a `## Archived` section.

## Entry template
Copy this block for each new lesson:

```md
### YYYY-MM-DD - <short title>
- Trigger: <user correction / escaped defect / failed check / review finding>
- Context: <scope and impacted area>
- Lesson: <trigger-condition -> required-action>
- Evidence: <error, failing check, review link, or repro note>
- Promotion target: <WORKFLOW.md / INTEGRATION.md / CODING.md / DELIVERY.md / DOCUMENTATION.md / new-topic>
- Disposition: <promoted / pending>
- Follow-up: <none or explicit next action>
```

## Entries
<!-- Append new entries below; do not modify or remove existing entries. -->

### 2026-02-23 - Repeated UI constraint must be frozen as acceptance criteria
- Trigger: user correction
- Context: BOS AI settings page implementation (`show-to-edit` requirement)
- Lesson: if a user repeats a UI pattern constraint multiple times, freeze it as non-negotiable acceptance criteria and encode that constraint in system/smoke coverage before declaring completion.
- Evidence: AI settings was initially implemented with section-level edit forms despite repeated `show-to-edit` direction; user rejected implementation.
- Promotion target: `WORKFLOW.md` and `INTERFACE.md`
- Disposition: promoted
- Follow-up: keep `test/system/ai_settings_ui_smoke_test.rb` aligned with this invariant.

### 2026-02-22 - Disposition comments must preserve real newlines
- Trigger: failed check
- Context: PR review acknowledgement workflow in Butler release PR handling
- Lesson: when posting `Codex:` disposition comments through `gh`, never embed escaped `\n` sequences; use `--body-file` or a single-line body so URL extraction and acknowledgement matching work reliably.
- Evidence: Butler governance `review gate` blocked with `unacknowledged_actionable` until disposition comment was reposted without literal `\n`.
- Promotion target: `INTEGRATION.md`
- Disposition: promoted
- Follow-up: none

### 2026-02-23 - BOS show-to-edit must use the canonical editable stack
- Trigger: user correction
- Context: AI settings UI in BOS deviated to custom `<details>` edit controls.
- Lesson: when BOS asks for `show-to-edit`, implement with the existing editable stack (`products/_entity`, `shared/_editable`, `editable_controller`) instead of inventing alternative edit interactions.
- Evidence: user rejected multiple iterations and provided the canonical reference explicitly.
- Promotion target: `INTERFACE.md`
- Disposition: promoted
- Follow-up: keep UI smoke tests asserting editable button flow (`.editable-btn-edit` -> save icon).

### 2026-02-25 - New files in ~/AI require prior user permission
- Trigger: user correction
- Context: README template guidance was added via a new standalone file (`README_TEMPLATE.md`) in `~/AI` without prior approval.
- Lesson: before creating any new file in `~/AI`, ask explicit user permission; if denied, embed required content in existing global instruction files instead.
- Evidence: user explicitly required prior permission and requested removal of the standalone template file.
- Promotion target: `AGENTS.md` and `DOCUMENTATION.md`
- Disposition: promoted
- Follow-up: none

### 2026-02-25 - Use companion folders for ~/AI supplementary files
- Trigger: user correction
- Context: supplementary template files were requested without a stable placement convention in `~/AI`.
- Lesson: when a policy file in `~/AI` needs supplementary files, place them in a companion folder named after that policy file basename (for example `DOCUMENTATION/README_TEMPLATE.md` for `DOCUMENTATION.md`).
- Evidence: user explicitly required additional files like `README_TEMPLATE.md` to live in a same-name folder (`DOCUMENTATION/`).
- Promotion target: `AGENTS.md` and `DOCUMENTATION.md`
- Disposition: promoted
- Follow-up: keep future supplementary assets out of repository root unless explicitly approved.

### 2026-02-25 - Bounded scans must fail loud at safety limits
- Trigger: review finding
- Context: Carson refactor review identified pagination caps that silently truncated data in review sweep and merged-PR evidence lookups.
- Lesson: when introducing bounded scans (pagination, retry loops, or batch windows), never silently truncate results; return an explicit limit error or partial-data status and cover that path with a targeted test.
- Evidence: review findings on Carson refactor PR — pagination caps in `data_access.rb` and `local.rb` silently truncated data.
- Promotion target: `CODING.md` and `WORKFLOW.md`
- Disposition: promoted
- Follow-up: none

### 2026-02-25 - Code reviews must capture strengths and transferable lessons
- Trigger: user correction
- Context: review output for Claude's refactor focused on defects and under-reported what should be retained.
- Lesson: for non-trivial code reviews, report findings first, then include evidence-backed strengths and explicit "what to keep" lessons so teams preserve good changes alongside fixes.
- Evidence: user feedback: "Your review report is too simple. Isn't there anything Claude did better that we can learn from it?"
- Promotion target: `WORKFLOW.md`
- Disposition: promoted
- Follow-up: none
