# Hypothetical families

The unit of analysis is a family story, not an income bucket.

A family record should answer a concrete question such as:

> A student lives with a single mother who works as a flight attendant. The other parent contributes no money. What income does the aid system see, what aid is available, and can the student actually attend a particular college?

## Rules

1. Every numeric input is tagged as **measured**, **assumed**, or **calculated**.
2. Occupational earnings come from public data such as BLS OEWS and carry a SOC code, geography, source year, and wage statistic.
3. Do not equate occupational wages with AGI. Calculate AGI from an explicit tax-income record.
4. Do not infer overtime from OEWS. OEWS excludes overtime premium pay.
5. Keep `parent_money_actually_available` separate from FAFSA/SAI calculations.
6. Keep grants, scholarships, work-study, student loans, Parent PLUS, private loans, and cash contributions separate.
7. For aid calculations, match the FAFSA award year to the correct federal tax year. For example, 2026-27 FAFSA uses 2024 federal tax information.
8. Run smooth income sweeps in $5,000 increments alongside family stories so cliffs and phase-outs are visible.

## Family directory

Each family may contain:

```text
family.json        machine-readable facts and assumptions
story.md           ordinary-language account of the household
results/           college-specific aid and affordability results
sources.md         provenance for the family generator inputs
```

## Intended output

The final question is not merely `net_price`.

```text
cost_of_attendance
- grants
- scholarships
= price_after_gift_aid

parent_money_actually_available
+ student_cash_available
+ student_earnings_available
= cash_available

price_after_gift_aid
- cash_available
= financing_gap_before_debt
```

Debt options are then shown explicitly rather than counted as a reduction in price.
