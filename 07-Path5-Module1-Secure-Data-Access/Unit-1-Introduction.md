---
title: "Unit 1 — Introduction"
module: DP-600
unit: 1 of 7
xp: 100
duration_minutes: 2
source: https://learn.microsoft.com/en-us/training/modules/secure-data-access-in-fabric/1-introduction
tags:
  - dp-600
  - microsoft-fabric
  - security
  - introduction
  - least-privilege
  - workspace-roles
  - item-permissions
  - onelake-security
  - t-sql-permissions
---

# Unit 1 — Introduction

## 🎯 Why this matters

**Microsoft Fabric** has a **layered security model** that lets you control who can access data — and how much of it they can see. You assign access at the level that matches each user's needs, from an entire workspace down to individual tables and folders. Without thinking carefully about access at every layer, the same data that's available to a data engineer can also be available to a report consumer who has no business seeing it.

> [!info] The core idea
> Fabric security isn't a single switch — it's a **stack of independent layers**, each finer-grained than the last. The platform's job is to make every layer composable so you can give every user *exactly* the access they need (and nothing more).

## 🏢 Scenario

Suppose you're a **Fabric administrator** at a **healthcare company**. Your organization stores data across lakehouses and warehouses in Fabric — patient records, insurance claims, and clinical trial results. Different team members need different levels of access:

- **Data engineers** build pipelines and need broad workspace access.
- **Analysts** query specific datasets.
- **Report consumers** only view dashboards.

You need to make sure each person can do their job without seeing data they shouldn't.

> [!warning] One workspace, many audiences
> A single Fabric workspace can hold data for every team in the org — engineering, analytics, business, executive. If access is "all or nothing" at the workspace level, you've either locked out the analysts or leaked the patient records to the dashboards. The layered model exists so you don't have to choose.

## 📚 What you will learn

In this module, you explore Fabric's security model, learn how workspace roles and item permissions control access to Fabric items, and see how **T-SQL permissions** and **OneLake security roles** provide granular control over the data within those items.

By the end of this module, you'll be able to configure the right level of access for each user, from **workspace roles** to **OneLake security roles**, following the **principle of least privilege**.

> [!success] By the end of this module
> You can map every user (data engineer, analyst, report consumer) to the right combination of workspace role, item permission, and granular data control — without granting more access than they need.

## 🧭 Module map

| # | Unit | Focus |
|---|------|-------|
| 1 | [Introduction](./Unit-1-Introduction.md) | Why Fabric security matters; healthcare scenario |
| 2 | [Understand the Fabric security model](./Unit-2-Understand-Fabric-Security-Model.md) | Three evaluation levels; four data-security controls |
| 3 | [Configure workspace and item permissions](./Unit-3-Configure-Workspace-and-Item-Permissions.md) | Workspace roles + lakehouse sharing |
| 4 | [Apply granular permissions](./Unit-4-Apply-Granular-Permissions.md) | T-SQL permissions + OneLake security roles |
| 5 | [Exercise — Secure data access in Microsoft Fabric](./Unit-5-Exercise.md) | Hands-on lab (≈45 min, 2 user accounts) |
| 6 | [Knowledge check](./Unit-6-Knowledge-Check.md) | 12 questions |
| 7 | [Summary](./Unit-7-Summary.md) | Decision rule: workspace → item → granular |

> [!tip] The four-layer mental model
> Whenever a user tries to read Fabric data, the platform checks (in order):
> 1. **Microsoft Entra ID authentication** — can they sign in?
> 2. **Fabric access** — do they have a Fabric license / role?
> 3. **Workspace role or item permission** — what workspace or item is this?
> 4. **Granular data security** — T-SQL permissions or OneLake security roles
>
> Each layer is independent. A user can pass the first three and still be denied by the fourth.

## 🔑 Key terms (flashcards)

- **Layered security model** — Fabric evaluates access at multiple independent layers; the narrowest layer that lets a user do their job is the right one.
- **Workspace role** — broad access permission (Admin / Member / Contributor / Viewer) that applies to all items in a workspace.
- **Item permission** — a share-time permission on a specific Fabric item (lakehouse, warehouse, etc.).
- **T-SQL permission** — `GRANT` / `DENY` / `REVOKE` statements that control access via the SQL analytics endpoint.
- **OneLake security role** — a role that grants access to specific tables or folders and is enforced across Spark, SQL, and OneLake APIs.
- **Principle of least privilege** — give every user exactly the access they need, no more.

## 🧭 Next

→ [Unit 2 — Understand the Fabric security model](./Unit-2-Understand-Fabric-Security-Model.md)
↑ [_MOC](./_MOC.md)
