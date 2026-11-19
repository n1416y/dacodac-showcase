# Sanitized local test evidence summary

**Evidence date:** November 19, 2026  
**Scope:** Synthetic/local engineering only; not hosted staging or production acceptance.

## Latest recorded backend run

<!-- DACODAC_AUTO_TESTS_BEGIN -->
**Evidence date:** 2026-11-19

**Result:** PASS — 1,209 passed, 0 failed, 2 skipped.

**Additional checks:** 14 subtests passed; 43 warnings; 53.75 seconds. The I11 profile/runner suite passed 32 tests; the complete synthetic family browser journey passed 1 Playwright test. The focused local intake-checkpoint suite passed 11 tests; Ruff passed for the changed I11 and collector files.

**Database and scope:** Disposable local PostgreSQL 16.15, bound to loopback with temporary storage. The two skips were workstation-database-presence checks; PostgreSQL-specific acceptance ran. This is local synthetic-data engineering evidence, not hosted staging or production acceptance.
<!-- DACODAC_AUTO_TESTS_END -->


## Earlier runs and reconciliation

An earlier environment-limited run recorded 1,054 passed and 15 PostgreSQL-dependent skips. The prior public summary reported 1,069 passed and no skips; this newer November 19 result supersedes that summary. Earlier results remain historical and are not rewritten.

The two skips in the current run are workstation-database-presence checks. PostgreSQL-specific runtime-role, RLS, tenant-isolation and migration acceptance ran against the disposable local database. Hosted security and operational acceptance remains mandatory before public staging testing or any service is scaled above zero.

## Other local checks

A separate November 12 checkpoint recorded frontend type checking and production build, container smoke checks, image secret scans, CloudFormation lint/Guard, and read-only AWS template validation. Those checks do not establish that application resources were deployed. Current AWS application staging remains NO-GO; no application resources are deployed. This is not production approval.

This summary is sanitized from the versioned engineering checkpoint. It intentionally omits local paths, credentials, account identifiers, infrastructure resource identifiers, and raw test logs.
