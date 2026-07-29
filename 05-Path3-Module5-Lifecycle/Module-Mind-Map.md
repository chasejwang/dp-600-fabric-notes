---
title: Module Mind Map — Manage the semantic model development lifecycle
module: DP-600 — Manage the semantic model development lifecycle
unit: Mind map
xp: 1000
duration_minutes: 86
source: https://learn.microsoft.com/en-us/training/modules/manage-semantic-model-lifecycle/
tags: [dp-600, mind-map, lifecycle, fabric, power-bi]
---

# Module Mind Map

```mermaid
mindmap
  root((Semantic Model Lifecycle))
    Develop
      Reusable assets
        Shared semantic model
        Power BI template (.pbit)
        Data source file (.pbids)
      Version control
        Power BI Desktop project (.pbip)
        TMDL semantic model
        PBIR report JSON
        Fabric Git integration
        Commit / Update / Branches / Conflicts
    Validate
      XMLA endpoint
        Read-only vs read-write
        Encrypted protocol
      SemPy notebooks
        list_tables / list_columns / list_measures
        list_relationship_violations
        evaluate_measure / evaluate_dax
        read_table + asserts
      External tools
        DAX Studio
        Tabular Editor + BPA
        ALM Toolkit
        Built-in Fabric BPA (60+ rules)
    Deploy
      Deployment pipelines
        Development → Test → Production
        2 to 10 stages
      Deployment rules
        Data source rules
        Parameter rules
      Compare and deploy
        Selective item promotion
      Automation
        Fabric REST API
        CI/CD patterns
    Monitor
      Scheduled refresh
        Data gateway for on-prem
        Failure notifications
      Pipeline refresh
        Data Factory orchestration
        Conditional logic
      Monitoring Hub
        Refresh history
        Failure investigation
      Lineage view
        Impact analysis before schema changes
```

## Stage-to-unit map

| Stage | Unit | Output |
|---|---|---|
| Develop | [[Unit-2-Reusable-Assets]], [[Unit-3-Power-BI-Projects]] | Reusable assets under version control |
| Validate | [[Unit-4-XMLA]] | Programmatic checks via XMLA / SemPy |
| Deploy | [[Unit-5-Deploy-Stages]] | Promoted content with stage rules |
| Monitor | [[Unit-6-Maintain-Monitor]] | Reliable, refreshed, observable models |

See also: [[_MOC]] · [[Unit-9-Summary]]
