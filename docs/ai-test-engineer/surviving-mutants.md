# Surviving mutants - v1 (fill from target/pit-reports/v1/index.html)
Write the "why missed" column in your own words (brief Section 11).

| # | Class:line | PIT mutator | Mutation (from report) | Why the AI tests missed it | Manual test that kills it | Design technique |
|---|-----------|-------------|------------------------|----------------------------|---------------------------|------------------|
| 1 | | | | | | |
| 2 | | | | | | |
| 3 | | | | | | |
| 4 | | | | | | |
| 5 | | | | | | |
| 6 | | | | | | |
| 7 | | | | | | |
| 8 | | | | | | |

Equivalent mutants found (exclude from score reasoning, explain): e.g. TransferValidatorImpl `sum.add` -> `sum.subtract` (sum negated, zero iff sum zero).

## Where to look first (candidates, unconfirmed)
Account.isOverdrawn boundary; TransferValidatorImpl `size() < 2` and `type == null`; per-currency balance check;
validBalance overdraft check; TransferServiceImpl void calls (updateBalance, validBalance, storeTransaction) and `refs.isEmpty()`.
Staged manual tests that target these: staged-manual-tests/ (S1-S9 mapping in the test class comments).
