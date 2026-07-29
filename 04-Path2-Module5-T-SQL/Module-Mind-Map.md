# Module 5 Mind Map — Transform data using T-SQL in Microsoft Fabric

> [!info] Companion file
> This is the **standalone, single-page Mermaid mind map** for Path 2 Module 5. It is duplicated inside [[_MOC]] for inline reading; this file exists so you can open it directly in Obsidian's Mermaid preview, or paste into the [Mermaid Live Editor](https://mermaid.live) for export/zoom.

```mermaid
mindmap
  root((Transform Data<br/>with T-SQL<br/>in Fabric))
    Warehouse vs Lakehouse
      Warehouse
        Full read-write T-SQL
        SELECT INSERT UPDATE DELETE CTAS
        Persist results
      Lakehouse SQL endpoint
        Read-only
        Delta tables queryable
        No DML
      Query tools
        SQL query editor in browser
        IntelliSense and tabs
        SSMS / VS Code MSSQL
        Visual Query Editor
    Transform with Queries
      Filter and project
        WHERE
        SELECT columns
      Calculated columns
        Arithmetic
        CASE tiers
      Null handling
        ISNULL
        COALESCE
      Type conversion
        CAST
        CONVERT
      Joins
        INNER
        GROUP BY
        HAVING
      Window functions
        ROW_NUMBER
        SUM OVER running
        LAG LEAD
        Keep detail rows
      CTEs
        WITH named steps
        Chain transformations
      CTAS
        CREATE TABLE AS SELECT
        One-time materialization
    Views for Reuse
      CREATE VIEW
        Stored SELECT
        Always current
      ALTER VIEW
        Update logic in one place
      Benefits
        Reusability
        Abstraction
        Security
      Patterns
        Transformation view
        Aggregation view
        Denormalized view
      Views vs Tables
        Views live query
        Tables materialized snapshot
        Pick by freshness cost
    Stored Procedures
      CREATE PROCEDURE
        EXEC with params
        usp_ naming convention
      Capabilities
        Write data
        Parameters
        Multi-step
        TRY CATCH
      Loading patterns
        Full refresh
        Incremental load
        MERGE upsert
      Pipeline orchestration
        Data Factory activities
        Schedule nightly refresh
    Dimensional Tables
      Dimension tables
        Surrogate key IDENTITY
        SCD Type 2 columns
        effective end is_current
      Fact tables
        Foreign keys to dims
        Numeric measures
      No FK enforcement
        Naming conventions only
        Loading logic maintains RI
      Load dimensions
        INSERT SELECT initial
        MERGE for SCD1
        Expire insert for SCD2
      Load facts
        Join to dim lookups
        is_current filter
        Effective date for history
      Table clones
        Zero-copy snapshot
        Develop and test
        Rollback safety
    Exercise
      Filter join aggregate
      Create view
      Build stored procedure
      Load fact and dim
    Knowledge Check
      Window vs GROUP BY
      Views reduce duplication
      Full refresh of a period
      is_current filter
      Table clones
```

> [!tip] Navigation
> Return to [[_MOC]] for the full module index, unit breakdown, and knowledge-check answers.