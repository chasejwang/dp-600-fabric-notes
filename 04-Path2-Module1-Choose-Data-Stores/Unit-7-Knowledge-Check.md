---
title: "Unit 7 — Module assessment"
module: "DP-600 · Path 2 · Module 1 — Choose data stores in Microsoft Fabric"
unit: 7 of 8
xp: 200
duration_minutes: 3
source: https://learn.microsoft.com/en-us/training/modules/choose-data-store-fabric/7-knowledge-check
tags:
  - dp-600
  - microsoft-fabric
  - knowledge-check
  - assessment
  - data-stores
---

# Unit 7 — Module assessment

## 🎯 Why this matters

This five-question knowledge check confirms you can apply the decision framework from Units 2–5 in realistic scenarios. Each question below is followed by the **correct answer with reasoning** grounded in the unit content (no peeking at Microsoft Learn first — try to recall, then check).

## 📝 Question 1

> Which analytical data store in Microsoft Fabric provides **full multi-table ACID transaction support** through T-SQL?
>
> - Lakehouse
> - Warehouse
> - Eventhouse

> [!success] Correct answer: Warehouse
> **Why:** The warehouse is the only Fabric analytical store with **full multi-table ACID transactions** delivered via T-SQL. The lakehouse supports only single-table transactions through Delta Lake, and the eventhouse is append-optimized (no transactional UPDATE/DELETE). See [[Unit-4-Evaluate-Warehouse|Unit 4 — Warehouse]].

## 📝 Question 2

> A data science team needs to explore a mix of structured transaction data and semi-structured web logs using **Python notebooks**. Which data store is the best fit?
>
> - Lakehouse
> - Warehouse
> - Eventhouse

> [!success] Correct answer: Lakehouse
> **Why:** Mixed formats (structured + semi-structured JSON/Parquet) and Python notebooks are defining lakehouse characteristics. The lakehouse handles all three data formats in its Tables and Files areas and provides a native Spark notebook environment with the full Python ML ecosystem. See [[Unit-3-Evaluate-Lakehouse|Unit 3 — Lakehouse]].

## 📝 Question 3

> What is the **primary query language** used by the eventhouse for time-series analytics?
>
> - T-SQL
> - Spark SQL
> - KQL (Kusto Query Language)

> [!success] Correct answer: KQL (Kusto Query Language)
> **Why:** KQL is designed specifically for time-series analysis, with built-in operators for time-window aggregations, anomaly detection, pattern matching, and geospatial analysis. The eventhouse also supports a subset of T-SQL, but KQL provides the richest analytics experience. See [[Unit-5-Evaluate-Eventhouse|Unit 5 — Eventhouse]].

## 📝 Question 4

> An organization needs to build a **star schema** with dimension tables that require **frequent updates**. Which data store best supports this requirement?
>
> - Warehouse
> - Lakehouse
> - Eventhouse

> [!success] Correct answer: Warehouse
> **Why:** Star schemas with frequently updated dimensions (slowly changing dimensions) require full T-SQL DML (UPDATE, DELETE, MERGE) with multi-table ACID transactions. Only the warehouse provides these capabilities natively. The lakehouse's SQL analytics endpoint is read-only, and the eventhouse is append-optimized. See [[Unit-4-Evaluate-Warehouse|Unit 4 — Warehouse]].

## 📝 Question 5

> Which feature allows data in one Fabric data store to be accessed from another store **without copying or moving the data**?
>
> - Cross-database queries and shortcuts
> - Data pipelines
> - Streaming ingestion

> [!success] Correct answer: Cross-database queries and shortcuts
> **Why:** Because all three stores write to **OneLake**, Fabric provides two native integration mechanisms: **OneLake shortcuts** let any store reference data in another without duplication, and **cross-database queries** in the warehouse let you join data from multiple warehouses and lakehouse SQL analytics endpoints using three-part naming (`warehouse.schema.table`). Data pipelines move/copy data; streaming ingestion only feeds the eventhouse — neither matches the question. See [[Unit-2-Describe-Options|Unit 2 — Describe options]].

## 📊 Score yourself

| Score | Verdict |
|---|---|
| 5 / 5 | Mastered the decision framework — confident to choose stores in real Fabric projects. |
| 4 / 5 | Strong; re-read the one missed unit before the exam. |
| 3 / 5 | Decent; revisit [[Unit-2-Describe-Options]] to reinforce the comparison axes. |
| ≤ 2 / 5 | Re-walk Units 2–5 before continuing. |

> [!tip] Spaced repetition
> Come back to this assessment in a few days. If the answers don't feel automatic, the mental model isn't fully consolidated yet — re-read the linked units and try again.

## 🔗 Related

- [[Unit-6-Case-Study|← Unit 6 — Case study]]
- [[Unit-8-Summary|Next → Summary]]
- [[_MOC|Module index]]