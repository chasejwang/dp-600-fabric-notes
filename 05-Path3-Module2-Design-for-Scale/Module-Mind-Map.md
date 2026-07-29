# Module 2 Mind Map — Design semantic models for scale in Microsoft Fabric

> [!info] Companion file
> This is the **standalone, single-page Mermaid mind map** for Module 2. It is duplicated inside [[_MOC]] for inline reading; this file exists so you can open it directly in Obsidian's Mermaid preview, or paste into the [Mermaid Live Editor](https://mermaid.live) for export/zoom.

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

> [!tip] Navigation
> Return to [[_MOC]] for the full module index, unit breakdown, and knowledge-check answers.
