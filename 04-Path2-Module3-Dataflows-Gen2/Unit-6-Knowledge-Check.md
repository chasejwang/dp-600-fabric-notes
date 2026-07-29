---
title: "Unit 6 — Knowledge check"
module: DP-600
unit: 6 of 7
xp: 200
duration_minutes: 3
source: https://learn.microsoft.com/en-us/training/modules/fabric-transform-data-dataflows/6-knowledge-check/
tags:
  - dp-600
  - microsoft-fabric
  - dataflows-gen2
  - assessment
  - knowledge-check
---

# Unit 6 — Knowledge check

> [!quote] Source
> Microsoft Learn · Path 2 · Module 3 · Unit 6 · "Knowledge check"
> <https://learn.microsoft.com/en-us/training/modules/fabric-transform-data-dataflows/6-knowledge-check/>

> [!warning] Note on answer extraction
> Microsoft Learn's **knowledge-check pages publish the questions and options** but **do not display the correct answers** when you take the assessment. The "correct" answers below are **derived from the unit content** (Units 2–4) per Microsoft Fabric's documented behavior, then cross-checked against the option wording in the source.

## Q1 — Primary purpose of a dataflow

> What is the primary purpose of a dataflow in Microsoft Fabric?

- [ ] To create visualizations and reports from raw data.
- [x] **To extract, transform, and load data using a low-code Power Query interface.**
- [ ] To manage workspace security and access permissions.

📐 **Why:** See [[Unit-2-Understand-Dataflows]] — dataflows are **cloud-based ETL tools** that use **Power Query** to connect to data sources, apply transformations, and load results to a destination. Visualizations belong to **Power BI reports**, not dataflows. Workspace security is a separate concern (workspace roles / item sharing), not the purpose of a dataflow.

> [!tip] Common distractor to recognize
> "Create visualizations and reports" sounds adjacent because Power BI sits downstream of dataflows — but **building reports is not what a dataflow does**. A dataflow *produces the data that reports visualize*.

## Q2 — What is query folding?

> What is query folding?

- [ ] The process of combining multiple queries into a single query for efficiency.
- [x] **The process of pushing transformation logic to the data source for execution instead of processing it in the Power Query engine.**
- [ ] The process of organizing applied steps into folders for better readability.

📐 **Why:** See [[Unit-4-Optimize-Performance]] — **query folding translates M steps into a native query (e.g., SQL)** that the data source executes, so the source returns only the transformed results and the Power Query engine does less work. "Combining multiple queries" describes query merging (a different concept), and "organizing steps into folders" describes the Applied Steps UI — neither is folding.

## Q3 — Combine rows from two queries like a SQL JOIN

> Which transformation combines rows from two queries into a single query, similar to a SQL JOIN?

- [ ] Append queries.
- [ ] Group by.
- [x] **Merge queries.**

📐 **Why:** See [[Unit-3-Transform-Power-Query]] — the transformations table explicitly maps **Merge queries → "Join two queries on matching columns (like a SQL JOIN)"**. **Append queries** is the SQL **UNION** equivalent (stacking rows). **Group by** aggregates — it does not combine rows from two sources.

> [!tip] Memorize the mapping
> **Merge = JOIN (add columns side-by-side)**. **Append = UNION (stack rows top-to-bottom)**. These two come up constantly on data-engineering exams.

## Q4 — Check whether a step folds

> How can you check whether a specific applied step folds to the data source?

- [ ] Open the Advanced Editor and look for SQL syntax in the M code.
- [x] **Right-click the step in the Applied Steps pane and check if View Native Query is available.**
- [ ] Run the dataflow and check the refresh history for folding status.

📐 **Why:** See [[Unit-4-Optimize-Performance]] — the documented way to inspect folding is to **right-click the step in Applied Steps and look for View Native Query** (available = folds; grayed out = doesn't fold from that step onward). Advanced Editor shows M, not the source query (M may or may not fold — you can't tell from the M alone). Refresh history tracks *timing*, not folding status.

## Q5 — When is a notebook better than a dataflow?

> When is a notebook a better choice than a dataflow for data transformation?

- [ ] When the team prefers a visual drag-and-drop interface.
- [ ] When transformations involve filtering rows and removing columns.
- [x] **When transformations require complex logic or large-scale distributed processing.**

📐 **Why:** See [[Unit-2-Understand-Dataflows]] — the source is explicit: **"If the logic involves advanced algorithms, iterative processing, or large-scale joins, Apache Spark notebooks provide more flexibility and performance."** Visual drag-and-drop and simple filter/remove-column work are exactly what dataflows are *good at* — not reasons to leave them.

> [!tip] Dataflow vs notebook decision
> **Dataflow** = low-code, Power Query, simple-to-moderate transformations, fast iteration, Fabric-managed compute. **Notebook (Spark)** = code-first, complex logic, distributed compute, ML iteration. Pick the simplest tool that fits the work.

## 📊 Self-score

| Question | Your answer | Correct | Notes |
|----------|-------------|---------|-------|
| 1 | ☐ | ✅ Extract, transform, load with low-code Power Query | Visualizations belong to Power BI reports |
| 2 | ☐ | ✅ Push logic to the source | Combining queries ≠ folding |
| 3 | ☐ | ✅ Merge queries = SQL JOIN | Append = UNION, Group by = aggregate |
| 4 | ☐ | ✅ Right-click step → View Native Query | M code ≠ native query |
| 5 | ☐ | ✅ Complex logic or distributed compute | Simple shaping is dataflow's sweet spot |

## 🧭 Next

→ [[Unit-7-Summary]]
← [[Unit-5-Exercise-Dataflows-Gen2]]
↑ [[_MOC]]