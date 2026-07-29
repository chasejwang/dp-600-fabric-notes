---
title: "Unit 9 — Module assessment"
module: DP-600
unit: 9 of 10
xp: 200
duration_minutes: 10
source: https://learn.microsoft.com/en-us/training/modules/get-started-kusto-fabric/6-knowledge-check
tags:
  - dp-600
  - microsoft-fabric
  - real-time-intelligence
  - assessment
  - knowledge-check
  - kql
  - activator
  - eventstreams
---

# Unit 9 — Module assessment

> [!quote] Source
> Microsoft Learn · Path 1 · Module 5 · Unit 9 · "Module assessment"
> <https://learn.microsoft.com/en-us/training/modules/get-started-kusto-fabric/6-knowledge-check>

> [!warning] Note on answer extraction
> Microsoft Learn intentionally **does not display the correct answers** on the assessment page (only the questions + options). The answers below are **derived from the unit content** per Microsoft Fabric's documented behavior and cross-checked against the Source unit content.

> [!note] Source disclosure
> The Microsoft Learn module page states: *"AI-generated content. The questions and answer choices in this module assessment were generated using AI and reviewed by a human author."*

## Q1 — Component to ingest & transform a stream

> **Which Microsoft Fabric Real-Time Intelligence component should you use to ingest and transform a stream of real-time data?**

- [ ] Eventhouse
- [x] **Eventstream**
- [ ] Activator

📐 **Why:** See [[Unit-3-RTI-Components]] and [[Unit-4-Ingest-Transform]] — **Eventstreams** are Fabric's ingest + in-line transform component. Eventhouse *stores*, Activator *acts on*.

## Q2 — Query language optimized for an eventhouse

> **Which language is optimized for querying real-time data in an eventhouse?**

- [ ] Python
- [ ] SQL
- [x] **KQL**

📐 **Why:** See [[Unit-5-Store-Query-KQL]] — KQL (Kusto Query Language) is purpose-built for time-series / streaming data in Eventhouses. SQL is supported as a subset only.

## Q3 — Component that visualizes real-time data in tiles

> **Which Microsoft Fabric Real-Time Intelligence component is used to visualize and explore real-time data in tiles?**

- [ ] Dataflows
- [x] **Real-Time Dashboards**
- [ ] Delta tables

📐 **Why:** See [[Unit-6-Visualize-Real-Time]] — **Real-Time Dashboards** are the tiled surface; each tile is a KQL query.

## Q4 — Combine data from two tables on a shared key

> **Which KQL operator would you use to combine data from two tables based on a shared key in Microsoft Fabric?**

- [ ] union
- [x] **join**
- [ ] merge

📐 **Why:** See [[Unit-5-Store-Query-KQL]] — `join` combines rows on a shared key. `union` stacks rows of the same shape; `merge` is not a KQL operator in this sense.

## Q5 — Activator for sensor-warning maintenance

> **Your company wants to use Activator to reduce downtime by automating responses to equipment sensor warnings. What should you configure to ensure immediate action is taken when a warning is detected?**

- [ ] Conduct regular manual checks of sensor data.
- [ ] Create detailed real-time dashboards for monitoring.
- [x] **Set up activator rules to trigger maintenance workflows.**

📐 **Why:** See [[Unit-7-Automate-Actions]] — Activator's purpose is to *define rules* that fire actions on property thresholds. Dashboards are for humans; manual checks defeat the automation.

## Q6 — Combine two streams

> **Which method would you use to combine temperature and humidity data from two different streams in Microsoft Fabric?**

- [ ] Union transformation
- [ ] Filter transformation
- [x] **Join transformation**

📐 **Why:** See [[Unit-4-Ingest-Transform]] — Stream-to-stream combination on a shared key uses the **Join** transformation. Union stacks rows of identical shape; filter removes rows, doesn't combine.

## Q7 — Activator not responding to event data

> **You notice that your Activator workflow in Microsoft Fabric is not responding to changes in event data as expected. What should you verify first?**

- [x] **The event properties are correctly mapped to the corresponding rules.**
- [ ] The dashboard refresh rate is set correctly.
- [ ] The data transformation logic includes all necessary fields.

📐 **Why:** See [[Unit-7-Automate-Actions]] — Activator's mental model is **Event → Property → Rule**. If properties aren't mapped, rules never evaluate against the right field. Refresh rates and transformations are secondary.

## Q8 — The `project` operator

> **How does the 'project' operator function in KQL queries within Microsoft Fabric?**

- [x] **It selects specific columns to include in the query results.**
- [ ] It filters rows based on specified conditions.
- [ ] It joins data from multiple tables based on a key.

📐 **Why:** See [[Unit-5-Store-Query-KQL]] — `project` is column-selection (analogous to SQL `SELECT col1, col2`). Filtering rows is `where`; combining tables is `join`.

## Q9 — Activator feature for auto-reorder

> **In designing a real-time workflow to manage inventory levels, which Activator feature should be utilized to automatically reorder stock when levels fall below a specified point?**

- [ ] Event transformation
- [x] **Rules**
- [ ] Data sources

📐 **Why:** See [[Unit-7-Automate-Actions]] — **Rules** define the condition-under-which-an-action-fires logic. Events are the records, sources are where the events come from — neither directly triggers reorder logic.

## Q10 — Limit rows in KQL

> **While executing a KQL query, you find that the query returns more rows than expected. Which KQL operator might you need to adjust to limit the number of rows returned?**

- [ ] project
- [x] **take**
- [ ] summarize

📐 **Why:** See [[Unit-5-Store-Query-KQL]] — `take N` caps the row count. `project` shapes columns; `summarize` aggregates (potentially reducing rows, but not as a row-limit operator).

## Q11 — Per-minute average temperature

> **Which transformation would you use in Eventstreams to calculate the average temperature from a stream of sensor data every minute?**

- [ ] Filter transformation
- [ ] Join transformation
- [x] **Aggregate transformation**

📐 **Why:** See [[Unit-4-Ingest-Transform]] — computing an average over time buckets is an **aggregate** operation. Filter restricts rows; join combines streams.

## Q12 — Diagnose IoT ingestion delays

> **Your organization is experiencing delays in processing real-time data from IoT devices. Which Microsoft Fabric component should you check to ensure efficient data ingestion and transformation?**

- [ ] KQL databases
- [ ] Real-Time Hub
- [x] **Eventstreams**

📐 **Why:** See [[Unit-4-Ingest-Transform]] — ingestion + transformation latency lives in the **Eventstream** pipeline. Real-Time Hub is the discovery/catalog surface; KQL DB is the storage target.

## 📊 Self-score

| Question | Your answer | Correct | Notes |
|----------|-------------|---------|-------|
| 1 | ☐ | ✅ Eventstream | Ingest + in-line transform = Eventstream |
| 2 | ☐ | ✅ KQL | Purpose-built for streaming/time-series |
| 3 | ☐ | ✅ Real-Time Dashboards | Tile surface driven by KQL |
| 4 | ☐ | ✅ join | Combine on a shared key |
| 5 | ☐ | ✅ Set up activator rules | Rules are the automation trigger |
| 6 | ☐ | ✅ Join transformation | Stream-to-stream combination |
| 7 | ☐ | ✅ Property mapping | Event → Property → Rule mental model |
| 8 | ☐ | ✅ project | Column selection |
| 9 | ☐ | ✅ Rules | Conditions that fire actions |
| 10 | ☐ | ✅ take | Row-count limiter |
| 11 | ☐ | ✅ Aggregate | Per-window average |
| 12 | ☐ | ✅ Eventstreams | Ingestion + transformation latency |

## 🧭 Next

→ [[Unit-10-Summary]]
← [[Unit-8-Exercise]]
↑ [[_MOC]]