# Engineering status and roadmap

Status reflects the latest recorded local engineering checkpoint dated November 12, 2026. Email/calendar provider paths and other real-family connections remain unverified; the checkpoint does not imply an AWS application environment is deployed or a real-family provider account has been connected. The test count and context are in the [sanitized evidence summary](test-evidence-summary.md).

## Implemented and locally tested

- Family workspace, normalized source/item/evidence model, review and audit concepts.
- Local synthetic application workflows for inbox review, tasks, decisions, conflicts, event readiness, and preparation checklists.
- FastAPI backend and Next.js/TypeScript frontend.
- PostgreSQL-compatible migrations and locally tested tenant isolation, runtime-role, and RLS behavior.
- Restricted beta design with two fictional identities and one workspace per identity; hosted app behavior still requires deployment acceptance.
- Automated backend regression suite, frontend type check, and production build.

## Partial or account-dependent

- Provider adapter code and calendar-feed paths exist, but live account access and end-to-end coverage are not generally verified.
- Canvas support is partial and awaits institution registration and live family-account verification.
- A selected existing-calendar output path exists in the design, with separate approval controls; live staging dispatch is not active.

## Prototype or disabled

- AI extraction, prioritization, and disruption-mitigation research uses synthetic data. Production inference is disabled and the AI production quality gate has not passed.
- Real-family enrollment, external integrations in staging, child access, trusted-adult access, calendar writes, and autonomous actions remain disabled.

## Planned

- Resolve remaining container vulnerability findings and refresh image scans.
- Complete approved, restricted AWS application staging only after the security and owner decision gates are satisfied.
- Run hosted database isolation, backup/restore, rollback, session, alert-delivery, and disabled-route acceptance.
- Verify each school and activity integration against the family's actual authorized access method before claiming support.
- Continue independent AI quality evaluation only under the established protocol and approvals.
- Obtain separate approval and independent security review before any real-family or public production release.

## Release gates

Engineering tests, owner risk acceptance, independent human review, staging acceptance, and production authorization are separate gates. The owner waiver of independent review applies only to fictional-data staging and is a risk-acceptance decision, not a completed review. A public production launch would require new authorization and independent review.
