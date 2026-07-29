# Module 2 Mind Map — Design dimensional models for analytics in Microsoft Fabric

> [!info] Companion file
> This is the **standalone, single-page Mermaid mind map** for Module 2. It is duplicated inside [[_MOC]] for inline reading; this file exists so you can open it directly in Obsidian's Mermaid preview, or paste into the [Mermaid Live Editor](https://mermaid.live) for export/zoom.

```mermaid
mindmap
  root((Dimensional<br/>Modeling in<br/>Fabric))
    Schema Types
      Star schema
        Central fact + denormalized dims
        Fewer joins
        Semantic-model ready
        Recommended default
      Snowflake schema
        Normalized dim hierarchies
        More joins
        Use when very large dims
      Conformed dims
        Shared across fact tables
    Fact Tables
      Column types
        Dimension keys
        Measures
        Degenerate dimensions
      Grain
        Most important decision
        Aligns dims + measures
      Fact table types
        Transaction
        Periodic snapshot
        Accumulating snapshot
        Factless facts
        Aggregate facts
      Measure types
        Additive
        Semi-additive
        Non-additive
      Naming
        f_ or Fact_ prefix
    Dimension Tables
      Keys
        Surrogate key
        Natural key
      Attributes
        Denormalized
      Hierarchies
        Balanced
        Unbalanced
        Ragged
      Patterns
        Conformed
        Role-playing
        Junk dimension
      Naming
        d_ or Dim_ prefix
    Slowly Changing Dims
      Type 0
        Retain original
      Type 1
        Overwrite
      Type 2
        Add new row
        Full history
        Start/end date + flag
      Type 3
        Add new column
        Previous value
      Type 6
        Hybrid
        Type 1+2+3
      Tradeoffs
        Storage
        Query complexity
        ETL complexity
        Business needs
    Foundation for AI
      Copilot + Power BI
        NL questions map to dims + facts
      Fabric IQ
        Ontology entity types → dims
        Properties → attributes
```

> [!tip] Navigation
> Return to [[_MOC]] for the full module index, unit breakdown, and knowledge-check answers.
