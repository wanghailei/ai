# LESSONS.md

## Intent
- Preserve lesson history so corrections are traceable and promotable into durable rules.

## Usage rules
- Append only; do not rewrite historical entries except to fix factual errors.
- Add one entry per learning event.
- Keep entries concise, evidence-based, and linked to rule promotion status.
- Use home-relative paths (`~/...`) when referencing files.

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

### 2026-02-22 - Disposition comments must preserve real newlines
- Trigger: failed check
- Context: PR review acknowledgement workflow in Butler release PR handling
- Lesson: when posting `Codex:` disposition comments through `gh`, never embed escaped `\n` sequences; use `--body-file` or a single-line body so URL extraction and acknowledgement matching work reliably.
- Evidence: Butler governance `review gate` blocked with `unacknowledged_actionable` until disposition comment was reposted without literal `\n`.
- Promotion target: `INTEGRATION.md`
- Disposition: promoted
- Follow-up: none
