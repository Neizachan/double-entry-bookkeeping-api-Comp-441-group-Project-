# COMP441 Risk Register

Likelihood and impact use Low / Medium / High. Ratings are qualitative and
should be revisited when new evidence becomes available.

| ID | Risk | Likelihood | Impact | Mitigation / contingency | Owner / status |
|---|---|---|---|---|---|
| R1 | Monetary or currency validation accepts an invalid transfer or rejects a numerically balanced one. | Medium | High | Test scale variants, genuine imbalance, and cross-currency cancellation; retain regression tests. | Test Lead + developer; regression tests exist, final run required |
| R2 | Tests miss defects despite a passing unit suite. | Medium | High | Review JaCoCo and PIT evidence; classify survivors, including equivalent mutants; add targeted tests for killable mutants. | Test Lead; latest clean PIT evidence recorded, rerun on final commit |
| R3 | CI or local verification is not reproducible on the merge target. | Medium | High | Run `mvn -B clean verify` on the branch and again after merge; capture logs and commit IDs. | Test Lead / CI owner; final merged run pending |
| R4 | Security, authorization, or failure-handling weaknesses are not covered by the available analysis. | Medium | High | Review threat model and supported API boundaries; run an appropriate security scanner and triage its actual output. | Security reviewer; security scan pending |
| R5 | Incomplete or stale evidence causes unsupported submission claims or missed work. | High | High | Maintain ten-item RTM, versioned reports, a task estimate, and an explicit pending/completed status for exploratory testing. | Kevin, Test Lead; documentation audit in progress |

**Review rule:** A risk is not closed solely because a document or test class exists.
Record execution evidence and reassess residual risk.
