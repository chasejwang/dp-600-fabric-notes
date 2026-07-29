---
title: "Unit 8 — Module assessment"
module: DP-600
unit: 8 of 9
xp: 200
duration_minutes: 10
source: https://learn.microsoft.com/en-us/training/modules/get-started-data-warehouse/8-knowledge-check
tags:
  - dp-600
  - microsoft-fabric
  - data-warehouse
  - assessment
  - knowledge-check
---

# Unit 8 — Module assessment

> [!quote] Source
> Microsoft Learn · Module 4 · Unit 8 · "Module assessment"
> <https://learn.microsoft.com/en-us/training/modules/get-started-data-warehouse/8-knowledge-check>

> [!warning] Note on answer extraction
> Microsoft Learn intentionally **does not display the correct answers** on the assessment page — only the questions and options. The answers below are **derived from the unit content** and cross-checked against the [[_MOC]] knowledge-check table. AI-assisted questions reviewed by a human author.

> [!note] Format
> The source page presents the questions in two groups of four, then five more (the assessment contains 13 questions total). Answers below cover all 13.

---

## Group A — first four questions

### Q1 — Table type for supplier attribute details

> **Which type of table should an insurance company use to store supplier attribute details for aggregating claims?**

- [ ] Fact table.
- [x] **Dimension table.**
- [ ] Staging table.

📐 **Why:** Supplier attribute details (name, address, category) are **descriptive context**, not the numerical measures being aggregated. See [[Unit-2-Understand-Data-Warehouse]].

### Q2 — What is a semantic model in the warehouse experience?

> **What is a semantic model in the data warehouse experience?**

- [x] **A semantic model is a business-oriented data model that provides a consistent and reusable representation of data across the organization.**
- [ ] A semantic model is a physical data model that describes the structure of the data stored in the data warehouse.
- [ ] A semantic model is a machine learning model that is used to make predictions based on data in the data warehouse.

📐 **Why:** A semantic model is the **business-facing layer** that standardizes how Power BI, Copilot, and Fabric IQ data agents see the data. See [[Unit-5-Model-Data]].

### Q3 — Purpose of item permissions in a workspace

> **What is the purpose of item permissions in a workspace?**

- [ ] To grant access to all items within a workspace.
- [ ] To grant access to specific columns within a table.
- [x] **To grant access to individual warehouses for downstream consumption.**

📐 **Why:** Item permissions are the **per-warehouse granularity** on top of workspace roles — share a single warehouse without sharing the whole workspace. See [[Unit-6-Security-Monitor]].

### Q4 — Fabric warehouse capability that SQL analytics endpoint lacks

> **What capability does a Fabric data warehouse provide that a SQL analytics endpoint does not?**

- [x] **Writing data using INSERT, UPDATE, DELETE, and MERGE statements.**
- [ ] Reading data from tables and views using SELECT statements.
- [ ] Connecting with SQL client tools like SQL Server Management Studio.

📐 **Why:** The SQL analytics endpoint is **read-only**. A warehouse is read/write — full DDL/DML including `MERGE`. See [[Unit-3-Understand-Warehouses-Fabric]].

---

## Group B — remaining nine questions

### Q5 — Key benefit of a star schema

> **What is the key benefit of using a star schema in a data warehouse design?**

- [x] **It simplifies complex queries by reducing the number of joins required.**
- [ ] It ensures that data is highly normalized, reducing storage space.
- [ ] It provides real-time data processing capabilities.

📐 **Why:** Star schemas **denormalize** dimension data so queries need fewer joins. See [[Unit-2-Understand-Data-Warehouse]].

### Q6 — Restrict sales data to sales-department employees

> **Your organization wants to ensure that only sales department employees can view sales data in your Fabric data warehouse. How would you implement this requirement using security measures?**

- [ ] Apply Dynamic data masking to hide sales data from unauthorized users.
- [ ] Use Column-level security to restrict columns for non-sales users.
- [x] **Implement Row-level security (RLS) to filter rows based on department.**

📐 **Why:** When the filter criterion is **which rows** a user can see (their department matches), RLS is the right tool. CLS masks whole columns; masking hides values. See [[Unit-6-Security-Monitor]].

### Q7 — Snowflake schema dimension structure

> **When using a snowflake schema in a data warehouse, how are dimension tables typically structured?**

- [x] **Dimension tables are normalized and split into additional tables based on hierarchical relationships.**
- [ ] Dimension tables contain only surrogate keys and no descriptive attributes.
- [ ] All dimension attributes are stored in a single table to minimize join operations.

📐 **Why:** Snowflake schema = dimension tables normalized into hierarchies (e.g. `DimProduct` → `DimCategory`, `DimSupplier`). Star schema does the opposite — keeps everything in one table per dimension. See [[Unit-2-Understand-Data-Warehouse]].

### Q8 — Zero-copy clone of `Sales` table

> **How can you create a zero-copy clone of the Sales table for testing purposes in a Fabric data warehouse?**

- [ ] `SELECT * INTO dbo.SalesClone FROM dbo.Sales;`
- [x] **`CREATE TABLE dbo.SalesClone AS CLONE OF dbo.Sales;`**
- [ ] `INSERT INTO dbo.SalesClone SELECT * FROM dbo.Sales;`

📐 **Why:** `CREATE TABLE … AS CLONE OF …` is the dedicated zero-copy syntax. `SELECT INTO` and `INSERT … SELECT` both physically copy data. See [[Unit-3-Understand-Warehouses-Fabric]].

### Q9 — User sees no rows after RLS is applied

> **After implementing row-level security in your Microsoft Fabric data warehouse, a user reports they cannot see any data in a specific table. What could be a potential cause of this issue?**

- [ ] The table does not have dynamic data masking enabled.
- [x] **The user does not meet any condition in the RLS policy's predicate.**
- [ ] The user's role does not have column-level security permissions.

📐 **Why:** RLS uses a `WHERE`-clause predicate that the user must satisfy. If the predicate excludes the user (or no row matches), the user sees **zero rows**. CLS and masking are unrelated to row visibility. See [[Unit-6-Security-Monitor]].

### Q10 — Primary role of a dimension table

> **In the context of a data warehouse star schema, what is the primary role of a dimension table?**

- [x] **To provide descriptive context for the numerical data stored in fact tables.**
- [ ] To store the numerical values that are analyzed for business insights.
- [ ] To act as a staging area for raw data before transformation.

📐 **Why:** Dimensions = **descriptive context** (customer, product, date, store). Facts = numerical measures. Staging = raw holding area. See [[Unit-2-Understand-Data-Warehouse]].

### Q11 — Show financial data to finance department only

> **A client requests that their sensitive financial data in your Microsoft Fabric data warehouse be visible only to finance department employees. Which security measure should you implement to comply with this request?**

- [x] **Row-level security (RLS)**
- [ ] Dynamic data masking
- [ ] Object-level security

📐 **Why:** Same pattern as Q6 — when the rule is "users in dept X see rows, others don't", RLS is the right fit. Masking would *hide values* but not filter rows; object-level security would *remove access entirely*. See [[Unit-6-Security-Monitor]].

### Q12 — Transform raw sales data via staging into final fact table

> **In a Microsoft Fabric data warehouse, how can you transform raw sales data stored in a staging table to include customer and product details before loading it into the final fact table?**

- [ ] Directly insert data from the staging table into the final fact table without any transformation.
- [x] **Use INNER JOINs with the DimCustomer and DimProduct tables to merge data from the staging table.**
- [ ] Use the MERGE statement to combine the staging table data with the DimGeography table only.

📐 **Why:** The staging-to-fact pattern from [[Unit-3-Understand-Warehouses-Fabric]] uses `INNER JOIN` on the dimension tables' **alternate keys** to look up the warehouse **surrogate keys**, then inserts into `FactSales`.

### Q13 — Frequent `DimProduct` updates without duplicates

> **Your company requires frequent updates to the DimProduct table to reflect changing product details. Which T-SQL statement ensures that updates are performed efficiently without duplicating existing records?**

- [ ] UPDATE statement followed by multiple INSERT statements for new products.
- [ ] DELETE and INSERT statements to replace outdated product records.
- [x] **MERGE statement to efficiently update and insert product details.**

📐 **Why:** `MERGE` is the upsert workhorse — match on the alternate key, update when present, insert when absent, all in a single statement. The module explicitly calls out MERGE as a Fabric warehouse capability. See [[Unit-3-Understand-Warehouses-Fabric]].

---

## 📊 Self-score

| # | Question | Your answer | Correct | Notes |
|---|----------|-------------|---------|-------|
| 1 | Supplier attribute table type | ☐ | ✅ Dimension | Descriptive context, not measures |
| 2 | What is a semantic model? | ☐ | ✅ Business-oriented | Business-facing layer for Power BI/AI |
| 3 | Item permissions purpose | ☐ | ✅ Per-warehouse access | Granular sharing below workspace role |
| 4 | Warehouse vs. analytics endpoint | ☐ | ✅ INSERT/UPDATE/DELETE/MERGE | Analytics endpoint is read-only |
| 5 | Star schema benefit | ☐ | ✅ Fewer joins | Denormalized dimensions |
| 6 | Department row filter | ☐ | ✅ RLS | Row predicate, not column or value |
| 7 | Snowflake dimension structure | ☐ | ✅ Normalized into hierarchies | Splits dims into related tables |
| 8 | Zero-copy clone | ☐ | ✅ AS CLONE OF | Other options copy data |
| 9 | RLS user sees nothing | ☐ | ✅ Predicate excludes user | Where-clause doesn't match |
| 10 | Dimension role | ☐ | ✅ Descriptive context | Facts hold the numbers |
| 11 | Finance-only rows | ☐ | ✅ RLS | Same row-filter pattern as Q6 |
| 12 | Staging → fact transform | ☐ | ✅ INNER JOINs to dims | Lookup surrogate keys |
| 13 | DimProduct upsert | ☐ | ✅ MERGE | One statement, no duplicates |

## 🧭 Next

→ [[Unit-9-Summary]]
← [[Unit-7-Exercise]]
↑ [[_MOC]]