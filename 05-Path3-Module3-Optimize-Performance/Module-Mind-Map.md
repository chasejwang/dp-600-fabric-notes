# Module 3 Mind Map — Optimize semantic model performance

> [!info] Companion file
> This is the **standalone, single-page Mermaid mind map** for Path 3 Module 3. It is duplicated inside [[_MOC]] for inline reading; this file exists so you can open it directly in Obsidian's Mermaid preview, or paste into the [Mermaid Live Editor](https://mermaid.live) for export/zoom.

```mermaid
mindmap
  root((Optimize Semantic<br/>Model Performance))
    Performance Analyzer
      Where to open
        Desktop Optimize ribbon
        Power BI service View menu
      Record workflow
        Start recording
        Interact with report
        Clear visual cache first
      Timing categories
        DAX query ms
        Visual display ms
        Direct query ms
        Other queue overhead
      Export DAX query
        Run in DAX query view
        Copy query
      DAX Studio
        Server Timings FE SE
        Query Plan
        Model metrics
    Optimize DAX
      Variables VAR RETURN
        Store expression once
        Reuse in RETURN
        Debug intermediates
      FILTER vs KEEPFILTERS
        FILTER iterates rows
        Boolean column predicate cheaper
        KEEPFILTERS preserves context
      Iterators SUMX AVERAGEX
        Row-by-row cost
        Scales with table size
        Prefer non-iterator when possible
      Avoid patterns
        COUNTROWS FILTER on large tables
        Nested CALCULATE
        Mixed aggregation grains
      Move upstream
        Power Query computed columns
        SQL source calculation
        Better VertiPaq compression
      AI impact
        Copilot and IQ agents use DAX
        Tighter timeouts than humans
    Reduce Cardinality
      VertiPaq compression
        Column-by-column
        Fewer uniques compress better
      Identify offenders
        Unused GUIDs surrogate keys
        High precision timestamps
        Free-text columns
        Unique IDs not needed
      Reduction strategies
        Remove unused columns
        Reduce time precision
        Bucket continuous values
        Remove unnecessary rows
        Optimize data types
      Trade-offs
        Granularity vs performance
        Composite for detail
    Implement Aggregations
      When to use
        Large fact tables
        Common summary patterns
        DirectQuery or composite
      User-defined
        Create aggregation table
        Manage aggregations mapping
        Hide aggregation table
        Import aggregation DirectQuery detail
      Automatic aggregations
        Query log analysis
        Premium or Fabric capacity
        DirectQuery storage mode
      Monitor effectiveness
        Refresh history memory used
        Azure Log Analytics hit rate
      Direct Lake note
        Start without aggregations
        Add when measurement shows need
    Troubleshoot
      Systematic workflow
        Symptom diagnosis fix verify
        Identify bottleneck category
        Isolate root cause
      Best Practice Analyzer
        60+ rules performance DAX
        Fabric notebook based BPA
        Memory Analyzer companion
        Tabular Editor fallback
      Complex visuals
        Too many measures
        Too many data points
        Too many visuals per page
      Relationship design
        Ambiguous paths
        Bidirectional filtering
        High-cardinality join keys
      Filter context
        REMOVEFILTERS ALL on large tables
        Many-to-many bridge tables
      DirectQuery
        Query folding failures
        Slow source queries
        Round-trip latency
      DAX Studio diagnostics
        Server Timings
        Query Plan
      Troubleshooting checklist
        Six ordered steps
        Measure before and after
    Exercise
      Capture Performance analyzer
      Identify expensive DAX
      Apply VAR optimization
      Examine cardinality
      Verify improvement
    Knowledge Check
      Diagnose slow visual
      VAR for repeated CALCULATE
      Truncate datetime
      Aggregations for DirectQuery
      Too many visuals
```

> [!tip] Navigation
> Return to [[_MOC]] for the full module index, unit breakdown, and knowledge-check answers.