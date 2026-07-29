---
title: "Unit 5 — Module assessment"
module: DP-600
unit: 5 of 6
xp: 200
duration_minutes: 3
source: https://learn.microsoft.com/en-us/training/modules/introduction-end-analytics-use-microsoft-fabric/5-knowledge-check/
tags:
  - dp-600
  - microsoft-fabric
  - assessment
  - knowledge-check
---

# Unit 5 — Module assessment

> [!quote] Source
> Microsoft Learn · Module 1 · Unit 5 · "Module assessment"
> <https://learn.microsoft.com/en-us/training/modules/introduction-end-analytics-use-microsoft-fabric/5-knowledge-check/>

> [!warning] Note on answer extraction
> Microsoft Learn intentionally **does not display the correct answers** on the assessment page (only the questions + options). The answers below are derived from the unit content per Microsoft Fabric's documented behavior and cross-checked against the Source unit content.

## Q1 — Key benefit of Fabric

> **What is a key benefit of using Microsoft Fabric in data projects?**

- [ ] It allows data professionals to work independently, without collaboration.
- [ ] It requires duplicating data across systems to ensure availability.
- [x] **It provides a single, integrated environment for collaboration on data projects.**

📐 **Why:** See [[Unit-3-Data-Teams]] — Fabric removes silos and the need for multiple systems.

## Q2 — Default OneLake format

> **What is the default storage format for Fabric's OneLake?**

- [x] **Delta-Parquet**
- [ ] JSON
- [ ] CSV

📐 **Why:** See [[Unit-2-Explore-Analytics-Fabric]] — All analytical engines write tabular data in **Delta-Parquet**.

## Q3 — Move and transform data

> **Which Fabric experience is used to move and transform data?**

- [ ] Data Science
- [ ] Data Warehousing
- [x] **Data Factory**

📐 **Why:** See [[Unit-4-Enable-and-Use-Fabric]] — Data Factory's purpose is **ingest, transform, orchestrate**.

## Q4 — Why OneLake matters for AI

> **Why is OneLake's unified storage model important for AI capabilities in Fabric?**

- [ ] It requires all data to be converted to a proprietary format for AI processing.
- [x] **AI tools like Copilot and data agents can access the same governed data without separate preparation pipelines.**
- [ ] It stores AI models alongside the data they process.

📐 **Why:** See [[Unit-4-Enable-and-Use-Fabric]] — open format + single lake = no separate prep pipelines for AI.

## 📊 Self-score

| Question | Your answer | Correct | Notes |
|----------|-------------|---------|-------|
| 1 | ☐ | ✅ | Look for "single, integrated environment" framing |
| 2 | ☐ | ✅ Delta-Parquet | Memorize this — asked in multiple Fabric exams |
| 3 | ☐ | ✅ Data Factory | ADF lineage survives in Fabric |
| 4 | ☐ | ✅ | Re-read the AI section in unit 4 |

## 🧭 Next

→ [[Unit-6-Summary]]
← [[Unit-4-Enable-and-Use-Fabric]]
↑ [[_MOC]]