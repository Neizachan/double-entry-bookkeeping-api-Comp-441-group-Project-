# Static Analysis Review

## Execution record
- Tool: PMD 7.17.0, invoked through Maven PMD plugin 3.28.0.
- Command: `mvn -B pmd:pmd`
- Recorded result: `BUILD SUCCESS`.
- Report: `target/pmd.xml`.
- Report timestamp: `2026-10-28T01:59:29.250`.
- Findings parsed from XML: **0**.

The XML report contains an empty PMD report element and no violations. Therefore
there are no PMD findings to rank as a top ten for this run. Do not invent
findings to satisfy a requested count. This result only describes this PMD run
and its configured rules; it does not prove the absence of defects or security
vulnerabilities. Preserve the XML alongside the command log when archiving
submission evidence. Maven emitted informational report-rendering warnings
about source cross-reference and parent-project URL; the build still succeeded.

## Review and limitations
PMD checks selected static rules without executing the program. It may not
identify business-rule errors, runtime integration failures, or all security
issues. No security-scanner result is claimed here. If another analyzer is
required by the assignment, run it separately and document its actual output.

## Symbolic execution
Symbolic execution evaluates program paths using symbolic inputs rather than
only concrete examples. For transfer validation, amounts and currencies could
be treated as symbolic values. Path constraints can represent cases such as
the sum of legs for each currency being zero, a nonzero imbalance, a missing
field, or a currency mismatch. A solver may then generate concrete values that
exercise a feasible branch, including boundary cases that ordinary examples
miss. This is particularly useful for checking arithmetic invariants and
contradictory validation conditions.

Its practical limitations include path explosion as conditions and loops grow,
constraints introduced by Java libraries, and difficulty modelling mocks,
external collaborators, and stateful behaviour. Solver models can also differ
from actual runtime semantics unless the modelling is faithful. Symbolic
execution is therefore complementary to JUnit, integration, mutation, and
exploratory testing rather than a replacement for them. No symbolic-execution
tool run is claimed in this report.
