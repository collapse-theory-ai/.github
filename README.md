# Collapse Theory AI GitHub Defaults

This repository provides organization defaults for `collapse-theory-ai`.

GitHub automatically uses supported files here, such as issue templates,
pull request templates, contributing guidance, and security policy, when a
repository does not define its own copy.

Workflow templates in `workflow-templates/` appear in the GitHub Actions "New
workflow" UI for organization repositories.

Additional files in `templates/` are copy-paste starters for new repositories and
repo-specific release configuration.

## Recommended DevOps Stack

- Release automation: use Release Please for version bumps, changelog generation,
  release PRs, tags, and GitHub Releases.
- Release assets: build wheels, images, or binaries in the same workflow after
  Release Please reports that a release was created.
- Conventional Commits: enforce pull request titles in CI because squash merges
  use the PR title as the commit subject.
- Local hooks: use pre-commit for formatting, structural checks, secret scanning,
  GitHub Actions linting, and optional commit-message validation.
- Actions hygiene: run actionlint for workflow correctness and zizmor for GitHub
  Actions security findings.
- Dependency updates: keep Dependabot enabled for GitHub Actions, uv/Python, and
  Cargo unless a repo needs Renovate's grouping or custom scheduling.
