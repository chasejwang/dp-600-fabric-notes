---
title: "Module mind map — Choose data stores in Microsoft Fabric"
module: "DP-600 · Path 2 · Module 1"
source: https://learn.microsoft.com/en-us/training/modules/choose-data-store-fabric/
tags:
  - dp-600
  - microsoft-fabric
  - data-stores
  - mind-map
  - mermaid
---

# Module mind map — Choose data stores in Microsoft Fabric

> [!info] How to use
> Open this file in Obsidian's Mermaid preview, or copy the `mermaid` block below into [Mermaid Live Editor](https://mermaid.live) for an exportable image. This is the **single-page mental model** for the entire module — print it, pin it, draw it from memory.

```mermaid
mindmap
  root((Choose data stores<br/>Fabric Module 1))
    Three analytical stores
      Lakehouse
        Spark Python Scala SQL R
        Delta Lake on OneLake
        Tables area managed
        Files area raw
        SQL analytics endpoint read-only
        Direct Lake Power BI
        Medallion bronze silver gold
        Feature engineering and ML
        Semantic Link SemPy
      Warehouse
        T-SQL full DML DDL
        INSERT UPDATE DELETE MERGE
        Multi-table ACID
        Schema-on-write enforced
        Star schema dimensional
        Slowly changing dimensions
        Cross-database three-part naming
        Direct Lake Power BI
        Copilot and data agents foundation
      Eventhouse
        KQL Kusto Query Language
        T-SQL subset supported
        Streaming ingestion
        Time-based partitioning and indexing
        Append-optimized
        Real-Time Dashboards
        Always-On option
        KQL ML series_decompose_anomalies
    Shared foundation
      OneLake
      Delta and Parquet open formats
      Integration across workloads
      Metadata quality for AI readiness
    Integration patterns
      OneLake shortcuts
        Reference without duplicating
      Cross-database queries
        Three-part naming warehouse.schema.table
      Eventstreams
        Route to eventhouse and lakehouse
      Direct Lake
        Power BI no import refresh
    Decision factors
      Data format
        Structured semi unstructured
      Query language preference
        T-SQL Spark KQL
      Write pattern
        Transactional batch streaming
      Team skills
        SQL-first Spark-first KQL
      Workload type
        Batch BI real-time exploratory ML
    AI readiness by store
      Lakehouse
        ML training data and feature stores
        Vector embeddings for RAG
      Warehouse
        Governed dimensional models
        Copilot and data agents foundation
      Eventhouse
        Real-time anomaly detection
        Streaming predictions
    Limits by store
      Lakehouse
        Single-table ACID only
        No multi-table transactions
        SQL analytics endpoint read-only
        No streaming
      Warehouse
        No Spark environment
        Structured only no Files area
        No real-time streaming
      Eventhouse
        Append-only no UPDATE DELETE
        No Spark
        No dimensional modeling
    Contoso case study
      Engineering lakehouse
        Spark Python PySpark
        Mixed formats 5 TB daily
        Curated Delta tables
      BI warehouse
        Star schema SCDs
        Cross-database queries
        Direct Lake Power BI
      Real-time eventhouse
        Eventstream from POS
        50K events per second
        Real-Time Dashboards KQL
      Data science lakehouse
        Workload isolation
        Shortcuts to lakehouse and warehouse
        SemPy to Power BI
    Process
      Unit 1 introduction
      Unit 2 describe options
      Unit 3 lakehouse
      Unit 4 warehouse
      Unit 5 eventhouse
      Unit 6 case study
      Unit 7 assessment
      Unit 8 summary
```