# Historical prepublication audit — private showcase

**Snapshot date:** November 12, 2026  
**Intended destination:** a new private GitHub repository named `dacodac-showcase`  
**Status:** Historical snapshot only. Public release was not approved at the time of this audit. Subsequent edits require a fresh review; this document does not certify the current files or approve a visibility change.

## Included files

- `.gitignore`
- `README.md`
- `architecture.mmd`
- `assets/synthetic-readiness-screen.jpg`
- `docs/architecture.md`
- `docs/case-study.md`
- `docs/portfolio-summary.md`
- `docs/status-and-roadmap.md`
- `docs/publication-audit.md`

## Excluded material

This showcase was created in a separate directory with independent Git history. It does not include the private repository's `.git` history or application source, cloud templates, deployment manifests, account identifiers, domains, credentials, secret values, databases, backups, logs, AI corpora, private annotations, or other milestone evidence packages.

No open-source license or third-party code has been included. The included screenshot is an actual local application image showing a synthetic field-trip example. It retains the internal engineering name visible in the UI; the README explains this. It contains no real family member, school, or provider account details. Metadata inspection found no creation/modification timestamp or location metadata.

## Checks performed

- Manual review of every file in the inclusion list.
- Targeted text scan for AWS account/resource identifiers, staging hostnames, private keys, common access-token patterns, passwords, and credential assignments: no matches.
- Trivy 0.76.1 filesystem secret scan: zero findings. The showcase contains no language dependency manifests or executable application code.
- Manual screenshot review; the visible event and task names are synthetic.
- No license was applied. Public release still requires owner approval.

This document records only the original November 12 prepublication snapshot. A fresh content and secret review is required after later edits and before switching repository visibility to public. No approval to change repository visibility is recorded here.
