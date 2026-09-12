# Income grid

Alongside family stories, run synthetic household-income sweeps in **$5,000 increments**.

The grid is not the primary user-facing object. It is a diagnostic surface for finding:

- Pell and institutional-aid phase-outs
- abrupt eligibility cliffs
- net-price discontinuities
- places where an extra shift or overtime could reduce aid
- ranges in which nominally higher earnings leave little or no additional college-buying power

Each grid point must hold all non-income household assumptions constant unless the run explicitly varies them.

Suggested first pass:

```text
$0
$5,000
$10,000
...
$250,000
```

Do not replace this with a few cosmetically round demonstration incomes. The purpose is to observe the shape of the aid function.
