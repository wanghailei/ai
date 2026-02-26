# CODING.md

## Naming
- Discuss naming choices before broad renames.
- Use domain nouns for class names.
- Keep domain names aligned to real-world concepts.
- Keep domain names concise and descriptive.
- Prefer single-word names first; use multi-word names only when extra words are required for clarity.
- Avoid UI-flavoured naming in domain/application layers unless explicitly justified.

## Coding
- Preserve existing author comments.
- Prefer plain-English code over unnecessary indirection.
- Every code file must begin with a short overview comment that states the file purpose, operating context, and key constraints.
- Use concise block comments before each major logic section so readers can follow structure without reverse-engineering intent.
- Keep implementation explanatory detail in code comments close to the logic, not only in external documentation.
- For new or generated production code, add concise comments for intent and non-obvious logic.
- For AI-agent-generated production code, add meaningful comments at module, class, and method level (especially private methods and domain logic) that explain what and why.
- For AI-agent-generated production code, also add concise explanatory comments on key non-obvious lines inside methods (for example guards, branch decisions, side-effect calls, and data transforms) so intent and reason stay explicit.
- Reuse existing repository CSS as much as possible; keep new CSS structured, modular, and reusable rather than page-specific overrides.
- Do not prefix comments with `Why:`; write direct high-quality comments that clearly explain intent and reason.
- Well-known, proven, widely trusted, and safe third-party libraries are allowed for production use.
- Ask for confirmation before adding a new dependency only when risk, maintenance burden, licensing, or security posture is unclear.
- Ask for confirmation before importing an outside library (gem, npm, pip, external package) only when the choice is not clearly standard or safe for the use case; Ruby standard-library modules are always allowed.
- The AI agent may use safe tools or libraries for execution work, as long as they are not introduced as codebase dependencies.
- Use tabs for indentation in programming languages, except where tabs are technically restricted.
- Prefer concise one-line code expressions or calls where readability is preserved; use multi-line formatting only when clarity, correctness, or tooling constraints require it.
- Keep spaces around operators (assignment, relational, range, hash rocket, exponent, etc.).
- Keep spaces inside hash braces, block braces, block pipes, and array literals where applicable.
- For method calls with arguments, use spacing like `a_method( p1, p2 )`.
- For arrays, use `[ 1, 2, 3 ]` when non-empty and `[]` when empty.
- For CSS intended to be reusable across modules or repositories, use neutral class names and never project-specific prefixes (for example `bos-`).
- Use project-prefixed CSS names only for project-specific styles that are not designed for reuse.
- Continuously distil reusable elements (for example UI primitives, utility classes, and service patterns) so code can be shared across projects with minimal adaptation.
- Extract logic only when reused, non-trivial, or cross-aggregate.
- Keep domain readability ahead of abstraction.
- Do not trade readability for encapsulation.
- When adding bounded scans (for example pagination, retries, or batch windows), never silently truncate remaining work at the limit; emit an explicit limit-reached failure or partial-result state and test that branch.

## Language-Specific Rules

- Ruby and Rails: see `~/AI/CODING/RUBY.md` and `~/AI/CODING/rubocop.yml`.
- JavaScript: see `~/AI/CODING/JAVASCRIPT.md`.
- CSS: see `~/AI/CODING/CSS.md`.
