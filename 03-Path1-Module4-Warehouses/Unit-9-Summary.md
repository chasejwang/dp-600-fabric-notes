---
title: "Unit 9 — Summary"
module: DP-600
unit: 9 of 9
xp: 100
duration_minutes: 1
source: https://learn.microsoft.com/en-us/training/modules/get-started-data-warehouse/9-summary
tags:
  - dp-600
  - microsoft-fabric
  - data-warehouse
  - summary
---

# Unit 9 — Summary

> [!quote] Source
> Microsoft Learn · Module 4 · Unit 9 · "Summary"
> <https://learn.microsoft.com/en-us/training/modules/get-started-data-warehouse/9-summary>

## 📝 Verbatim recap

> In this module, you learned how data warehouses use dimensional modeling to organize data into fact and dimension tables, and what makes a Fabric data warehouse unique. You explored querying and transforming data with T-SQL and the visual query editor, structured tables into a star schema, and applied security features like row-level security and dynamic data masking to protect your data.
>
> Without a platform like Microsoft Fabric, building this kind of warehouse environment would require provisioning and managing dedicated SQL infrastructure, configuring separate storage and compute, and manually integrating data across siloed systems. A Fabric data warehouse eliminates that complexity by combining full T-SQL capabilities with OneLake integration in a single, governed platform that supports both traditional analytics and AI-powered experiences.
>
> To learn advanced T-SQL transformation patterns like staging workflows, incremental loads, and MERGE-based upserts, continue to the [Transform data using T-SQL](https://learn.microsoft.com/en-us/training/modules/modify-data-with-transact-sql/) module.

## 🧠 Key takeaway diagram

```mermaid
flowchart LR
    subgraph Modeling["Dimensional Modeling"]
      F[Fact tables<br/>numbers]
      D[Dimension tables<br/>context]
      Star[Star schema]
      Snow[Snowflake schema]
      F --> Star
      D --> Star
      D --> Snow
    end

    subgraph FabricWh["Fabric Data Warehouse"]
      TSQL[Full T-SQL<br/>DDL/DML/MERGE]
      OL[Delta on OneLake]
      XD[Cross-database<br/>three-part queries]
      Clone[Zero-copy clones]
      TSQL --> OL
      OL --> XD
      OL --> Clone
    end

    subgraph Query["Query & Transform"]
      SQLE[SQL query editor<br/>+ Copilot]
      VQE[Visual query editor]
      View[Views]
      SP[Stored procedures]
      SQLE --> View
      VQE --> View
      SQLE --> SP
    end

    subgraph ModelPub["Modeling & Publishing"]
      Prep[Prepare for consumption<br/>hide, rename, describe]
      Rel[Relationships<br/>cardinality, cross-filter]
      Meas[Measures<br/>single source of truth]
      SM[Direct Lake<br/>semantic model]
      Prep --> Rel --> Meas --> SM
    end

    subgraph Secure["Secure & Monitor"]
      Sec[Layered security<br/>workspace · item · T-SQL]
      Mon[Query insights + DMVs]
    end

    Modeling --> FabricWh
    FabricWh --> Query
    Query --> ModelPub
    ModelPub --> Secure
    Secure --> Value[Traditional analytics<br/>+ AI experiences<br/>on one platform]
```

## 🔑 One-paragraph synthesis

A Fabric data warehouse gives you **full transactional T-SQL on Delta files in OneLake** — facts and dimensions organized into a star schema, ingested via `COPY INTO` / `OPENROWSET` / pipelines / cross-database queries, queried through the SQL or Visual editor, and transformed via views and stored procedures. Modeling choices — hidden internals, business-friendly names, descriptions, defined relationships, and centralized measures — make the warehouse intelligible to analysts **and** to AI tools like Copilot and Fabric IQ data agents. **Direct Lake semantic models** publish that data straight to Power BI without copies. Layered security (workspace roles → item permissions → object/row/column/masking) governs who sees what, and **Query insights + DMVs** keep watch on performance. Result: one governed platform for both traditional analytics and AI-powered experiences.

## 📚 Learn more (Microsoft docs)

- [What is Fabric Data Warehouse?](https://learn.microsoft.com/en-us/fabric/data-warehouse/data-warehousing)
- [Query the warehouse](https://learn.microsoft.com/en-us/fabric/data-warehouse/query-warehouse)
- [Transform data using T-SQL (next module)](https://learn.microsoft.com/en-us/training/modules/modify-data-with-transact-sql/)
- [Design dimensional models in Microsoft Fabric](https://learn.microsoft.com/en-us/training/modules/design-dimensional-models-fabric)
- [Secure a Microsoft Fabric data warehouse](https://learn.microsoft.com/en-us/training/modules/secure-data-warehouse-in-microsoft-fabric/)

## 🧭 Done with Module 4

← [[Unit-8-Module-Assessment]]
↑ [[_MOC]]

**Next module candidate:** "Transform data using T-SQL" — advanced staging workflows, incremental loads, and MERGE-based upserts.