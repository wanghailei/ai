# Ruby and Rails Style

This file contains Ruby and Rails-specific coding rules. It supplements the universal rules in `~/AI/CODING.md`.

For RuboCop configuration, see `~/AI/CODING/rubocop.yml`.

## Ruby Style
- Outdent access modifiers (`private`, `protected`, `public`, `module_function`) to the same indentation level as the enclosing class/module declaration, and enforce with RuboCop `Layout/AccessModifierIndentation` using `EnforcedStyle: outdent`.
- Prefer `do...end` over `{}` for Ruby blocks.
- Avoid `elsif` where a clearer structure is possible.
- Avoid unnecessary parentheses.
- When complexity tooling (for example RuboCop `Metrics/CyclomaticComplexity`) flags a method, prefer splitting into focused helper methods instead of suppressing the rule or raising thresholds.

## Rails Style
- Keep simple, single-use Active Record query chains inline.
- Choose simple Active Record query-chain patterns over complex SQL fragments.
- Favour one-line Rails DSL declarations (for example `belongs_to`, `has_one`, `has_many`, and `enum`) when the statement remains readable.
- Only split these declarations across multiple lines when line length or clarity would otherwise suffer.
- In HTML, ERB, and XML-like templates, keep tag content on one line unless manually edited otherwise.

## File Splitting (Rails-derived)
- Split files by behaviour ownership, not by arbitrary line count.
- Keep one primary class or module responsibility per file.
- Keep file paths aligned with constant namespaces and runtime ownership boundaries.
- Keep entrypoint files thin: wiring, requires/includes, argument parsing, and dispatch only.
- Move substantive behaviour into cohesive modules under a matching subdirectory (for example `relation/*.rb` style in Rails).
- Do not keep pass-through wrapper files that only forward one call and add no policy or behaviour.
- Allow large files only when they remain one cohesive concern with tightly shared context.
- Split a file when it mixes multiple workflows, multiple external integrations, or unrelated helper clusters.
- For command systems, keep discovery and invocation centralised, and keep each real command implementation in a behaviour file with its own private helpers.
