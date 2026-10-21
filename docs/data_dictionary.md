# Data dictionary

## reps.csv
| Column | Description |
|---|---|
| RepID | Unique rep ID. Managers are R100, R200, R300 |
| RepName | Full name |
| Email | Fake email |
| Role | Account Executive, Senior Account Executive, Sales Manager |
| ManagerID | RepID of the rep's manager (blank for managers) |
| HireDate | Hire date (ISO yyyy-mm-dd) |
| TerminationDate | Last working day, blank if still active |
| Region | North America, LATAM North, LATAM South |

## rep_territory_history.csv
| Column | Description |
|---|---|
| RepID | Rep |
| TerritoryID | Territory covered |
| StartDate | First day in that territory |
| EndDate | Last day in that territory, blank if current |

## territories.csv
TerritoryID, TerritoryName, Region, Country.

## products.csv
ProductID, ProductName, Category (Software or Services), ListPrice_USD.

## deals.csv
| Column | Description |
|---|---|
| DealID | Deal ID |
| RepID | Rep who owns the deal |
| ProductID | Product sold |
| CustomerName | Fake customer |
| CloseDate | Date the deal closed |
| PaymentDate | Date the customer paid (Won and Cancelled only) |
| CancelDate | Date the deal was cancelled (Cancelled only) |
| Quantity | Units |
| DiscountPct | Discount off list price, as a fraction (0.1 = 10%) |
| Amount_USD | ListPrice x Quantity x (1 - DiscountPct) |
| Status | Won, Lost, Cancelled |

## quotas_wide.csv
RepID, FiscalYear, then one column per month (Jan to Dec) with that month's quota in USD. Zero means the rep was not employed that month.

## commission_plan.csv
Role, AttainmentFrom, AttainmentTo, Rate. Attainment values are fractions (1.0 = 100%).
