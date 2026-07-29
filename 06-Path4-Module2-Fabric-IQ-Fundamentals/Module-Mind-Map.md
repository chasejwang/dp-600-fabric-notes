---
title: "Module — Understand Microsoft Fabric IQ fundamentals · Mind Map"
module: DP-600
type: mind-map
source: _MOC.md
tags:
  - dp-600
  - mind-map
  - mermaid
  - microsoft-fabric
  - fabric-iq
  - ontology
  - data-agent
  - graph
  - semantic-model
---

# Module — Understand Microsoft Fabric IQ fundamentals · Mind Map

```mermaid
mindmap
  root((Fabric IQ Fundamentals<br/>Path 4 / M2))
    What is Fabric IQ
      Workload in Fabric
      Creates ontology items
      Sits with Data Eng DW RTI Power BI
      Preview status
      Admin tenant settings
    Ontology concepts
      Entity types things
      Properties facts
      Relationships connections
      Identifiers
      Named directional
    Build
      Entity types
      Properties
      Relationship types
      Configuration canvas
      In business language
    Bind
      Lakehouse tables
      Eventhouse streams
      No data movement
      Entity-specific keys
    Query
      Graph visual traversal
      Query Builder
      Data agents
      Federated routing
    Two creation paths
      Generate from semantic model
      Build from OneLake data
      Same destination
    Fabric IQ components
      Ontology items
        Define vocabulary
        Bind to data
      Data agents
        NL2SQL NL2DAX NL2KQL
        Up to 5 sources
        Azure OpenAI
        Instructions + examples
        Read only secure
        Copilot Studio integration
      Graph in Microsoft Fabric
        Labelled property graph
        Auto from ontology
        GQL queries
        OneLake no ETL
        Scale out
      Semantic models
        Generate Ontology
        Faster starting point
        Refine rename verify
    Ontology vs traditional
      Concept driven
        Business concepts first
        Reusable definitions
        One canonical source
        Binds later
      Use case driven
        Reports first
        Star schema
        Abbreviated columns
        Often drifts
    Entity types vs tables
      Conceptual definition
      Independent of storage
      Combine schema and storage
      Identifier properties
    Properties
      Standardised names
      Bound to messy columns
      Data types
    Relationships
      Named directional
      Department has Room
      Traverse with GQL
    Federation
      GQL to Graph
      KQL to Eventhouse
      SQL to Lakehouse
      Single business query
```

## 🧭 How to view

- **Obsidian**: open this file, Obsidian will render the Mermaid block natively.
- **Web**: paste into <https://mermaid.live> for an editable SVG.
- **Export**: use the Mermaid CLI (`mmdc`) to render PNG/SVG.

## 🔗 Related

- [[_MOC]] — full module index
- [[Unit-1-Introduction]] · [[Unit-2-Get-Started-Fabric-IQ]] · [[Unit-3-Explore-Fabric-IQ-Components]] · [[Unit-4-Understand-Ontology-Modeling-Paradigm]] · [[Unit-5-Module-Assessment]] · [[Unit-6-Summary]]
