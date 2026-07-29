---
title: "Unit 1 — Introduction"
module: DP-600
unit: 1 of 7
xp: 100
duration_minutes: 3
source: https://learn.microsoft.com/en-us/training/modules/enforce-semantic-model-security/1-introduction
tags:
  - dp-600
  - microsoft-fabric
  - power-bi
  - semantic-model
  - security
  - rls
  - ols
  - row-level-security
  - object-level-security
---

# Unit 1 — Introduction

## 🎯 Why this matters

**Semantic model security** controls which data users can access when they query your Power BI semantic models. Without security, anyone with query access to a semantic model can view **all** data in the model. By implementing security, you restrict data visibility to only authorized users.

> [!info] The core idea
> Semantic model security isn't a single feature — it's two complementary mechanisms (**RLS** for rows, **OLS** for objects) that must be designed together to protect data across every consumption path.

## 🏢 Scenario

Suppose you work at a retail analytics organization with regional sales teams across multiple territories.

- **Sales managers** need to view performance data for their own region but shouldn't access data for other regions.
- The **HR department** maintains employee records with sensitive salary information that only authorized payroll staff should see.
- As the organization adopts **Copilot in Power BI** for natural language queries, you need to ensure that security boundaries apply to **every access path**, not just traditional reports.

> [!warning] AI surfaces extend the security perimeter
> When you enable Copilot or Fabric data agents on a semantic model, every NL question becomes a query. If your model has no security, every answer can leak. **RLS + OLS protect NL queries the same way they protect visual queries.**

## 📚 What you will learn

In this module, you learn how to:

1. Implement **row-level security (RLS)** using DAX filter expressions, including **dynamic patterns** that scale without per-user role updates.
2. Explore **object-level security (OLS)** to hide tables and columns from unauthorized roles.
3. **Test security configurations** in Power BI Desktop and the service.
4. **Manage role membership** in the Fabric portal.

> [!success] By the end of this module, you can implement RLS and OLS in semantic models, test security configurations, and manage role membership to ensure that every user sees only the data they're authorized to access.

## 🧭 Module map

| # | Unit | Focus |
|---|------|-------|
| 1 | [Introduction](./Unit-1-Introduction.md) | Why semantic model security matters |
| 2 | [Implement row-level security](./Unit-2-Row-Level-Security.md) | RLS via DAX filter expressions; static vs dynamic |
| 3 | [Apply object-level security](./Unit-3-Object-Level-Security.md) | Hide tables and columns with Tabular Editor |
| 4 | [Test security and manage roles](./Unit-4-Test-Manage-Roles.md) | View as, Test as role, Entra groups |
| 5 | [Exercise — Implement RLS](./Unit-5-Exercise.md) | Hands-on lab (≈30 min) |
| 6 | [Knowledge check](./Unit-6-Knowledge-Check.md) | 5 questions |
| 7 | [Summary](./Unit-7-Summary.md) | Recap + further reading |

> [!tip] Two-axis mental model
> - **RLS** answers "**which rows** can this user see?"
> - **OLS** answers "**which columns and tables** can this user see at all?"
>
> You almost always need both. RLS alone still lets users see the `Salary` column they shouldn't have; OLS alone still lets every manager see every row.

## 🔑 Key terms (flashcards)

- **Semantic model security** — the umbrella term for RLS + OLS rules in a Power BI model.
- **Row-level security (RLS)** — DAX filter expressions on tables that filter which rows a user sees.
- **Object-level security (OLS)** — permissions that hide specific tables or columns from a role.
- **Role** — a named container of filter expressions and OLS permissions; users are assigned to roles.

## 🧭 Next

→ [Unit 2 — Implement row-level security](./Unit-2-Row-Level-Security.md)
↑ [_MOC](./_MOC.md)