---
title: "Unit 7 — Knowledge check"
module: DP-600
unit: 7 of 8
xp: 200
duration_minutes: 3
source: https://learn.microsoft.com/en-us/training/modules/fabric-transform-data-notebooks/7-knowledge-check
tags:
  - dp-600
  - microsoft-fabric
  - notebook
  - spark
  - delta-table
  - assessment
  - knowledge-check
---

# Unit 7 — Knowledge check

> [!quote] Source
> Microsoft Learn · Path 2 · Module 4 · Unit 7 · "Knowledge check"
> <https://learn.microsoft.com/en-us/training/modules/fabric-transform-data-notebooks/7-knowledge-check>

> [!warning] Note on answer extraction
> Microsoft Learn intentionally **does not display the correct answers** on the assessment page — only the questions and options. The answers below are **derived from the unit content** and cross-checked against the [[_MOC]] knowledge-check table.

> [!note] Format
> The source page presents 5 multiple-choice questions. Answers below cover all 5.

---

### Q1 — Run Spark SQL in a PySpark notebook

> **A data team wants to run Spark SQL queries in a PySpark notebook. What do they need to add at the top of a cell to run SQL?**

- [ ] `%spark`
- [x] **`%%sql`**
- [ ] `%%pyspark`

📐 **Why:** The `%%sql` magic command tells the notebook kernel to interpret the cell as Spark SQL — even when the notebook's default language is PySpark. The single `%spark` form is not the standard cell magic, and `%%pyspark` would switch the cell to Python. See [[Unit-2-Describe-Notebooks]].

### Q2 — Replace null values in `discount` with zero in PySpark

> **An analytics engineer needs to replace null values in a discount column with zero using PySpark. Which method should they use?**

- [ ] `df.dropna(subset=["discount"])`
- [x] **`df.fillna({"discount": 0})`**
- [ ] `df.filter(col("discount").isNotNull())`

📐 **Why:** `fillna` with a dict replaces nulls in specific columns with the provided defaults — exactly what the question asks. `dropna` removes rows; `filter` excludes rows from the result but doesn't change the underlying values. See [[Unit-3-Shape-Clean-Data]].

### Q3 — Nightly full refresh of a gold-layer table

> **A team writes a nightly transformation that replaces all data in a gold-layer table with freshly processed results. Which write mode should they use?**

- [ ] `append`
- [x] **`overwrite`**
- [ ] `merge`

📐 **Why:** A nightly **full refresh** that replaces all data matches the `overwrite` mode definition ("Replaces the entire table with new data — running a full refresh of transformed data"). `append` would accumulate rows; `merge` is for row-level upserts. See [[Unit-5-Write-Delta-Tables]].

### Q4 — Window functions vs. GROUP BY

> **What does a window function provide that a standard GROUP BY aggregation does not?**

- [x] **It calculates aggregated values while keeping the individual row detail.**
- [ ] It runs faster than GROUP BY on large datasets.
- [ ] It supports more aggregation functions than GROUP BY.

📐 **Why:** The defining property of window functions is that they **compute across related rows without collapsing the data into groups** — so you get running totals, rankings, and row-to-row comparisons alongside every original row. GROUP BY reduces the row count; windows keep it. See [[Unit-4-Combine-Aggregate]].

### Q5 — Many small Parquet files after weeks of appends

> **A table has grown to contain many small Parquet files after weeks of incremental appends. Which command consolidates these files to improve query performance?**

- [ ] `VACUUM`
- [x] **`OPTIMIZE`**
- [ ] `ANALYZE TABLE`

📐 **Why:** `OPTIMIZE` **compacts small files into larger ones** — exactly the fix for small-file fragmentation after incremental appends. `VACUUM` *removes* old, unreferenced files (storage cleanup, not compaction). `ANALYZE TABLE` is a SQL statistics command, not a Delta file operation. See [[Unit-5-Write-Delta-Tables]].

---

## 📊 Self-score

| # | Question | Your answer | Correct | Notes |
|---|----------|-------------|---------|-------|
| 1 | Run SQL in PySpark notebook | ☐ | ✅ `%%sql` | Magic command to switch cell language |
| 2 | Replace nulls with zero | ☐ | ✅ `df.fillna({...})` | Default replacement, not row removal |
| 3 | Nightly full-refresh write mode | ☐ | ✅ `overwrite` | Replace all data |
| 4 | Window vs. GROUP BY | ☐ | ✅ Keeps row detail | Aggregates without collapsing |
| 5 | Compact small files | ☐ | ✅ `OPTIMIZE` | `VACUUM` removes, doesn't compact |

## 🧭 Next

→ [[Unit-8-Summary]]
← [[Unit-6-Exercise]]
↑ [[_MOC]]
