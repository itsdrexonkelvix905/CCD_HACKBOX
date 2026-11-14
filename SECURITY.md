
# Security Policy

## About CCD_HACKBOX

CCD_HACKBOX is an intentionally vulnerable Linux training environment.

Its vulnerabilities are included for educational purposes and are not intended for deployment on production systems.

## Supported Scope

Security reports may cover:

- Accidental exposure of project secrets.
- Unsafe default network configurations.
- Unintended access outside the intended lab.
- Vulnerabilities in project deployment scripts.
- Issues affecting the isolation of the training environment.
- Unintended exposure of instructor-only materials.

## Reporting a Security Issue

Do not publish sensitive security findings, credentials, private keys or challenge flags in public issues.

Report security concerns privately to the project maintainers through an appropriate private communication channel.

Include:

- A description of the issue.
- Affected component.
- Steps to reproduce safely.
- Potential impact.
- Suggested mitigation, if available.

## Security Requirements

Users should:

1. Run CCD_HACKBOX in an isolated virtual environment.
2. Prefer Host-only networking for local exercises.
3. Avoid exposing vulnerable services to public networks.
4. Never reuse personal or production credentials.
5. Keep instructor-only materials private.
6. Take VM snapshots before making significant changes.

## Important Notice

The intentionally vulnerable services inside CCD_HACKBOX are part of the training design.

Do not interpret the presence of a vulnerable service as a recommendation to deploy it in a production environment.

## Responsible Use

All activities must be conducted on systems for which the user has explicit authorization.
