# Latest clean PIT mutation run

Source report: `target/pit-reports/v2/mutations.xml`

The report was copied after the clean PIT rerun on 28 October 2026.
The run generated 251 mutations, killed 250, left one equivalent
survivor, and reported zero uncovered mutations. PIT displayed test
strength as 99%; the exact killed fraction is 250/251 (approximately
99.6%).

The surviving mutant replaces `BigDecimal.add` with `BigDecimal.subtract`
in `TransferValidatorImpl.checkTransactionLegsBalanced`. Because the
accumulated total is checked only for whether it equals zero, negating
the total does not change the verdict. This mutant is treated as
equivalent, not as an untested defect.

The older v1 and v2 archives are historical results and are retained
separately.
