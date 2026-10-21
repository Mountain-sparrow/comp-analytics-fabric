# Comp Analytics on Fabric

A learning project: a sales compensation analytics solution built on Power BI, Microsoft Fabric and, later, an AI agent grounded on the semantic model.

**All data in this repo is fake.** Names, customers and amounts were randomly generated. No real company data is used.

## Dataset (`/data`)

| File | What it is | Rows (approx.) |
|---|---|---|
| `reps.csv` | Sales reps and managers | 23 |
| `rep_territory_history.csv` | Which territory each rep covered, and when | 21 |
| `territories.csv` | US and LATAM territories | 9 |
| `products.csv` | Product catalog with list prices | 8 |
| `deals.csv` | Opportunities closed Jan 2025 to Sep 2026 | ~2,900 |
| `quotas_wide.csv` | Monthly quota per rep, one column per month | 40 |
| `commission_plan.csv` | Tiered commission rates by role | 8 |

See `docs/data_dictionary.md` for every column.

## Commission plan rules

- Attainment = Won bookings / Quota, measured on the **fiscal year** (Jan to Dec).
- Rates are **marginal tiers**, like income tax brackets. Example for an Account Executive with 120% attainment: the first 50% of quota earns 3%, the next 50% earns 5%, the last 20% earns 8%.
- Accelerators kick in above 100% attainment.
- Deals with Status `Cancelled` were paid, then cancelled. Commission on them must be **clawed back** in the month of the CancelDate.
- Commission is paid in the month of the **PaymentDate**, not the CloseDate.
- Managers (Role = Sales Manager) carry no quota in this dataset.

## Progress log

| Week | What I built |
|---|---|
| 0 | Repo + dataset |
