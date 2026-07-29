---
title: "Module — Design semantic models for scale in Microsoft Fabric"
module: DP-600
unit_index: "Module 2 of Learning Path 3"
status: complete
xp_total: 900
duration_minutes: 65
source: https://learn.microsoft.com/en-us/training/modules/design-semantic-models-scale/
tags:
  - dp-600
  - microsoft-fabric
  - semantic-model
  - star-schema
  - direct-lake
  - dax
  - calculation-group
  - aggregation
  - xmla-endpoint
  - query-scaleout
  - large-model-storage-format
---

# Module — Design semantic models for scale in Microsoft Fabric

> [!info] Module map
> Path 3 Module 2 in the **Fabric Analytics Engineer** (DP-600) track. This module is the **scale-design module** for semantic models: how to choose a storage mode that fits the data, design a star schema that holds up at volume, write calculations that scale with team size and measure count, and configure the settings that unlock large-model, high-concurrency, and external-tool scenarios. Includes a 30-minute hands-on lab and a 5-question knowledge check.

## 🎯 Learning objectives (synthesized from unit-level goals)

By the end of this module you should be able to:

1. **Choose** the right storage mode (Direct Lake, Import, DirectQuery, Composite) for a Fabric semantic model based on data location, freshness, and performance needs.
2. **Design** a star schema in a semantic model — fact and dimension tables, referential integrity, inactive relationships, and cross-source composite arrangements.
3. **Design** scalable calculations — calculation groups, DAX variables and naming conventions, iterators vs. aggregation functions, and aggregations for large fact tables.
4. **Configure** scale settings — large semantic model storage format, XMLA endpoint read/write, query scaleout, Direct Lake fallback, and OneLake integration.
5. **Apply** all four design decisions end-to-end in a Fabric semantic model through a guided hands-on exercise.

## 🧠 Module mind map

> [!tip] How to use
> The mind map below is duplicated as a standalone Mermaid file (`Module-Mind-Map.md`) you can open in Obsidian's Mermaid preview or the [Mermaid Live Editor](https://mermaid.live). It is the **single-page view** of the entire module.

```mermaid
mindmap
  root((Semantic<br/>Models for<br/>Scale))
    Storage Mode
      Direct Lake
        Default in Fabric
        Reads Delta tables from OneLake
        No scheduled refresh
        Large model format auto-on
      Import
        In-memory copy
        Fastest queries
        Non-Fabric sources
      DirectQuery
        Live source queries
        Real-time needs
      Composite
        Mixed modes per table
        Cross-source joins
    Fallback
      Allow fallback
      Disallow fallback
    Star Schema
      Fact tables
        Measurable events
      Dimension tables
        Descriptive context
      Relationships
        One-to-many
        Many-to-many via bridge
        Bi-directional (sparingly)
        Referential integrity
        Inactive + USERELATIONSHIP
      Snowflake handling
        Flatten to star
        Preserve if shared subdims
      Cross-source
        Composite models
    Scalable Calculations
      Calculation groups
        SELECTEDMEASURE()
        Dynamic format strings
        Time intelligence
      DAX readability
        Variables
        Naming conventions
        Iterators vs aggregations
        Information functions
      Aggregations
        Pre-summarized tables
        High-grain summary queries
    Scale Settings
      Large semantic model storage format
        Removes 10 GB limit
        Prerequisite for XMLA + scaleout
      XMLA endpoint read/write
        Tabular Editor
        DAX Studio
        CI/CD
      Query scaleout
        Read replicas
        High concurrency
      Direct Lake fallback
        Allow vs disallow
      OneLake integration
        Expose model as Delta tables
```

## 📑 Unit breakdown

| # | Unit | XP | Minutes | Focus |
|---|------|----|---------|-------|
| 1 | [Introduction](./Unit-1-Introduction.md) | 100 | 2 | What changes when a model moves from small-team to scale |
| 2 | [Choose a storage mode](./Unit-2-Storage-Modes.md) | 100 | 7 | Direct Lake, Import, DirectQuery, Composite + fallback |
| 3 | [Design star schema for semantic models](./Unit-3-Star-Schema.md) | 100 | 7 | Relationships, referential integrity, inactive, cross-source |
| 4 | [Design scalable calculations](./Unit-4-Calculation-Patterns.md) | 100 | 7 | Calculation groups, DAX discipline, aggregations |
| 5 | [Configure settings for scale](./Unit-5-Scale-Settings.md) | 100 | 7 | Large model format, XMLA, scaleout, fallback, OneLake |
| 6 | [Exercise: Design a semantic model for scale in Fabric](./Unit-6-Exercise.md) | 100 | 30 | Hands-on lab in a Fabric workspace |
| 7 | [Knowledge check](./Unit-7-Knowledge-Check.md) | 200 | 3 | 5 questions derived from module content |
| 8 | [Summary](./Unit-8-Summary.md) | 100 | 2 | Recap + learn-more links |

**Total: 900 XP · ~65 minutes (~1 hr 5 min)**

## 🔗 Knowledge-check answers (unit 7)

Microsoft Learn does not display the correct answers; the table below is derived from the unit content.

| # | Question topic | Correct answer |
|---|----------------|----------------|
| 1 | Default storage mode for a new Fabric semantic model with data in a lakehouse | **Direct Lake** — reads Delta tables from OneLake without importing data |
| 2 | Pattern to avoid 180 extra measures (YTD/QTD/MTD × 60 base) | **A calculation group with time intelligence items using `SELECTEDMEASURE()`** |
| 3 | Prerequisite for XMLA endpoint read/write access | **Large semantic model storage format** |
| 4 | Benefit of "Assume referential integrity" on a Direct Lake relationship | **Engine uses INNER joins instead of LEFT OUTER joins, reducing rows processed** |
| 5 | Pattern that improves query performance for monthly/quarterly summaries on a 150M-row fact | **Aggregation tables precalculated at the monthly and quarterly grain** |

See [[Unit-7-Knowledge-Check]] for full reasoning.

## 🧭 Downstream links

- [[Unit-1-Introduction]] · [[Unit-2-Storage-Modes]] · [[Unit-3-Star-Schema]] · [[Unit-4-Calculation-Patterns]] · [[Unit-5-Scale-Settings]] · [[Unit-6-Exercise]] · [[Unit-7-Knowledge-Check]] · [[Unit-8-Summary]]
- [[Module-Mind-Map]]
- Parent MOC — `../02-Study-Guide-Index/_MOC.md`

## 📚 External references

- Microsoft Learn module page: <https://learn.microsoft.com/en-us/training/modules/design-semantic-models-scale/>
- [Direct Lake overview](https://learn.microsoft.com/en-us/fabric/fundamentals/direct-lake-overview)
- [Semantic model storage modes (Power BI guidance)](https://learn.microsoft.com/en-us/power-bi/guidance/powerbi-implementation-planning/storage-mode-preference)
- [Calculation groups in Power BI](https://learn.microsoft.com/en-us/power-bi/transform-model/calculation-groups)
- [Large semantic model storage format](https://learn.microsoft.com/en-us/fabric/enterprise/powerbi/service-premium-large-models)
- [Query scaleout for semantic models](https://learn.microsoft.com/en-us/fabric/enterprise/powerbi/service-premium-scale-out)
