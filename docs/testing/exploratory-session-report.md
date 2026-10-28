# Exploratory Testing Session Report

## Charter
**Charter:** Explore whether transfer validation preserves monetary and
bookkeeping invariants when inputs vary from typical examples. Investigate
decimal scales, zero/positive/negative amounts where permitted, per-currency
balancing, malformed or missing fields, boundary values, repeated requests,
and failure handling.

## Session record
- Tester: Kevin (Test Lead)
- Date/time: To be recorded during execution
- Branch and commit: To be recorded at session start
- Environment: Java/Maven versions and relevant runtime configuration to record
- Timebox: 60–90 minutes
- Status: **Planned — execution evidence not yet supplied**

## Test approach and AI co-pilot
1. Start from a clean checkout and record the commit hash.
2. Use the charter to explore one risk area at a time; capture inputs, actions,
   expected results, actual results, and evidence.
3. Ask an AI co-pilot to suggest edge cases and challenge assumptions. Treat
   each suggestion as a hypothesis; execute it independently and record whether
   it was actually tested.
4. For any suspected defect, preserve a minimal reproduction, impact, logs or
   screenshots where applicable, and a candidate regression test.
5. Re-run relevant automated tests after any fix.

## Session observations

| ID | Scenario / input | Expected result | Actual result | Outcome / evidence |
|---|---|---|---|---|
| EX-01 | Equal-and-opposite amounts with different decimal scales | Accept if numerically balanced within each currency | Not yet executed | Pending |
| EX-02 | Unequal totals within one currency | Reject as unbalanced | Not yet executed | Pending |
| EX-03 | Equal-and-opposite amounts across different currencies only | Reject per-currency imbalance | Not yet executed | Pending |
| EX-04 | Missing or malformed required transfer fields | Reject safely according to API contract | Not yet executed | Pending |
| EX-05 | Repeated submission / failure handling | Observe duplicate handling and state consistency per contract | Not yet executed | Pending |

## Results and follow-up
No exploratory outcome or defect is claimed until the session is performed.
After execution, replace each pending result with observed behaviour, record
defect IDs and evidence, and distinguish confirmed defects from questions
requiring clarification. AI-generated suggestions alone are not test results.
