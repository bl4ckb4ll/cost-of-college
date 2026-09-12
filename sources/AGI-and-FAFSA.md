# AGI and FAFSA tax-year alignment

## Adjusted gross income

IRS definition: https://www.irs.gov/e-file-providers/definition-of-adjusted-gross-income

Adjusted gross income is total gross income from taxable sources minus allowable adjustments to income. It is calculated before the standard or itemized deduction. On Form 1040 it is reported on line 11.

A family generator therefore should not use `occupation_wage` as a synonym for `AGI`.

At minimum model:

```text
wages
+ taxable_interest
+ dividends
+ capital_gains
+ business_income
+ retirement_income
+ other_taxable_income
- adjustments_to_income
= AGI
```

If a hypothetical explicitly sets every non-wage item and every adjustment to zero, then AGI equals wages. That equality is a consequence of the assumptions, not a general rule.

## FAFSA

2026-27 Federal Student Aid Handbook:
https://fsapartners.ed.gov/knowledge-center/fsa-handbook/2026-2027/application-and-verification-guide/ch2-filling-out-fafsa-form

For award year 2026-27, FAFSA federal tax information comes from tax year 2024. Relevant imported information includes AGI, income earned from work, taxes paid, education credits, retirement items, tax-exempt interest, and certain schedule information.

SAI and Pell calculation documentation:
https://fsapartners.ed.gov/knowledge-center/fsa-handbook/2026-2027/application-and-verification-guide/ch3-student-aid-index-sai-and-pell-grant-eligibility

Do not calculate an aid result from a wage estimate whose year has not been aligned with the FAFSA tax year. A current BLS wage can be used to construct a current family story, but the record must be marked ineligible for a historical FAFSA run until the tax-year inputs are supplied.
