# AGENTS.md

## Project overview

`orizinarutu-ru` is currently an empty repository. As of this writing it contains
only `README.md` (which holds just the project title) and no application code,
dependencies, tests, or build configuration.

There is intentionally no source code, package manifest (e.g. `package.json`,
`requirements.txt`, `pyproject.toml`, `go.mod`, `Cargo.toml`), lockfile, lint
config, test suite, or build system yet.

## Repository structure

- `README.md` — project title placeholder.
- `AGENTS.md` — this file.

## Conventions

- Branch naming for agent work: use the `cursor/` prefix (e.g.
  `cursor/<descriptive-name>`).
- Commit with clear, descriptive messages; create one commit per logical change.
- Do not force-push or amend commits unless explicitly asked.

## Basic engineering rules for this project

These rules are written for a beginner engineer and should keep day-to-day work
simple, safe, and efficient.

### Work style

- Start by reading the smallest relevant files before editing.
- Keep each change focused on one purpose.
- Prefer simple, readable code over clever code.
- Use existing project patterns before introducing new tools or structures.
- When requirements are unclear, write down the assumption in the PR or commit
  message instead of silently guessing.

### Before changing code

- Check `git status` so unrelated user changes are not overwritten.
- Look for an existing script or documented command before inventing a new one.
- If adding a new file or dependency, confirm it is necessary for the requested
  task.
- Avoid broad scaffolding until the project has real source code and a chosen
  stack.

### Quality checks

- Run the narrowest useful check first, then broader checks if the change has
  wider impact.
- For documentation-only changes, inspect the rendered or plain text result and
  run whitespace checks when possible.
- For code changes, run the relevant formatter, linter, tests, and build command
  once those commands exist.
- Do not claim a change is verified unless the changed path was actually checked
  by a command, test, or manual review.

### Efficiency habits

- Keep terminal commands small and repeatable.
- Prefer project scripts, such as `npm test` or `make test`, once they exist.
- Reuse common helpers instead of copying logic.
- Update documentation when adding a command, setup step, environment variable,
  or workflow that future contributors need.
- Commit one logical change at a time with a message that explains the outcome.

### Learning notes

- When a command fails, read the first actionable error before changing code.
- Fix the cause of a problem, not only the visible symptom.
- Leave short comments only where the reason is not obvious from the code.
- If a new pattern is introduced, add a short note here or in the README so it is
  easier to repeat correctly next time.

## Cursor Cloud specific instructions

- There is nothing to install, lint, test, build, or run yet: no dependency
  manifest or lockfile exists, so there is no development environment to set up.
- Do NOT fabricate a toy application, scaffold a framework, or add dependencies
  just to make setup "pass". Wait until real project code is committed.
- Once actual project code is added (with a manifest/lockfile and source), update
  this file with the concrete commands to install dependencies and to run lint,
  tests, build, and the application in development mode.
