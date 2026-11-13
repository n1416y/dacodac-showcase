# Sanitized local test evidence summary

**Evidence date:** November 12, 2026  
**Scope:** Synthetic/local engineering only; not hosted staging or production acceptance.

## Latest recorded backend run

<!-- DACODAC_AUTO_TESTS_BEGIN -->
**Evidence date:** 2026-11-12

**Result:** PASS — 1,069 passed, 0 failed, 0 skipped.

**Additional checks:** 14 subtests passed; 2 deprecation warnings; 48.21 seconds.

**Database and scope:** Disposable local PostgreSQL with TLS; tenant and RLS guards checked. This is local synthetic-data engineering evidence, not hosted staging or production acceptance.
<!-- DACODAC_AUTO_TESTS_END -->


## Earlier run and reconciliation

An earlier full-suite run recorded 1,054 passed and 15 PostgreSQL-dependent skips because the required disposable PostgreSQL environment was not configured. The November 12 run above is the later rerun with that environment available and supersedes the earlier count for the complete local suite. The earlier result remains valid historical evidence of the incomplete run and has not been rewritten.

The skipped cases covered PostgreSQL runtime-role and RLS behavior, tenant context, projections, migration acceptance, and workspace governance. Hosted security and operational acceptance remains mandatory before any service is scaled above zero or public testing begins.

## Other local checks

The same checkpoint recorded frontend type checking and production build as passing, alongside container smoke checks, image secret scans, CloudFormation lint/Guard, and read-only AWS template validation. These checks do not establish that AWS application resources were deployed. The owner has accepted a limited container-risk exception for the fictional staging pilot only. No application resources are deployed; a fresh initial-write authorization is still pending. This is not remediation or production approval.

This summary is sanitized from the versioned engineering checkpoint. It intentionally omits local paths, credentials, account identifiers, infrastructure resource identifiers, and raw test logs.
