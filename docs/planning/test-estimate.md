# COMP441 Test Engineering Estimate

**Owner:** Kevin — Test Lead  
**Unit:** person-hours  
**Estimate type:** planning estimate, not measured effort.

| Work item | Estimated hours | Basis / output |
|---|---:|---|
| Review API behaviour and define 10 requirements | 1.0 | Requirement IDs and testable acceptance statements |
| Complete one-page test plan | 0.5 | Scope, strategy, environment, gates |
| Consolidate five project risks | 0.5 | Risk register with mitigations |
| Build and reconcile traceability matrix | 1.0 | Requirement-to-test mapping |
| Run PMD and document findings | 0.5 | Tool version, command, XML report and triage |
| Write symbolic execution discussion | 0.5 | Approximately half-page technical discussion |
| Conduct exploratory session and record observations | 1.5 | Charter, timebox, test notes, defects and AI co-pilot review |
| Run/review tests, coverage and mutation evidence | 1.5 | Logs, metrics, survivor classification |
| Final review, branch commit and merge verification | 1.0 | Reviewed diff and merged-branch test results |
| **Subtotal** | **8.0** | |
| Contingency (25%) | **2.0** | Unexpected failures, setup and documentation corrections |
| **Total estimate** | **10.0 hours** | |

## Assumptions and dependencies
The repository and existing test suite are available, Java/Maven are installed,
and the remote repository is accessible. The estimate assumes one test engineer
and does not include substantial production-code changes, CI redesign, external
security remediation, or waiting time for reviews. Exploratory testing and
post-merge verification must be executed before their results can be reported.
Actual effort should be recorded separately from this estimate.
