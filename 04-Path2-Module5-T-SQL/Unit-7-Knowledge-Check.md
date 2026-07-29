---
title: "Unit 7 — Knowledge check"
module: DP-600
unit: 7 of 8
xp: 200
duration_minutes: 3
source: https://learn.microsoft.com/en-us/training/modules/fabric-transform-data-tsql/7-knowledge-check
tags:
  - dp-600
  - microsoft-fabric
  - t-sql
  - sql
  - assessment
  - knowledge-check
---

# Unit 7 — Knowledge check

> [!quote] Source
> Microsoft Learn · Path 2 · Module 5 · Unit 7 · "Knowledge check"
> <https://learn.microsoft.com/en-us/training/modules/fabric-transform-data-tsql/7-knowledge-check>

> [!warning] Note on answer extraction
> Microsoft Learn intentionally **does not display the correct answers** on the assessment page — only the questions and options. The answers below are **derived from the unit content** and cross-checked against the [[_MOC]] knowledge-check table.

> [!note] Format
> The source page presents 5 multiple-choice questions. Answers below cover all 5.

---

### Q1 — Running total of sales per customer without collapsing rows

> **A data engineer needs to combine order data from a staging table with customer names from a dimension table and calculate a running total of sales per customer. Which T-SQL feature calculates the running total without collapsing the result set?**

- [ ] A `GROUP BY` clause with `SUM`
- [x] **A window function with `SUM ... OVER`**
- [ ] A common table expression (CTE)

📐 **Why:** Window functions perform calculations **across a set of rows related to the current row without collapsing the result set** — they keep every row and add the calculated value alongside. `SUM(amount) OVER (PARTITION BY customer_id ORDER BY order_date)` is the textbook running-total pattern. `GROUP BY` collapses rows into one per group; a CTE alone doesn't compute anything new — it just names an intermediate result. See [[Unit-2-Transform-Queries]].

### Q2 — Encapsulate a complex join-and-aggregation used by many reports

> **A team queries the same complex join and aggregation logic from multiple reports and semantic models. What is the primary benefit of implementing this logic as a view instead of repeating the query?**

- [ ] Views store pre-computed results that load faster than running the query directly.
- [x] **Views define the query once so it can be referenced by name, reducing duplication and simplifying maintenance.**
- [ ] Views enforce foreign key constraints between the tables they reference.

📐 **Why:** The defining benefit of a view is **reusability** — write the logic once as `CREATE VIEW gold.vw_...`, then reference it by name from any number of reports and semantic models. When the logic changes, `ALTER VIEW` updates one place. Views **don't store pre-computed results** (that's a materialized table) and Fabric warehouses **don't enforce foreign-key constraints** at the engine level. See [[Unit-3-Create-Views]].

### Q3 — Procedure deletes a period's rows then inserts fresh aggregates

> **A data engineer builds a stored procedure that accepts year and month parameters to refresh a summary table. The procedure deletes existing rows for that period and inserts freshly aggregated data. Which loading pattern does this procedure implement?**

- [ ] Merge (upsert)
- [ ] Incremental load
- [x] **Full refresh of a partition**

📐 **Why:** The procedure deletes **only the rows for the targeted year/month** (a partition of the table) and replaces them with a fresh aggregation. This is a **full refresh scoped to a partition** — not a row-level merge, and not an incremental append. The parameters `@year` and `@month` are what make it partitioned rather than table-wide. See [[Unit-4-Build-Stored-Procedures]].

### Q4 — Why filter `dim.customer` by `is_current = 1` when loading a fact table

> **When loading a fact table from staging data, the `INSERT` statement joins `staging.orders` with `dim.customer` using the filter `is_current = 1`. What does this filter accomplish?**

- [ ] It restricts the load to only the most recent orders in the staging table.
- [x] **It links each fact row to the current version of the customer dimension record.**
- [ ] It prevents duplicate rows from being inserted into the fact table.

📐 **Why:** In SCD Type 2 dimensions, the same natural `customer_id` can have multiple rows (one per historical version). Filtering on `is_current = 1` ensures the join matches **only the current version** of the customer record. (For historical accuracy — linking to the version active at order time — match on the effective-date range instead.) See [[Unit-5-Implement-Dimensional-Tables]].

### Q5 — Test transforms against production data without risking the originals

> **A data engineer needs to test transformation logic against production warehouse data without risking changes to the original tables. Which Fabric feature supports this scenario with minimal storage overhead?**

- [ ] Create a view over the production table
- [x] **Create a table clone of the production table**
- [ ] Create a stored procedure that wraps the production table in a transaction

📐 **Why:** `CREATE TABLE ... AS CLONE OF ...` creates a **zero-copy reference** to the production table's data at a point in time — clones share underlying files with the source until you modify them, so there's no storage penalty. Views are read-only (you can't test `INSERT`/`UPDATE`/`DELETE` against them), and wrapping in a `BEGIN TRAN` / `ROLLBACK` doesn't isolate changes from concurrent readers and adds rollback-log overhead. See [[Unit-5-Implement-Dimensional-Tables]].

---

## 📊 Self-score

| # | Question | Your answer | Correct | Notes |
|---|----------|-------------|---------|-------|
| 1 | Running total without collapsing | ☐ | ✅ `SUM ... OVER` | Window function keeps row detail |
| 2 | Reuse logic across reports | ☐ | ✅ View = one-place definition | Reusability, not pre-computation |
| 3 | Delete-period + insert-aggregate pattern | ☐ | ✅ Full refresh of a partition | Parameterized period, not row-level |
| 4 | `is_current = 1` filter on dim join | ☐ | ✅ Pin to current dim version | SCD2 history filter |
| 5 | Test against prod with minimal storage | ☐ | ✅ Table clone | Zero-copy + writable |

## 🧭 Next

→ [[Unit-8-Summary]]
← [[Unit-6-Exercise]]
↑ [[_MOC]]