# Contributing

Use small pull requests with a clear verification trail.

## Git

- Branch names use conventional prefixes: `feat/`, `fix/`, `docs/`, `ci/`,
  `chore/`, `test/`, `refactor/`, or `build/`.
- Commit subjects and pull request titles use Conventional Commits.
- Prefer squash merges so the pull request title becomes the canonical commit
  subject on `main`.
- Keep pull requests draft until local verification has run.

## Verification

Every pull request should list the exact commands run. If a change touches cloud
infrastructure, call out cost or destructive behavior explicitly.

## Releases

Use Release Please for repositories that publish packages, images, or other
versioned artifacts. Release Please should open the version/changelog pull request;
asset builds should run from the same release workflow after the release is created.
