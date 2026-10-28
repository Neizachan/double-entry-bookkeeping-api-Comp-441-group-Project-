# Requirements Traceability Matrix (RTM)

**Basis:** existing repository test names and documented bookkeeping behaviour.
Confirm these statements against the authoritative assignment/API specification
before submission. Test classes existing in the repository do not by themselves
prove that a requirement passed.

| ID | Requirement / acceptance criterion | Test mapping / evidence | Level | Status |
|---|---|---|---|---|
| REQ-01 | Monetary values retain correct amount and currency semantics. | `MoneyTest`, `MoneyAiTest` | Unit | Verify on final run |
| REQ-02 | Numerically balanced transaction legs are accepted regardless of decimal scale. | `DefectCandidateTest` scale/balance cases | Unit/regression | Fix and tests recorded; final run required |
| REQ-03 | Genuinely unbalanced transaction legs are rejected. | `DefectCandidateTest`, `TransferValidatorDecisionTableTest` | Unit | Verify on final run |
| REQ-04 | Legs that cancel only across different currencies are rejected as unbalanced per currency. | `TransferValidatorCurrencyTest`, `ManualMutationKillTests` | Unit | Verify on final run |
| REQ-05 | Transfer request inputs and currency constraints are validated. | `TransferRequestAiTest`, `TransferValidatorImplAiTest`, `TransferValidatorCurrencyTest` | Unit | Verify on final run |
| REQ-06 | Transfer service coordinates its collaborators correctly. | `TransferServiceImplAiTest`, `TransferServiceInteractionTest` | Unit | Verify on final run |
| REQ-07 | Account boundary behaviour is handled according to the implemented contract. | `AccountBoundaryTest` | Unit | Verify on final run |
| REQ-08 | Ledger and bank functional behaviour is exercised. | `LedgerTest`, `BankFunctionalTest`, `BankFactoryImplTest` | Unit/functional | Confirm scope and final run |
| REQ-09 | Automated checks are available to support repeatable CI verification. | `.github/workflows/ci.yml`; final Maven/CI logs | CI | Workflow exists; final branch/merge checks pending |
| REQ-10 | Test effectiveness and code quality are assessed with reproducible analysis evidence. | JaCoCo, PIT reports, `target/pmd.xml`, analysis review | Quality | PMD run: zero findings; final test/coverage/mutation evidence must be identified by commit |

## Traceability rules
- Map additional API or assignment requirements here if the authoritative
  specification contains requirements not represented above.
- Record test outcomes only after execution; preserve command, commit and report.
- The ten rows are a working test-engineering set, not a claim that the
  assignment's full specification has only ten requirements.
