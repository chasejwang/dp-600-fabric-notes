---
title: "Unit 5 — Exercise: Discover and connect to data in OneLake"
module: DP-600
unit: 5 of 7
xp: 100
duration_minutes: 30
source: https://learn.microsoft.com/en-us/training/modules/discover-data-onelake/5-exercise
exercise_url: https://go.microsoft.com/fwlink/?linkid=2352592
tags:
  - dp-600
  - microsoft-fabric
  - exercise
  - lab
  - lakehouse
  - shortcuts
  - sql-analytics-endpoint
  - semantic-models
  - hands-on
---

# Unit 5 — Exercise: Discover and connect to data in OneLake

> [!warning] Interactive lab — not performed here
> This unit is an **interactive Microsoft Learn lab** that runs in a hosted sandbox. It is **not** executed by these notes. The summary below describes what the lab does so you know what to expect when you click the launch button.

## 🧪 Lab summary

> [!quote] Module description
> In this exercise, you create a **lakehouse with sample sales data**, discover it through the **OneLake catalog**, create **shortcuts for cross-workspace access**, query data using the **SQL analytics endpoint**, and explore **semantic models**.

This lab takes approximately **30 minutes** to complete.

## 🛠️ Prerequisites

> [!warning] Workspace requirement
> You need access to a **Microsoft Fabric-enabled workspace** to complete this exercise. For more information, see [**Getting started with Fabric**](https://learn.microsoft.com/en-us/fabric/get-started/fabric-trial) to enable a Fabric trial license.

## 🚀 Launch

[![Launch exercise](https://learn.microsoft.com/en-us/training/wwl/discover-data-onelake/media/launch-exercise.png)](https://go.microsoft.com/fwlink/?linkid=2352592)

Open the lab at: <https://go.microsoft.com/fwlink/?linkid=2352592>

## 🧭 What you'll do (inferred from module description)

| # | Step | What you do | What it teaches |
|---|------|-------------|-----------------|
| 1 | Create a lakehouse | Build a new lakehouse and load sample sales data | The default Fabric item for storing batch data |
| 2 | Discover via the catalog | Find your lakehouse using the OneLake catalog | Search + browse + read metadata |
| 3 | Create a shortcut | Reference data from another workspace into your lakehouse | Zero-copy cross-workspace collaboration (medallion pattern) |
| 4 | Query via SQL endpoint | Use the SQL analytics endpoint to preview and verify the data | Read-only T-SQL access to lakehouse tables |
| 5 | Explore semantic models | Open a semantic model, inspect Overview / Tables / Lineage / Monitor tabs | How to evaluate a semantic model before reporting |

## 🎯 Skills practiced

> [!success] Skills this lab reinforces
> - Creating a Fabric-enabled workspace and a new lakehouse item.
> - Searching the OneLake catalog and reading item metadata.
> - Creating a OneLake shortcut to perform cross-workspace data access without copying.
> - Querying the SQL analytics endpoint with T-SQL to validate shortcut data.
> - Exploring a semantic model's details page and reading its tabs.

## 🔗 Concepts to revisit before the lab

> [!tip] Pre-lab review
> - [[Unit-2-Understand-OneLake]] — what OneLake is and how data is stored.
> - [[Unit-3-Browse-Connect-OneLake]] — catalog navigation, shortcut creation, SQL endpoint, semantic model tabs.
> - [[Unit-4-Discover-Streaming-Data]] — for context on where streaming discovery lives (not exercised here).

## 🔑 Key terms (flashcards)

- **Lakehouse** — Fabric item combining a managed file area with a Delta-Parquet table area.
- **Sample data** — Pre-built dataset Microsoft Learn provides so the lab is self-contained.
- **Shortcut (cross-workspace)** — Pointer to a lakehouse table in another workspace; no copy.
- **SQL analytics endpoint** — Auto-created read-only T-SQL endpoint for every lakehouse.

## 🧭 Next

→ [[Unit-6-Knowledge-Check]]
← [[Unit-4-Discover-Streaming-Data]]
↑ [[_MOC]]
