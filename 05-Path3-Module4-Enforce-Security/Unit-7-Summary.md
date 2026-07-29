---
title: "Unit 7 — Summary"
module: DP-600
unit: 7 of 7
xp: 100
duration_minutes: 2
source: https://learn.microsoft.com/en-us/training/modules/enforce-semantic-model-security/7-summary
tags:
  - dp-600
  - rls
  - ols
  - power-bi
  - summary
  - copilot
  - fabric
---

# Unit 7 — Summary

## 🎯 Recap

Your organization needed to ensure that different user groups see only the data they're authorized to access. Sales managers should see only their region's data, and sensitive employee information like salary should be restricted to authorized payroll staff.

> [!success] What you learned
> You learned how to implement row-level security using **dynamic DAX filter expressions** with `USERPRINCIPALNAME()` and the **security table pattern**. You applied **object-level security** to hide sensitive tables and columns from unauthorized roles. You then tested security configurations in **Power BI Desktop and the service**, and managed role membership using **Microsoft Entra security groups**.

## 🛡️ Security applies to every access path

With these security configurations in place, your semantic models enforce data protection across **all consumption paths**:

| Consumption path | Honored by |
|------------------|------------|
| Power BI reports | RLS + OLS |
| Paginated reports | RLS + OLS |
| **Copilot** chat (NL2DAX) | RLS + OLS |
| **Fabric data agents** (NL2DAX) | RLS + OLS |

> [!quote] The key takeaway
> Reports, Copilot chat, and Fabric data agents all respect the same RLS and OLS rules you defined — ensuring consistent authorization **regardless of how users access the data**.

## ✅ You can now

- Implement **RLS** in semantic models using dynamic DAX filter expressions and security tables.
- Implement **OLS** in semantic models using Tabular Editor to hide tables and columns.
- **Test** security configurations in Power BI Desktop (**View as**) and in the Power BI service (**Test as role**).
- **Manage role membership** using Microsoft Entra security groups for scalability.
- Recognize and avoid common security misconfigurations (unassigned viewers, bidirectional filter leaks, broken relationships, additive role union).

## 📚 Learn more (external references)

- [Row-level security (RLS) with Power BI](https://learn.microsoft.com/en-us/power-bi/enterprise/service-admin-rls)
- [Object-level security (OLS)](https://learn.microsoft.com/en-us/fabric/security/service-admin-object-level-security)
- `USERPRINCIPALNAME()` reference: <https://learn.microsoft.com/en-us/dax/userprincipalname-function-dax/>
- Tabular Editor download: <https://tabulareditor.com/>

## 🔁 Module self-check

Before you move on, can you:

- [ ] Write a static RLS rule for a single region?
- [ ] Write a dynamic RLS rule using `USERPRINCIPALNAME()` against a security table?
- [ ] Explain why you filter dimension tables, not fact tables?
- [ ] Open Tabular Editor and set `None` permission on a column?
- [ ] Use **View as** in Desktop to validate a dynamic rule with a test email?
- [ ] Map an Entra security group to a role in the Fabric portal?

## 🧭 Next

← [Unit 6 — Knowledge check](./Unit-6-Knowledge-Check.md)
↑ [_MOC](./_MOC.md)
→ Next module: [[../05-Path3-Module3-Optimize-Performance/_MOC|Module M3 — Optimize a semantic model]] (or your next module in the path)