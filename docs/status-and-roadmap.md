# Engineering status and roadmap

<!-- DACODAC_AUTO_STATUS_BEGIN -->
**As of 2026-11-13:** The owner accepted a limited container-risk exception for the fictional staging pilot. No application AWS resources are deployed. Review the consolidated initial-write authorization package.
<!-- DACODAC_AUTO_STATUS_END -->

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

<!-- DACODAC_AUTO_ROADMAP_BEGIN -->
- Review the consolidated initial-write authorization for the restricted fictional staging pilot.
- If authorized, complete hosted security and operational acceptance before any application testing.
- Continue verifying school and activity integrations against approved access methods.
<!-- DACODAC_AUTO_ROADMAP_END -->



## Release gates

Engineering tests, owner risk acceptance, independent human review, staging acceptance, and production authorization are separate gates. The owner waiver of independent review applies only to fictional-data staging and is a risk-acceptance decision, not a completed review. A public production launch would require new authorization and independent review.
