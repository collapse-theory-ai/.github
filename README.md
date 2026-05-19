# Collapse Theory AI GitHub Defaults

This repository provides organization defaults for `collapse-theory-ai`.

GitHub automatically uses supported files here, such as issue templates,
pull request templates, contributing guidance, and security policy, when a
repository does not define its own copy.

Workflow templates in `workflow-templates/` appear in the GitHub Actions "New
workflow" UI for organization repositories.

Additional files in `templates/` are copy-paste starters for new repositories and
repo-specific release configuration.

## Organization Scope

Collapse Theory AI is the organization. Ceres is the first project area.

Use `CT_*` names for organization-level automation, templates, and reusable tooling.
Use project names such as `ceres` only for project-specific repos, cloud resources,
runtime configuration, and teams.

Current org-level release automation expects:

- `CT_RELEASE_APP_ID` as an organization Actions variable.
- `CT_RELEASE_APP_PRIVATE_KEY` as an organization Actions secret.

Both should be restricted to the repositories that need the release bot.

## Recommended DevOps Stack

- Release automation: use Release Please for repos that publish SemVer packages,
  wheels, SDKs, or other versioned artifacts.
- Services and apps: build immutable container images and promote by digest. Add
  Release Please only if stable SemVer tags or GitHub Releases become part of the
  product contract.
- Infrastructure: use plan-only CI and protected/manual applies. Add Release Please
  only if a repo publishes reusable infrastructure modules consumed by version.
- Release assets: build wheels or binaries in the same workflow after Release Please
  reports that a release was created.
- Conventional Commits: enforce pull request titles in CI because squash merges
  use the PR title as the commit subject.
- Local hooks: use pre-commit for formatting, structural checks, secret scanning,
  GitHub Actions linting, and optional commit-message validation.
- Actions hygiene: run actionlint for workflow correctness and zizmor for GitHub
  Actions security findings.
- Dependency updates: keep Dependabot enabled for GitHub Actions, uv/Python, and
  Cargo. Add Renovate when a repo needs internal git-tag or GitHub Release artifact
  bumps, such as `ceres-contracts` tags or `ceres-als` wheel URLs.
- Python CI: pin both `astral-sh/setup-uv` and the uv runtime. The org reusable
  workflow defaults to uv `0.11.14` and `uv sync --locked`.
- AI review: inherit CodeRabbit from `collapse-theory-ai/coderabbit`; add a
  repo-local `.coderabbit.yaml` only for an intentional repo-specific override.

## Human-Only Merges

AI agents may create branches, commits, pull requests, and status reports, but
must not merge pull requests, approve pull requests, enable auto-merge, or push
directly to protected default branches.

Repository rulesets or branch protection should require at least one approving
human review, required status checks, linear history, and no bypass permissions
for AI automation.

## Release Please Requirements

- Enable the organization setting that allows GitHub Actions to create pull requests.
- Keep default `GITHUB_TOKEN` permissions read-only, then set explicit workflow
  permissions in release workflows.
- If release PRs must trigger required CI checks, use the CT Release Bot GitHub App
  through `CT_RELEASE_APP_ID` and `CT_RELEASE_APP_PRIVATE_KEY`.
- PR standards must allow Release Please bot branches such as
  `release-please--branches--main`.
