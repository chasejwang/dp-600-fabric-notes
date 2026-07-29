---
title: "Module 1 — Mind Map (Mermaid)"
module: DP-600
type: mind-map
source: _MOC.md
tags:
  - dp-600
  - mind-map
  - mermaid
---

# Module 1 — Fabric End-to-End Analytics · Mind Map

```mermaid
mindmap
  root((Microsoft Fabric<br/>Module 1))
    What is Fabric
      SaaS unified platform
      OneLake foundation
      Open Delta-Parquet format
      Replaces PBI + Synapse + ADF
    OneLake
      Built on ADLS Gen2
      Single logical lake
      Shortcuts to ADLS, S3, Dataverse
      Default Delta-Parquet for tables
      All engines read/write same data
    Workspaces
      Logical containers
      4 roles: admin, contributor, member, viewer
      Lineage view
      Git integration
      Spark workload settings
    Data Teams
      Data engineers
        Pipelines
        Lakehouses
        Delta-Parquet
      Analytics engineers
        Curate data assets
        Semantic models in PBI
      Data analysts
        Direct Lake mode
        Dataflows
        Power BI reports
      Data scientists
        Notebooks
        Python and Spark
        Azure ML integration
      Citizen developers
        OneLake catalog
        PBI templates
        Copilot NL questions
    Admin and Enable
      Fabric admin role
      Power Platform admin
      Global admin implicit
      Admin portal > Tenant settings
      Security group scoped enable
      Free trial available
    OneLake Catalog
      Discover shared data
      Filter by workspace and domain
      Sensitivity labels
      Item metadata
    Workloads
      Data Engineering
      Data Factory
      Data Warehouse
      Real-Time Intelligence
      Industry Solutions
      Data Science
      Databases
      IQ preview
      Power BI
    AI Capabilities
      Fabric IQ ontology
      Foundry IQ enterprise knowledge
      Work IQ collaboration signals
      Fabric data agents
      Copilot across workloads
        Code completion
        SQL from NL
        KQL from NL
        Data transformation guidance
        Report generation
    Module Assessment
      Q1 collaboration
      Q2 Delta-Parquet
      Q3 Data Factory
      Q4 OneLake + AI
```

## 🧭 How to view

- **Obsidian**: open this file, Obsidian will render the Mermaid block natively.
- **Web**: paste into <https://mermaid.live> for an editable SVG.
- **Export**: use the Mermaid CLI (`mmdc`) to render PNG/SVG.

## 🔗 Related

- [[_MOC]] — full module index
- [[Unit-1-Introduction]] · [[Unit-2-Explore-Analytics-Fabric]] · [[Unit-3-Data-Teams]] · [[Unit-4-Enable-and-Use-Fabric]] · [[Unit-5-Module-Assessment]] · [[Unit-6-Summary]]