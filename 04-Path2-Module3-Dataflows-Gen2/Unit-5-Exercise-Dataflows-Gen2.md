---
title: "Unit 5 — Exercise: Transform data with Dataflows Gen2"
module: DP-600
unit: 5 of 7
xp: 100
duration_minutes: 30
source: https://learn.microsoft.com/en-us/training/modules/fabric-transform-data-dataflows/5-exercise/
tags:
  - dp-600
  - microsoft-fabric
  - dataflows-gen2
  - exercise
  - lab
  - lakehouse
---

# Unit 5 — Exercise: Transform data with Dataflows Gen2

> [!quote] Source
> Microsoft Learn · Path 2 · Module 3 · Unit 5 · "Exercise: Transform data with Dataflows Gen2"
> <https://learn.microsoft.com/en-us/training/modules/fabric-transform-data-dataflows/5-exercise/>

## 🎯 Purpose

A **30-minute hands-on lab** that consolidates everything from Units 2–4: connect to a sample data source with Power Query, apply transformations and custom columns, configure a lakehouse destination, and publish + verify the dataflow.

> [!warning] Lab access requirement
> You need access to a **Fabric-enabled workspace** to complete this exercise. For information about a trial license, see [Getting started with Fabric](https://learn.microsoft.com/en-us/fabric/get-started/fabric-trial).

## 🧪 What the lab does

In this exercise you create a **Dataflow Gen2** to connect to **sample data**, apply **Power Query transformations** to filter, clean, and shape the data, and **load the results to a lakehouse table**.

The exercise walks through four tasks:

| # | Task | What you do |
|---|---|---|
| 1 | **Create a Dataflow Gen2 and connect to a data source** | New item → Dataflow Gen2 → **Get data** → pick a sample data connector |
| 2 | **Apply transformations and custom columns** | Use ribbon + right-click transformations in the data preview; add a custom column with Power Query |
| 3 | **Configure a lakehouse as the data destination** | Choose Lakehouse destination, select update method (Replace / Append), pick target table name |
| 4 | **Publish the dataflow and verify results** | Publish; then check the resulting table in the lakehouse |

## 🔗 Launch

> [!info] Launch the exercise
> Click the button below to launch the exercise in the Microsoft Learn lab environment.
> [![Button to launch exercise.](https://learn.microsoft.com/en-us/training/wwl/fabric-transform-data-dataflows/media/launch-exercise.png)](https://go.microsoft.com/fwlink/?linkid=2361021)
>
> Approximate time to complete: **30 minutes**.

## 🧠 Map back to the units

| Lab task | Reinforces concepts from |
|---|---|
| Create Dataflow Gen2 + Get data | [[Unit-2-Understand-Dataflows]] — what dataflows are + how they're created |
| Apply transformations + custom columns | [[Unit-3-Transform-Power-Query]] — Power Query Online, transformations, M language |
| Configure lakehouse destination | [[Unit-2-Understand-Dataflows]] — output destinations (Lakehouse is one of the supported targets) |
| Publish + verify | [[Unit-3-Transform-Power-Query]] — applied steps become the auditable recipe |
| (Implicit) Keeping refresh fast | [[Unit-4-Optimize-Performance]] — Modern Query Evaluator + folding + best practices |

> [!tip] Don't skip
> This is the only **hands-on** unit in the module. Doing it (or at least walking through the steps mentally) is the difference between *knowing* the concepts and being able to **build a dataflow end-to-end** on the exam.

## 🧭 Next

→ [[Unit-6-Knowledge-Check]]
← [[Unit-4-Optimize-Performance]]
↑ [[_MOC]]