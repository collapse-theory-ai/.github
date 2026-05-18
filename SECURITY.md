# Security Policy

Do not open public issues for vulnerabilities, leaked credentials, or access-control
problems.

For now, report security issues directly to the organization owner through a private
channel. Rotate any exposed credential immediately and document the rotation in the
affected repository.

## Baseline

- No long-lived cloud service account keys in repositories.
- Use GitHub OIDC / Workload Identity Federation for cloud access where possible.
- Keep generated `gha-creds-*.json`, `.env`, and token files out of git.
- Run secret scanning locally or in CI for repositories that can contain source code.
