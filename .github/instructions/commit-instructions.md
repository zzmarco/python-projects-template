# Git Commits

When generating commit messages or committing code, strictly follow the Conventional Commits 1.0.0 specification:

## Format

`<type>(<scope>): <subject>`

`<optional body>`

`<optional footer>`

## Rules

- **Types**: Use only `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, or `revert`.
- **Scope**: Optional, lowercase noun describing the affected module or directory (e.g., `auth`, `api`, `ui`). Omit parentheses if there is no clear scope.
- **Subject**:
  - Keep under 50 characters.
  - Use imperative, present tense ("add", not "added" or "adds").
  - Do not capitalize the first letter.
  - Do not end with a period.
- **Body**:
  - Separate from the subject with a blank line.
  - Wrap lines at 72 characters.
  - Explain **what** changed and **why**, not **how**.
  - Omit the body for trivial, single-line changes.
- **Breaking Changes**: Append `!` before the colon (e.g., `feat(api)!: drop v1 endpoints`) and include a `BREAKING CHANGE:` footer explaining the migration path.
- **Issue References**: Reference related tickets in the footer (e.g., `Closes #123` or `Refs #456`).

### Example

- **Simple**: `fix(auth): prevent token expiration race condition`
- **No scope**: `docs: update local setup instructions in README`
- **With body & footer**:

  ```text
  feat(billing): add webhook retry logic

  Implement exponential backoff for failed Stripe webhook deliveries
  to prevent dropped subscription updates during network blips.

  Closes #84
  ```

Do not be too verbose. You can omit body and footer when not necessary, e.g. when changes are small and limited in scope.
