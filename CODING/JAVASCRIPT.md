# JavaScript Style

This file contains JavaScript-specific coding rules. It supplements the universal rules in `~/AI/CODING.md`.

## General

- Plain JavaScript only; do not use TypeScript.
- Browser-only: JavaScript is used exclusively on the client side; never for server-side code.
- Do not use SPA frameworks (React, Vue, Angular, Svelte, etc.) or their ecosystems. Favour server-rendered HTML enhanced with Hotwire (Turbo + Stimulus).
- Universal spacing and formatting rules in `~/AI/CODING.md` apply to JavaScript code.

## Formatting

- No semicolons.
- Use double quotes for strings.
- Use tabs for indentation (per `~/AI/CODING.md`).

## Naming

- Use camelCase for variables, functions, and method names.
- Use PascalCase for class names and Stimulus controller classes.

## Variables

- Use `const` by default; use `let` only when reassignment is needed.
- Never use `var`.

## Functions and Classes

- Use Stimulus controllers (ES6 classes) for DOM interaction and page behaviour.
- Use plain standalone functions for utilities and helpers outside controllers.
- Prefer named function declarations over anonymous arrow functions for top-level definitions.

## Async and Server Interaction

- Prefer server-driven async via Turbo Streams and Turbo Frames over client-side fetch or XHR.
- When client-side async is unavoidable, use `async`/`await` over Promise chains or callbacks.
- Keep client-side JavaScript thin; push logic to the server where possible.

## Stimulus Conventions

- One controller per file, named to match its Stimulus identifier.
- Keep controllers focused on a single interaction concern.
- Use Stimulus values, targets, and classes for DOM binding instead of manual query selectors.
- Prefer declarative data attributes over imperative DOM manipulation.

## Linting

- No global linter is mandated yet.
- When a project adopts a linter (for example ESLint or Biome), configure it to reflect the rules in this file.
