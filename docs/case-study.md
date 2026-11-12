# Technical case study: from scattered logistics to a reviewable family plan

## The product challenge

Family logistics are distributed across email, school portals, activity apps, calendars, forms, and messages. A simple event list is not enough: families need to know where a detail came from, whether two updates refer to the same event, who should follow up, and what remains uncertain.

The product goal became a source-aware shared plan that helps families coordinate while leaving consequential choices with people.

## Architecture choices

### Python API with a TypeScript web application

FastAPI provides a typed service boundary for ingestion, normalization, authorization, and workflow operations. Next.js and TypeScript support a responsive family interface. Keeping source adapters behind the API allows each provider's permissions and limitations to be assessed separately.

### A normalized source and family-item model

Source evidence and normalized family items are different things. That distinction supports provenance, review, deduplication, correction, and audit history. Similar-looking messages are not enough to silently merge conflicting facts.

### PostgreSQL-compatible persistence and tenant boundaries

The data model targets PostgreSQL and includes tenant-isolation controls. Rather than relying only on application filters, the engineering work tests a restricted database runtime role and row-level-security behavior using a disposable PostgreSQL instance. This is local acceptance evidence; hosted RDS acceptance remains a separate step.

### Human approval before consequential action

The product separates a proposed change from an accepted change. Conflicting information, ambiguous attribution, and calendar changes remain reviewable. Production automation and autonomous actions are not enabled.

## Product and governance decisions

The product retains the family's existing email accounts and shared calendar. Integrations are added only when there is an authorized access method and a clear family use case. A planned connector is never described as a working connection.

The development process uses explicit milestones, acceptance conditions, preserved historical evidence, and separate gates for engineering, security, independent review, and production authorization. A passing automated suite does not by itself establish production quality.

## AI-assisted development

Nick Perry supplied the product direction and requirements, selected architectural boundaries, prioritized trade-offs, and set security and acceptance conditions. Coding agents contributed generated code, test scaffolding, and documentation under that direction. The owner remains responsible for deciding what evidence is sufficient and whether a capability is authorized.

AI product functionality is at an earlier stage than the surrounding application. Local synthetic-data prototypes explore extraction and obligation coverage. Production AI remains disabled; no real-family data is used for inference, and the production quality gate has not passed.

## What required redesign or extra care

- **Database acceptance:** PostgreSQL-dependent tests initially could not run because a disposable test database lacked TLS. A later run used the wrong database role for test setup. The harness was corrected to use a disposable administrator for fixtures while retaining explicit tests of the restricted application role; the final recorded suite passed.
- **Identity-provider compatibility:** the first Cognito configuration combined a user-pool tier with a token-rotation setting that the selected tier did not support. The design moved to Cognito Essentials before the replacement identity stack was created. This remained an identity-only milestone, not an application deployment.
- **Image findings:** switching from Debian Bookworm to current Debian Trixie removed Critical findings in the candidate scan, but eleven unique High OS-package CVEs remained. They were not suppressed. The application staging gate remains NO-GO until fixes arrive or the owner explicitly accepts the documented fictional-staging risk.
- **SNS encryption:** the alert design was reviewed against CloudWatch-to-SNS service permissions and uses a customer-managed key with narrow alarm-source permissions. Live delivery still requires an end-to-end test after a separately approved deployment.

These examples show why deployment status is tracked separately from implementation and test status.

## Verification snapshot

The latest local checkpoint recorded 1,069 backend tests passed, no failures, and no skipped tests, including PostgreSQL-dependent coverage. Frontend type checking and production build passed. Container smoke checks, image secret scans, CloudFormation linting/Guard, and read-only AWS template validation also passed.

The remaining High image findings, unverified live provider access, hosted backup/restore acceptance, and undelivered alarm test mean these results must not be presented as production readiness.

## Lessons

1. Preserve provenance as a first-class part of the product model.
2. Treat authorization as an end-to-end property across API, database, background work, and derived views.
3. Make the distinction between proposal, approval, and action visible in the product.
4. Treat synthetic/local test success as evidence for a narrow claim, not proof of real-world reliability.
5. Keep integrations honest: distinguish planned access, implemented code, synthetic tests, live account verification, and available service.
6. Prefer explicit stop conditions and preserved historical records over silently rewriting a milestone's status.

## Current status

dacodac is not publicly launched or production-ready. The private application remains under engineering and security review. This showcase contains selected narrative and one synthetic UI image; it does not contain the full source repository or deployment package.
