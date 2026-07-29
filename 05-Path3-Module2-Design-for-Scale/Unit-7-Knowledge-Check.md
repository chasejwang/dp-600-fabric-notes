---
title: "Unit 7 — Knowledge check"
module: DP-600
unit: 7 of 8
xp: 200
duration_minutes: 3
source: https://learn.microsoft.com/en-us/training/modules/design-semantic-models-scale/7-knowledge-check
tags:
  - dp-600
  - microsoft-fabric
  - semantic-model
  - assessment
  - knowledge-check
---

# Unit 7 — Knowledge check

> [!quote] Source
> Microsoft Learn · Module 2 · Unit 7 · "Module assessment"
> <https://learn.microsoft.com/en-us/training/modules/design-semantic-models-scale/7-knowledge-check>

> [!warning] Note on answer extraction
> Microsoft Learn intentionally **does not display the correct answers** on the knowledge-check page — only the questions and options. The answers below are **derived from the unit content** and cross-checked against the [[_MOC]] knowledge-check table.

> [!note] Format
> The assessment contains **5 questions**. All 5 are covered below.

---

### Q1 — Default storage mode for a new semantic model with data in a lakehouse

> **An analytics team builds a new semantic model in Microsoft Fabric with all data stored in a lakehouse. Which storage mode should they choose as the default for this model?**

- [ ] Import mode, because it provides the fastest query performance.
- [x] **Direct Lake mode, because it reads Delta tables directly from OneLake without importing data.**
- [ ] DirectQuery mode, because it queries the source in real time.

📐 **Why:** [[Unit-2-Storage-Modes]] opens with: *"In Fabric, **Direct Lake is the default**, and for most workloads it's the right choice."* Direct Lake reads Delta tables directly from OneLake into memory — combining Import's speed with DirectQuery's freshness. Import is fastest per query but introduces a refresh dependency; DirectQuery would make sense only if real-time were required and the source were outside Fabric.

### Q2 — Avoiding 180 extra measures for 60 base measures

> **A company has 60 base measures in a semantic model and needs Year-to-Date, Quarter-to-Date, and Month-to-Date versions of each. What should a model designer implement to avoid creating 180 additional measures?**

- [x] **A calculation group with time intelligence calculation items that use `SELECTEDMEASURE()`.**
- [ ] DAX variables to store intermediate results and reduce repeated calculations.
- [ ] Aggregations with pre-summarized tables at the monthly, quarterly, and yearly grain.

📐 **Why:** [[Unit-4-Calculation-Patterns]] frames this exact scenario: *"50 base measures needing YTD, QTD, and MTD → 150 extra measures without calculation groups."* A calculation group with YTD/QTD/MTD items wraps `SELECTEDMEASURE()` and applies to any base measure automatically. DAX variables improve readability of a single measure; aggregations address performance, not measure proliferation.

### Q3 — Prerequisite for XMLA endpoint read/write access

> **A model designer needs to use Tabular Editor for external model development and deploy through CI/CD pipelines. Which setting is a prerequisite for XMLA endpoint read/write access?**

- [x] **Large semantic model storage format.**
- [ ] OneLake integration.
- [ ] Query scaleout.

📐 **Why:** [[Unit-5-Scale-Settings]] explicitly states: *"This setting is also a prerequisite for both XMLA endpoint read/write access and query scaleout."* OneLake integration and query scaleout are independent capabilities — scaling and integration concerns, not XMLA prerequisites.

### Q4 — Benefit of "Assume referential integrity" on a Direct Lake relationship

> **A model designer enables the Assume referential integrity setting on a relationship between a fact table and a dimension table in a Direct Lake model. What is the performance benefit of this setting?**

- [x] **The engine uses INNER joins instead of LEFT OUTER joins, which reduces the number of rows processed.**
- [ ] The engine caches relationship metadata so that subsequent queries skip relationship evaluation.
- [ ] The engine creates an index on the foreign key column to speed up relationship lookups.

📐 **Why:** [[Unit-3-Star-Schema]] states: *"The **Assume referential integrity** setting tells the engine to use INNER joins rather than LEFT OUTER joins when querying across a relationship. In Direct Lake and DirectQuery modes, this setting can significantly improve performance because it reduces the number of rows the engine processes."* The other options describe engine optimizations that don't actually exist for this setting — the explicit benefit is the INNER join substitution.

### Q5 — Improving summary query performance on a 150M-row fact table

> **A semantic model has a fact table with 150 million rows. Report users primarily view monthly and quarterly summaries by region. Which design pattern improves query performance for these summary-level visuals?**

- [x] **Aggregation tables that store precalculated totals at the monthly and quarterly grain.**
- [ ] Calculation groups with time intelligence calculation items.
- [ ] Bi-directional filtering between the fact and dimension tables.

📐 **Why:** [[Unit-4-Calculation-Patterns]] defines aggregations as *"summary tables that store precalculated totals at a higher grain than the detail data"* and lists *"fact tables exceed millions of rows and commonly used queries summarize data at a higher grain (such as monthly totals by region)"* as the prime trigger. Calculation groups reduce measure proliferation, not query scan cost; bi-directional filtering typically degrades performance and is the opposite of what helps at scale.

---

## 📊 Self-score

| # | Question | Your answer | Correct | Notes |
|---|----------|-------------|---------|-------|
| 1 | Default storage mode for Fabric-native data | ☐ | ✅ Direct Lake | Default in Fabric, reads Delta from OneLake |
| 2 | Avoiding 180 extra YTD/QTD/MTD measures | ☐ | ✅ Calculation group | `SELECTEDMEASURE()` pattern |
| 3 | Prerequisite for XMLA read/write | ☐ | ✅ Large model storage format | Hard prerequisite |
| 4 | "Assume referential integrity" benefit | ☐ | ✅ INNER joins over LEFT OUTER | Row count reduction |
| 5 | 150M-row fact, monthly summaries | ☐ | ✅ Aggregation tables | Pre-summarized at high grain |

## 🧭 Next

→ [[Unit-8-Summary]]
← [[Unit-6-Exercise]]
↑ [[_MOC]]
