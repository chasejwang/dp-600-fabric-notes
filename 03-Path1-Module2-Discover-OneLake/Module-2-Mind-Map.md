---
title: "Module 2 — Discover and connect to data in OneLake · Mind Map"
module: DP-600
type: mind-map
source: _MOC.md
tags:
  - dp-600
  - mind-map
  - mermaid
  - onelake
---

# Module 2 — Discover OneLake · Mind Map

```mermaid
mindmap
  root((OneLake Discovery<br/>Module 2))
    OneLake
      Tenant-wide single lake
      Built-in to Fabric
      No setup needed
      Single copy of data
      Open Delta-Parquet default
    Data in OneLake
      Tables in lakehouses, warehouses, eventhouses
      Files (Parquet, CSV, JSON, etc.)
      Shortcuts to external sources
      Semantic models for Power BI
    Ingestion Methods
      Mirroring
        SQL Server
        Azure SQL
        Cosmos DB
        Snowflake
      Pipelines via Data Factory
      Dataflows via Power Query
      Streaming via eventstreams
      Direct upload
    OneLake Catalog
      Search by name or tag
      Filter by workspace and domain
      Metadata: owner, refresh, sensitivity, endorsement
      Endorsement
        Promoted
        Certified
        Master data
      Permission-aware visibility
      Governed via Microsoft Purview
    Shortcuts
      Reference without copying
      Cross-workspace collaboration
      Medallion architecture layers
      Avoid when need stable snapshot
      Avoid when compliance requires copy
    SQL Analytics Endpoint
      Read-only T-SQL per lakehouse
      Preview schema and data
      Copilot writes T-SQL
    Semantic Models
      Details page
        Overview
        Tables
        Lineage
        Monitor
      Explore this data
      Auto-create report
      Blank report
      Template report
      Paginated report
      Analyze in Excel
    Real-Time Hub
      Catalog for streaming data
      Eventstreams
        Kafka
        Event Hubs
        IoT Hub
        CDC
      KQL tables in eventhouses
      Streaming data view
      Add data experience
      Bridge batch and real-time
    AI in OneLake
      Copilot uses the catalog
      Fabric IQ data agents
      Better answers when data is well-cataloged
    Knowledge Check
      Q1 OneLake tenant-wide benefit
      Q2 Read-only T-SQL shortcut
      Q3 Streaming catalog location
      Q4 Purpose of shortcuts
      Q5 Catalog supports AI
```

## 🧭 How to view

- **Obsidian**: open this file, Obsidian will render the Mermaid block natively.
- **Web**: paste into <https://mermaid.live> for an editable SVG.
- **Export**: use the Mermaid CLI (`mmdc`) to render PNG/SVG.

## 🔗 Related

- [[_MOC]] — full module index
- [[Unit-1-Introduction]] · [[Unit-2-Understand-OneLake]] · [[Unit-3-Browse-Connect-OneLake]] · [[Unit-4-Discover-Streaming-Data]] · [[Unit-5-Exercise]] · [[Unit-6-Knowledge-Check]] · [[Unit-7-Summary]]
