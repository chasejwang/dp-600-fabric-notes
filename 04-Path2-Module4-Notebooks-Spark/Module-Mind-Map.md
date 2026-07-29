# Module 4 Mind Map — Transform data using notebooks in Microsoft Fabric

> [!info] Companion file
> This is the **standalone, single-page Mermaid mind map** for Path 2 Module 4. It is duplicated inside [[_MOC]] for inline reading; this file exists so you can open it directly in Obsidian's Mermaid preview, or paste into the [Mermaid Live Editor](https://mermaid.live) for export/zoom.

```mermaid
mindmap
  root((Transform Data<br/>with Fabric<br/>Notebooks))
    Notebook Concepts
      Web-based Spark surface
        Cells run independently
        Persistent Spark session
        All cells share variables
      Multi-language
        PySpark
        Spark SQL
        Scala
        R
      Magic commands
        %%sql
        %%pyspark
        %%scala
        Switch per cell
      Lakehouse attachment
        Default lakehouse pins metastore
        Query tables by name
        Explorer panel access
      Data stores reached
        Lakehouse
        Warehouse 3-part
        KQL database
        External JDBC / ADLS / REST
      Notebooks vs Dataflows Gen2
        Complex logic
        Spark distributed scale
        Version control friendly
      Dev patterns
        Interactive development
        Parameterized notebooks
        Pipeline integration
    Shape and Clean
      Read source
        spark.table or SELECT
      Deduplicate
        dropDuplicates
        DISTINCT
        ROW_NUMBER by business key
      Handle nulls
        fillna / COALESCE
        dropna / WHERE NOT NULL
      Filter rows
        filter / WHERE
      Select and rename
        select + alias
      Calculated columns
        withColumn
        quantity x unit_price
        Date parts year month
      Conditional columns
        when / CASE
        value tiers
      Type conversion
        cast / CAST
        decimal date int
    Combine and Aggregate
      Joins
        inner
        left
        right
        full outer
        cross
      GROUP BY
        count sum avg
        HAVING for filter
      Window functions
        row_number
        rank
        lag lead
        running totals
        Keep detail rows
      CTEs
        WITH named steps
        Chain DataFrames in PySpark
      Pivot
        rows to columns
        Specify values explicitly
    Write Delta Tables
      Save
        saveAsTable
        CREATE OR REPLACE TABLE AS
      Write modes
        overwrite full refresh
        append incremental
        MERGE row-level updates
      Partitioning
        Tables over 1 TB
        1 GB per partition
        year month region
        Avoid high cardinality
      File sizing
        Optimize Write on by default
        OPTIMIZE compact small files
        VACUUM reclaim storage
        Target 128 MB to 1 GB
      Delta features
        ACID transactions
        Schema enforcement
        V-Order read-heavy opt
    Exercise
      Clean raw sales
      Join customers products
      Aggregate and window
      Write Delta result
    Knowledge Check
      Magic commands
      Null handling
      Write mode overwrite
      Window vs GROUP BY
      OPTIMIZE for small files
```

> [!tip] Navigation
> Return to [[_MOC]] for the full module index, unit breakdown, and knowledge-check answers.
