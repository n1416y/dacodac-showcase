# Sanitized local test evidence summary

**Evidence date:** November 12, 2026  
**Scope:** Synthetic/local engineering only; not hosted staging or production acceptance.

## Latest recorded backend run

- Result: PASS
- Backend tests: 1,069 passed, 0 failed, 0 skipped
- Additional subtests: 14 passed
- Warnings: 43; recorded as Starlette/httpx `TestClient` and Alembic `path_separator` deprecations
- Duration: 48.21 seconds
- Database: disposable local PostgreSQL 16.15, loopback-only, TLS required
- Database setup: migrations applied; the runtime role was verified as a non-superuser without `BYPASSRLS`; the tenant signing key was seeded; RLS guard and runtime TLS checks passed
- Cleanup: disposable database container and network, temporary credential file, and test certificate were removed

The final full-suite attempt configured PostgreSQL fixtures through the disposable database administrator URL while retaining explicit tests of the restricted application runtime role. All 1,069 tests passed. This demonstrates local test coverage under that harness; it does not substitute for hosted RDS, deployment, restore, alert-delivery, or production acceptance.

## Earlier run and reconciliation

An earlier full-suite run recorded 1,054 passed and 15 PostgreSQL-dependent skips because the required disposable PostgreSQL environment was not configured. The November 12 run above is the later rerun with that environment available and supersedes the earlier count for the complete local suite. The earlier result remains valid historical evidence of the incomplete run and has not been rewritten.

The skipped cases covered PostgreSQL runtime-role and RLS behavior, tenant context, projections, migration acceptance, and workspace governance. Hosted security and operational acceptance remains mandatory before any service is scaled above zero or public testing begins.

## Other local checks

The same checkpoint recorded frontend type checking and production build as passing, alongside container smoke checks, image secret scans, CloudFormation lint/Guard, and read-only AWS template validation. These checks do not establish that AWS application resources were deployed. The remaining container OS High findings keep application staging at NO-GO unless remediated or separately accepted within the approved fictional-staging scope.

This summary is sanitized from the versioned engineering checkpoint. It intentionally omits local paths, credentials, account identifiers, infrastructure resource identifiers, and raw test logs.
