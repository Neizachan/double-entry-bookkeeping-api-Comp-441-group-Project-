# Flagging weak AI tests (Section 7.4, bullet 2)
For every AI test method, tick one category. Anything in B-E goes in the report's "weak tests" table.
A. Meaningful   - asserts a specific value/state/exception type
B. No-oracle    - only "does not throw", or `assertNotNull(x)` on something that can't be null
C. Loose        - `assertTrue(result != null)`, `size() > 0`, `contains` where equality is expected
D. Tautology    - asserts the mock returns what you just stubbed; no behaviour under test
E. Missing boundary - happy path only (e.g. only balances like 100.00, never 0.00 / -0.01)
Quick grep:  grep -rnE "assertNotNull|assertTrue\(.*(!= null|> 0)\)|@Test\s*$" src/test/java/**/ai
Coverage: mvn jacoco needs adding; or `mvn cobertura:cobertura` (already in pom). Report statement + BRANCH %.
