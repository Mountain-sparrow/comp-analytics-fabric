# Answer key (don't peek until you've finished Week 1 cleaning)

The data has deliberate problems for Power Query practice. You should find all of these:

1. **Wide quota table.** `quotas_wide.csv` has one column per month. Unpivot it into RepID | FiscalYear | Month | Quota, then build a real date.
2. **Messy rep names.** Three names have leading/trailing spaces or wrong capitalisation. Trim + Capitalize Each Word.
3. **Amounts stored as text.** About 40 rows in `deals.csv` have Amount_USD like "$12,345.00". Remove "$" and "," before changing type, or the column errors out.
4. **Inconsistent Status.** About 30 rows say "won", "WON", "Won " or " Won". Trim and fix case so there are exactly three values.
5. **Lowercase ProductIDs.** About 12 deals use "p003" instead of "P003". Relationships are case sensitive in some engines, so standardise to upper case.
6. **Duplicate deals.** 15 rows are exact duplicates. Remove duplicates on DealID.
7. **Unassigned deals.** 6 deals have a blank RepID. Decide: filter out, or map to an "Unassigned" rep. Document your choice.

Business scenarios for later weeks:

- **R103** is a new hire who started 2025-06-01 (quota is zero before that). Prorated quota test.
- **R105** moved territory on 2025-07-01 (Week 3: SCD Type 2). Which territory gets credit for which deals?
- **R110** left on 2026-04-30. Quota is zero after that. What happens to deals cancelled after he left?
- 2026 data stops at September, but quotas cover the full year. Good for "YTD attainment vs full-year quota" questions.
