---
title: "Unit 7 — Knowledge check"
module: DP-600
unit: 7 of 8
xp: 200
duration_minutes: 3
source: https://learn.microsoft.com/en-us/training/modules/design-dimensional-models-fabric/7-knowledge-check
tags:
  - dp-600
  - microsoft-fabric
  - dimensional-modeling
  - assessment
  - knowledge-check
---

# Unit 7 — Knowledge check

> [!quote] Source
> Microsoft Learn · Module 2 · Unit 7 · "Knowledge check"
> <https://learn.microsoft.com/en-us/training/modules/design-dimensional-models-fabric/7-knowledge-check>

> [!warning] Note on answer extraction
> Microsoft Learn intentionally **does not display the correct answers** on the knowledge-check page — only the questions and options. The answers below are **derived from the unit content** and cross-checked against the [[_MOC]] knowledge-check table.

> [!note] Format
> The assessment contains **5 questions**. All 5 are covered below.

---

### Q1 — Schema type recommended for most analytics workloads in Microsoft Fabric

> **Which schema type is recommended for most analytics workloads in Microsoft Fabric?**

- [ ] Snowflake schema
- [x] **Star schema**
- [ ] Normalized schema

📐 **Why:** [[Unit-2-Describe-Schema-Types]] states explicitly that "**Star schema is the recommended approach** for most analytics workloads in Microsoft Fabric" because of fewer joins, intuitive structure, semantic-model readiness, and low maintenance.

### Q2 — Most important design decision when creating a fact table

> **What is the most important design decision when creating a fact table?**

- [ ] Choosing the naming convention for the table
- [ ] Selecting which measures to include
- [x] **Defining the grain**

📐 **Why:** [[Unit-3-Design-Fact-Tables]] opens the design unit with: "The most important design decision for a fact table is defining the **grain**. The grain specifies what one row in the fact table represents." Naming conventions are addressed later as a maintenance tip; measure selection follows from a correctly-defined grain.

### Q3 — Why surrogate keys are recommended for dimension tables

> **Why are surrogate keys recommended for dimension tables?**

- [ ] They store meaningful business values that users can interpret
- [x] **They insulate the data warehouse from source system changes and support historical tracking**
- [ ] They eliminate the need for natural keys in the dimension

📐 **Why:** [[Unit-4-Design-Dimension-Tables]] lists four benefits of surrogate keys — *consolidate data from multiple source systems without key conflicts*, *replace multi-column natural keys with a single, efficient column*, *support SCD Type 2 tracking*, and *reduce fact-table storage*. Option 2 captures the core motivation. The natural key (business key) is still kept alongside the surrogate key for ETL traceability.

### Q4 — SCD type for "sales by salesperson region at the time of each sale"

> **An organization needs to analyze sales by the region a salesperson was assigned to at the time of each sale. Which SCD type should the organization use for the region attribute?**

- [ ] Type 1, which overwrites the current value
- [x] **Type 2, which adds a new version row**
- [ ] Type 3, which adds a column for the previous value

📐 **Why:** [[Unit-5-Implement-Slowly-Changing-Dimensions]] uses **exactly this scenario** as its flagship Type 2 example: *"if you need to report sales by the region a salesperson was assigned to at the time of each sale, Type 2 tracking preserves that context."* Type 1 would silently reassign all past sales to the salesperson's current region; Type 3 only retains the most recent prior value.

### Q5 — Measure type for end-of-day inventory balance

> **A periodic snapshot fact table records end-of-day inventory levels. Which measure type best describes the inventory balance?**

- [ ] Additive
- [x] **Semi-additive**
- [ ] Non-additive

📐 **Why:** [[Unit-3-Design-Fact-Tables]] defines `InventoryLevel` (and `AccountBalance`) as the canonical **semi-additive** example — *"Can be summed across some dimensions, but not all, typically not across time."* Summing inventory balances across dates would double-count, which is exactly the wrong behavior; summing them across products, stores, or product/store combinations is fine.

---

## 📊 Self-score

| # | Question | Your answer | Correct | Notes |
|---|----------|-------------|---------|-------|
| 1 | Recommended schema type | ☐ | ✅ Star | Recommended default in Fabric |
| 2 | Most important fact-table decision | ☐ | ✅ The grain | Determines keys + measures |
| 3 | Why surrogate keys | ☐ | ✅ Insulate from source change + history | Source-of-truth neutrality |
| 4 | SCD for "region as of sale date" | ☐ | ✅ Type 2 | Preserves historical context |
| 5 | Inventory balance measure type | ☐ | ✅ Semi-additive | Not summable across dates |

## 🧭 Next

→ [[Unit-8-Summary]]
← [[Unit-6-Exercise]]
↑ [[_MOC]]
