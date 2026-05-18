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

Use Release Please for repositories that publish SemVer packages, wheels, SDKs, or
other versioned artifacts. Service repositories should usually deploy immutable image
digests instead of pretending every deploy is a package release. Infrastructure
repositories should use reviewed plans and protected applies unless they publish
reusable modules consumed by version.

Organization-level release automation uses the CT Release Bot GitHub App and `CT_*`
Actions configuration. Do not create project-named handles for reusable organization
automation.
