# COMP441 Test Plan

**Role:** Kevin — Test Lead  
**System:** Double-Entry Bookkeeping API  
**Environment:** Java 17, Maven 3.8.7; record the tested commit with each run.

## Purpose and scope
Verify monetary semantics, transfer validation, service coordination, account
boundaries, ledger behaviour, and regression safety. Testing includes unit,
integration/functional, mutation, static-analysis, and exploratory activities.
Security and external acceptance behaviour remain subject to the implemented
interfaces and authoritative requirements.

## Strategy
- **Unit/regression:** JUnit tests for monetary values, validation, currency
  grouping, boundary conditions, and service interactions.
- **Integration/functional:** exercise supported bank/account/ledger workflows.
- **Coverage:** use JaCoCo to identify unexecuted instructions and branches.
- **Mutation:** use PIT to assess assertion effectiveness; triage survivors and
  document equivalent mutants separately.
- **Static analysis:** run PMD, review findings, and preserve the report.
- **Exploratory:** use a timeboxed charter focused on transfer invariants,
  malformed inputs, boundaries, and failure handling. AI suggestions are leads,
  not evidence, until a human executes and records them.

## Environment and evidence
Record Java/Maven/tool versions, branch, commit hash, exact commands, reports,
and test totals. Do not treat historical reports as results for the final commit.

## Entry criteria
Source and dependencies are available; the intended branch and commit are
identified; tests can be run in the documented environment.

## Exit criteria
Required checks have recorded results; failures and surviving mutants are
triaged; defects have reproduction steps and regression coverage; remaining
risks and unexecuted activities are disclosed. A failed or unexecuted check
must not be marked as passed.

## Defect lifecycle
New → Triaged → Assigned → Fixed → Retested → Closed. Reopen when a regression
persists. Record severity separately from priority.

## Responsibilities
Test Lead: plan, traceability, evidence, triage, and reporting. Developers:
fix defects and provide regression tests. Reviewers: inspect evidence and
confirm release/merge gates.
