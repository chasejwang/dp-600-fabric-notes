# Module 4 Mind Map — Get started with data warehouses in Microsoft Fabric

> [!info] Companion file
> This is the **standalone, single-page Mermaid mind map** for Module 4. It is duplicated inside [[_MOC]] for inline reading; this file exists so you can open it directly in Obsidian's Mermaid preview, or paste into the [Mermaid Live Editor](https://mermaid.live) for export/zoom.

```mermaid
mindmap
  root((Fabric<br/>Data Warehouse<br/>Module 4))
    Dimensional Modeling
      Fact tables
        Numerical measures
        Foreign keys to dims
      Dimension tables
        Descriptive context
        Surrogate key
        Alternate key
      Star schema
        Denormalized dims
        Few joins
      Snowflake schema
        Normalized dims
        Many joins
    Fabric Warehouse
      Full T-SQL
        DDL + DML + MERGE
        ACID compliant
      Built on OneLake
        Delta-Parquet files
        Zero-copy clones
      Fully managed
        Auto-scale compute
        Independent storage
      Cross-database queries
        Three-part naming
      SQL analytics endpoint
        Read-only on lakehouse
      Tooling
        SSMS
        Azure Data Studio
        Copilot in editor
    Ingest Data
      COPY INTO
        CSV / Parquet from blob
      OPENROWSET
        Ad hoc file queries
      Pipelines / Dataflows
        Orchestrated ETL
      Cross-database
        No-copy joins
    Create and Load
      CREATE TABLE
        INT for keys
        NVARCHAR for text
        DECIMAL for money
      Staging tables
        Land raw
        Transform
        Load final
      Table clones
        CREATE TABLE as CLONE OF
        Zero-copy metadata
    Query and Transform
      SQL query editor
        IntelliSense
        Copilot assist
      Visual query editor
        No-code canvas
        Power Query style
      Views
        Saved reusable query
        Encapsulate joins
      Stored procedures
        T-SQL logic
        Repeatable transforms
    Model Data
      Prepare for consumption
        Hide staging
        Rename columns
        Add descriptions
      Relationships
        Cardinality
        Cross-filter direction
      Measures
        DAX calculations
        Single source of truth
      Semantic model
        Direct Lake
        No data copy
    Security
      Workspace roles
      Item permissions
        Read
        ReadData
        ReadAll
      Granular SQL security
        Object-level
        Row-level RLS
        Column-level CLS
        Dynamic data masking
    Monitoring
      Query insights
        queryinsights.exec_requests_history
        queryinsights.long_running_queries
        queryinsights.exec_sessions_history
      Dynamic management views
        sys.dm_exec_requests
        Real-time
```

> [!tip] Navigation
> Return to [[_MOC]] for the full module index, unit breakdown, and knowledge-check answers.