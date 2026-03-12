# AGENTS.md
Repository guidance for coding agents.

## Project Snapshot
- Type: static website served directly from source files.
- Stack: HTML + CSS only.
- Key files: `index.html`, `style.css`, `README.md`.
- No package manager metadata detected.
- No CI, test suite, or build config detected.

## Instruction Priority
When instructions conflict, follow this order:
1. Explicit user task instructions.
2. Existing repository code patterns.
3. This file.
4. Conservative defaults for static web projects.

## Build / Lint / Test Commands
This repo currently has no canonical build/lint/test scripts.

### Build
- Build step: none.
- Deployment model: serve static files as-is.
- Local preview command:
```bash
python3 -m http.server 8000
```
- Verify by opening `http://localhost:8000`.

### Lint
- No linter is configured in repository files.
- Optional ad hoc lint commands (only when task requires):
```bash
npx --yes htmlhint index.html
npx --yes stylelint "**/*.css"
```
- Do not add lockfiles or config just to run optional lint once.

### Test
- No automated tests are configured.
- No test runner is present.
- No test directory is present.

### Running a Single Test
- Not applicable at this time.
- If tests are introduced later, immediately document single-test commands here.
- Future examples (use only after tools are actually installed):
  - Jest: `npm test -- path/to/file.test.js -t "case name"`
  - Vitest: `npx vitest run path/to/file.test.ts -t "case name"`
  - Playwright: `npx playwright test tests/home.spec.ts --grep "hero"`

## Code Style Guidelines

### General Rules
- Keep edits small, focused, and task-specific.
- Preserve static-site architecture unless explicitly asked to change it.
- Do not introduce frameworks/build tooling by default.
- Prefer clarity and maintainability over cleverness.
- Avoid unrelated refactors.

### HTML Style
- Use semantic elements where practical (`nav`, `main`, `section`, `footer`, `address`).
- Keep valid document structure and logical heading order.
- Use lowercase tag/attribute names.
- Quote all attribute values with double quotes.
- Use 2-space indentation.
- Keep lines reasonably short when possible (target around 100 chars).
- Prefer descriptive class names for new markup.
- Keep third-party includes minimal and intentional.

### CSS Style
- Use 2-space indentation.
- Prefer class selectors over IDs and over-specific selector chains.
- Group declarations by concern: layout, spacing, typography, color.
- Keep selectors simple and reusable.
- Avoid `!important` unless absolutely necessary.
- Extend `style.css` unless there is a clear reason to split files.

### Imports and Dependencies
- There are no local module imports today.
- External assets are currently CDN-based.
- Add dependencies only when explicitly needed.
- If dependencies/tooling are added, also add documented scripts and update this file.

### Types
- No typed language is currently used.
- If TypeScript or another typed layer is added:
  - Use explicit types at public boundaries.
  - Avoid `any` when practical.
  - Keep configuration minimal and documented.

### Naming Conventions
- Filenames: lowercase, kebab-case for new files.
- CSS classes: kebab-case (`hero-title`, `contact-card`).
- IDs: only when needed for anchors/accessibility; keep unique and descriptive.
- Avoid abbreviations that reduce readability.

### Formatting
- Encoding: UTF-8.
- Preserve LF newlines.
- Ensure trailing newline at end of files.
- Remove trailing whitespace.
- Match surrounding style in edited regions.

### Error Handling and Resilience
- For static pages, prioritize graceful degradation.
- Do not rely on fragile third-party assets without considering fallback behavior.
- If JavaScript is added, handle DOM and network failures defensively.
- Never commit credentials/secrets to client-side code.

### Accessibility and UX
- Maintain keyboard-accessible interactions.
- Keep sufficient color contrast.
- Use meaningful link labels.
- Add alt text for meaningful images.
- Avoid unnecessary motion-heavy behavior.

## Agent Workflow Checklist
Before finishing a task:
1. Confirm the page renders locally with `python3 -m http.server 8000`.
2. Check for obvious HTML/CSS regressions.
3. Validate key links (especially `mailto:` links).
4. Ensure no accidental tooling/dependency changes were introduced.
5. Update this file if tooling/process changed.

## Cursor / Copilot Rule Files
Checked locations:
- `.cursorrules`
- `.cursor/rules/`
- `.github/copilot-instructions.md`

Current status:
- No Cursor rules found.
- No Copilot instructions found.
- If added later, incorporate their guidance here and treat them as higher-priority repo rules.

## Non-Goals
- Do not invent canonical scripts that do not exist.
- Do not add frameworks or build pipelines without explicit need.
- Do not perform broad refactors for narrow tasks.
- Do not remove external CDN dependencies unless safely replaced.

## Maintenance
- Keep this document aligned with the real repository state.
- Update command sections first when tooling changes.
- Prefer concrete, runnable commands over generic recommendations.
- Keep guidance repository-specific and concise.
