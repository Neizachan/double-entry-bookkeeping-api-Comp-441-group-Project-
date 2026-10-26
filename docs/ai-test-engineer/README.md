# AI Test Engineer workspace (Section 7.4 - 7.5 of the project brief)

Prerequisites: JDK 11 (PIT needs 11+ to run; project compiles to Java 8), Maven 3.6+, Python 3 + matplotlib.
Windows tip: `git config core.autocrlf true` (the upstream repo is LF, Windows checkouts show every file modified otherwise).

## Order of work (keep this commit order - it is your evidence)
1. `mvn test`  -> upstream baseline ("before AI"). Save the console summary.
2. **Fresh chat, fresh context** in your chosen AI tool. Paste prompt-inputs/P1..P4 one by one. Save the raw transcript + fill prompt-log.md.
   Put the generated classes in `src/test/java/com/yanimetaxas/bookkeeping/ai/`. Do not hand-edit them (record any deletions).
   Commit: "AI baseline v1 (unedited)".
3. Coverage of the AI suite only:  `mvn clean test -Dtest='com.yanimetaxas.bookkeeping.ai.*' ` then open `target/site/jacoco/index.html` (statement + branch). Fill weak-tests-checklist.md.
4. PIT v1:  `mvn test-compile org.pitest:pitest-maven:mutationCoverage`   -> `target/pit-reports/v1/` . Commit the report folder (`git add -f target/pit-reports/v1`).
5. Pick 8 survivors from the HTML report; fill surviving-mutants.md. Then `./docs/ai-test-engineer/apply-manual-tests.sh`, adapt tests to your 8, commit.
6. `python3 docs/ai-test-engineer/scripts/prioritise.py` -> risk ranking for the report.
7. PIT v2:  `mvn test-compile org.pitest:pitest-maven:mutationCoverage -Dpit.targetTests="com.yanimetaxas.bookkeeping.ai.*,com.yanimetaxas.bookkeeping.manual.*" -Dpit.reportsDir=target/pit-reports/v2`
8. `python3 docs/ai-test-engineer/scripts/mutation_chart.py target/pit-reports/v1/mutations.xml target/pit-reports/v2/mutations.xml`
