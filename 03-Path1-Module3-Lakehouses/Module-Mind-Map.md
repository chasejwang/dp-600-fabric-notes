---
title: "Module 3 — Mind Map (Mermaid)"
module: DP-600
type: mind-map
source: _MOC.md
tags:
  - dp-600
  - mind-map
  - mermaid
  - lakehouse
  - microsoft-fabric
---

# Module 3 — Get started with lakehouses in Microsoft Fabric · Mind Map

```mermaid
mindmap
  root((Fabric Lakehouse<br/>Module 3))
    What is a Lakehouse
      Lake flexibility plus warehouse SQL
      Built on OneLake and Delta Lake
      Eliminates lake vs warehouse trade-off
      AI-ready data foundation
    Lakehouse Design
      Tables area
        Delta Lake tables
        ACID and schema enforced
        SQL-queryable
        Power BI read
      Files area
        Any native format
        CSV JSON Parquet images docs
        Staging zone
      SQL analytics endpoint
        Read-only T-SQL
        Views and functions
        Row and column level security
    Two Explorer Modes
      Lakehouse explorer
        Add tables files folders
        Upload create manage
        Reference lakehouses side by side
      SQL analytics endpoint
        Read-only T-SQL
        Cannot modify underlying data
    Schemas
      Enabled by default
      dbo created automatically
      Group tables by domain
        sales
        marketing
        hr
      Schema-level permissions
      Four-part namespace
        workspace dot lakehouse dot schema dot table
    Delta Lake
      Open-source storage layer
      ACID transactions
      Schema enforcement
      Time travel and rollback
      Efficient updates and deletes
      Parquet files plus transaction log
    Security Layers
      Workspace roles
      Item-level sharing
      Row-level security SQL
      Column-level security SQL
      Schema-level permissions
      Sensitivity labels
      Microsoft Purview extension
    Ingest Five Paths
      Upload local files
      Load to Table
        No-code
        Parquet and CSV
        Append or overwrite
      Dataflows Gen2 Power Query
      Notebooks Apache Spark
      Data Factory pipelines Copy activity
    Shortcuts
      Zero-copy references
      ADLS Gen2 S3 Dataverse
      OneLake managed credentials
      Identity-based auth at target
      Schema shortcuts Delta folders
    Transform
      Notebooks PySpark SQL Scala
      Dataflows Gen2 Power Query
      Pipelines visual orchestration
      Copilot generates Spark code
    Query Three Paths
      SQL endpoint
        Ad-hoc queries
        BI connections Power BI Excel
        Data validation
        Views
        RLS and CLS
        Copilot for SQL
      Spark notebooks
        Spark SQL syntax
        PySpark DataFrame API
        Exploratory data analysis
        ML preparation
        Cross-workspace four-part joins
        Copilot for notebooks
      Power BI
        Query SQL endpoint
        Semantic model
        Direct Lake default mode
          Reads Delta Parquet directly
          No copy
        Copilot in Power BI
    Exercise
      Create a lakehouse
      Upload files
      Load file data into tables
      Query lakehouse tables using SQL
      Create a visual query
    Assessment
      Q1 What is a lakehouse
      Q2 Explorer vs SQL endpoint
      Q3 External data no-copy
      Q4 CSV to Delta no-code
      Q5 Spark exploration
      Q6 PBI default mode
```

## 🧭 How to view

- **Obsidian**: open this file, Obsidian will render the Mermaid block natively.
- **Web**: paste into <https://mermaid.live> for an editable SVG.
- **Export**: use the Mermaid CLI (`mmdc`) to render PNG/SVG.

## 🔗 Related

- [[_MOC]] — full module index
- [[Unit-1-Introduction]] · [[Unit-2-Lakehouse-Features]] · [[Unit-3-Ingest-and-Transform]] · [[Unit-4-Query-and-Analyze]] · [[Unit-5-Exercise-Create-Lakehouse]] · [[Unit-6-Module-Assessment]] · [[Unit-7-Summary]]
