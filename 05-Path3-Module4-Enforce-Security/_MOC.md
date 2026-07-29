---
title: "Module — Enforce semantic model security"
module: DP-600
unit_index: 4 of 4
status: complete
xp_total: 800
duration_minutes: 67
source: https://learn.microsoft.com/en-us/training/modules/enforce-semantic-model-security/
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
  - dynamic-security
  - security-table
  - userprincipalname
  - tabular-editor
  - microsoft-entra
  - copilot
  - fabric-data-agents
---

# Module — Enforce semantic model security

> [!info] Module map
> This is the **security** module of the Fabric Analytics Engineer track. The model you build in Power Query is data; the DAX you write is answers; the **security** you configure is the **boundary** that decides who gets which answers. The module covers two complementary mechanisms — **RLS** (filter which rows a user sees) and **OLS** (hide which tables and columns a user sees) — plus the **testing** and **role-management** workflow that keeps them trustworthy in production. Mastery here is what lets you put sensitive data in front of the right people without leaking it to the wrong ones.

## 🎯 Learning objectives (from Microsoft Learn)

By the end of this module you should be able to:

1. **Implement row-level security (RLS)** with DAX filter expressions on roles — including **static** rules for fixed partitions and **dynamic** rules using `USERPRINCIPALNAME()` plus a **security table** for scalable, data-driven authorization.
2. **Implement object-level security (OLS)** by using **Tabular Editor** to set `None` permissions on tables and columns, hiding both data and metadata from unauthorized roles.
3. **Test security configurations** using **View as** in Power BI Desktop and **Test as role** in the Power BI service.
4. **Manage role membership** in the Fabric portal using **Microsoft Entra security groups** for scalable, delegated administration.
5. **Understand AI consumption paths** — how RLS and OLS protect Copilot chat and Fabric data agents the same way they protect traditional reports.

## 🧠 Module mind map

> [!tip] How to use
> The mind map below is duplicated as a standalone Mermaid file (`Module-Mind-Map.md`) you can open in Obsidian's Mermaid preview or the [Mermaid Live Editor](https://mermaid.live). It is the **single-page view** of the entire module.

```mermaid
mindmap
  root((Semantic Model Security<br/>Module — Path 3 / M4))
    Row-Level Security (RLS)
      Roles in Modeling tab
        Manage roles
        DAX filter expression
        One role can span tables
      Star-schema filter flow
        Filter dim table
        Relationships propagate to fact
        Faster than fact filter
      Static RLS
        Hardcoded values
        [Region] = "Midwest"
        Small fixed scenarios
        Model republish to change
      Dynamic RLS
        USERPRINCIPALNAME()
        Returns user@domain.com
        Preferred over USERNAME()
        Scales without model change
      Security table pattern
        Maps users to partitions
        CONTAINS lookup
        Many-to-many assignments
        Data-driven updates
    Object-Level Security (OLS)
      Defined in Tabular Editor
        External tool, Analysis Services
        Power BI Desktop has no native UI
      None vs Read
        None hides object + metadata
        Read is default
      Hide entire table
        Lookup tables, dev artifacts
      Hide specific column
        Most common pattern
        PII / salary / cost data
      OLS limitations
        Measures not directly hidable
        Workspace Admin/Member bypass
        Relationship chain rule
        No Quick Insights / Smart Narrative
        Errors look like missing fields
      OLS + RLS together
        Different roles per type
        Layered protection
        OLS blocks Copilot too
    Testing & Role Management
      View as in Desktop
        Modeling tab
        Other user email field
        Edge-case users
      Test as role in service
        More options → Security
        Re-validate after publish
        DirectQuery + SSO differences
      Assign role members
        Semantic model owner only
        Users / Entra groups / SPNs
        M365 groups NOT supported
      Entra security groups
        Bulk membership
        Delegated to IT
        One assignment covers many
      Workspace vs RLS
        Workspace roles = access
        RLS = data scope
        Admin/Member/Contributor bypass RLS
      Common mistakes
        Viewer without RLS role
        Bidirectional filter leaks
        Broken relationship chains
        Skipping post-publish test
        Additive multi-role union
    AI Consumption Paths
      Copilot respects RLS
      Data agents use NL2DAX
      OLS hides columns from NL
      User identity flows through
    Knowledge Check
      Q1 Dynamic RLS + security table
      Q2 OLS for column restriction
      Q3 Viewer without role = unfiltered
      Q4 View as in Desktop
      Q5 Entra security groups
```

## 📑 Unit breakdown

| # | Unit | XP | Minutes | Focus |
|---|------|----|---------|-------|
| 1 | [Introduction](./Unit-1-Introduction.md) | 100 | 3 | Why semantic model security matters; scenario (regional sales + HR salary) |
| 2 | [Implement row-level security](./Unit-2-Row-Level-Security.md) | 100 | 12 | RLS via DAX filter expressions; static vs dynamic; `USERPRINCIPALNAME()`; **security table pattern**; `USERNAME()` vs `USERPRINCIPALNAME()`; DirectQuery + SSO; RLS performance |
| 3 | [Apply object-level security](./Unit-3-Object-Level-Security.md) | 100 | 8 | OLS via **Tabular Editor**; hide tables vs columns; relationship-chain rule; **combine with RLS**; OLS blocks Copilot |
| 4 | [Test security and manage roles](./Unit-4-Test-Manage-Roles.md) | 100 | 9 | **View as** in Desktop; **Test as role** in service; role membership; **Entra security groups**; workspace-vs-RLS interaction; common mistakes; AI consumption paths |
| 5 | [Exercise — Implement RLS](./Unit-5-Exercise.md) | 100 | 30 | Hands-on lab: build a sales semantic model, configure static + dynamic RLS, test, publish, manage role membership |
| 6 | [Knowledge check](./Unit-6-Knowledge-Check.md) | 200 | 3 | 5 knowledge-check questions |
| 7 | [Summary](./Unit-7-Summary.md) | 100 | 2 | Recap + further reading |

**Total: 800 XP · 67 minutes (1 hr 7 min)**

## 🔗 Knowledge-check answers (unit 6)

> [!warning] Answer provenance
> Microsoft Learn intentionally does not publish the correct answers for knowledge-check questions. The answers below are **derived from the unit content** for this module and the wording of each question. Treat them as best-effort study notes — verify against the live module if you fail the check.

| Q | Question | Correct answer |
|---|----------|----------------|
| 1 | Scalable solution for "managers see only their assigned region, no model change when they switch regions"? | **Dynamic RLS with `USERPRINCIPALNAME()` + a security table** that maps managers to regions. Static RLS for each region requires new roles/republish; OLS hides columns, not rows. |
| 2 | HR salary column visible to HR only while general managers keep the rest of the Employee table? | **Object-level security on the `Salary` column**. RLS filters rows, not columns; removing the column from the model hurts everyone. |
| 3 | Viewer sees all data after RLS is published? | **User hasn't been assigned to an RLS role in the service**. Syntax errors surface in Desktop validation; import vs DirectQuery is irrelevant. |
| 4 | Test RLS before publishing? | **Use the View as feature on the Modeling tab in Power BI Desktop** to preview data as a specific role. |
| 5 | Manage membership for 200 sales reps across 5 regions? | **Map Microsoft Entra security groups to roles**, one group per region. M365 groups aren't supported for Power BI role membership. |

## 🧭 Downstream links

- [[Unit-1-Introduction]] · [[Unit-2-Row-Level-Security]] · [[Unit-3-Object-Level-Security]] · [[Unit-4-Test-Manage-Roles]] · [[Unit-5-Exercise]] · [[Unit-6-Knowledge-Check]] · [[Unit-7-Summary]]
- [[Module-Mind-Map]]
- Sister modules on Path 3:
  - [[../05-Path3-Module1-DAX-Calculations/_MOC|Module M1 — Create DAX calculations]]
  - [[../05-Path3-Module2-Design-for-Scale/_MOC|Module M2 — Design and build scalable semantic models]]
  - [[../05-Path3-Module3-Optimize-Performance/_MOC|Module M3 — Optimize a semantic model]]

## 📚 External references

- Microsoft Learn module page: <https://learn.microsoft.com/en-us/training/modules/enforce-semantic-model-security/>
- [Row-level security (RLS) with Power BI](https://learn.microsoft.com/en-us/power-bi/enterprise/service-admin-rls)
- [Object-level security (OLS) in Fabric](https://learn.microsoft.com/en-us/fabric/security/service-admin-object-level-security)
- [`USERPRINCIPALNAME()` DAX reference](https://learn.microsoft.com/en-us/dax/userprincipalname-function-dax/)
- [`USERNAME()` DAX reference](https://learn.microsoft.com/en-us/dax/username-function-dax/)
- [`CONTAINS` DAX reference](https://learn.microsoft.com/en-us/dax/contains-function-dax/)
- [Tabular Editor](https://tabulareditor.com/)
- [Getting started with Microsoft Fabric (trial license)](https://learn.microsoft.com/en-us/fabric/get-started/fabric-trial)
- DP-600 learning path: <https://learn.microsoft.com/en-us/training/paths/dax-power-bi/>