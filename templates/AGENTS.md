# AGENTS.md

Canonical instructions for AI coding agents working in `REPO_NAME`.

## Project

- Purpose: PROJECT_DESCRIPTION
- Primary runtime: RUNTIME_DESCRIPTION
- Package manager: PACKAGE_MANAGER
- Owning team: `@collapse-theory-ai/ceres`

## Workflow

- Prefer small, reviewable changes.
- Use conventional branch prefixes such as `feat/`, `fix/`, `docs/`, `ci/`, and
  `chore/`.
- Use Conventional Commit subjects for commits and PR titles.
- Inherit CodeRabbit from `collapse-theory-ai/coderabbit`; do not add
  repo-local `.coderabbit.yaml` unless intentionally overriding org review policy.
- Keep generated runtime state, credentials, caches, and vendor artifacts out of git.
- Run the repo verification commands before claiming work is complete.
- Ask before destructive, schema-breaking, or cloud-cost-incurring actions.

## Verification

Use the commands documented in `README.md` for this repository.
