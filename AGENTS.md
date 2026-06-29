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

## Cursor Cloud specific instructions

- There is nothing to install, lint, test, build, or run yet: no dependency
  manifest or lockfile exists, so there is no development environment to set up.
- Do NOT fabricate a toy application, scaffold a framework, or add dependencies
  just to make setup "pass". Wait until real project code is committed.
- Once actual project code is added (with a manifest/lockfile and source), update
  this file with the concrete commands to install dependencies and to run lint,
  tests, build, and the application in development mode.
