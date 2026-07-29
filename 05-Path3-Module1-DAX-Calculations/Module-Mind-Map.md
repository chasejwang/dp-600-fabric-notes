---
title: "Module — Create DAX calculations in semantic models · Mind Map"
module: DP-600
type: mind-map
source: _MOC.md
tags:
  - dp-600
  - mind-map
  - mermaid
  - dax
  - power-bi
  - semantic-model
---

# Module — Create DAX calculations in semantic models · Mind Map

```mermaid
mindmap
  root((DAX Calculations<br/>Module — Path 3 / M1))
    Three Calculation Types
      Calculated tables
        DAX formula returns table
        Duplicate for role-playing dims
        CALENDAR / CALENDARAUTO
        Mark as date table
        Increase model size
      Calculated columns
        Row context: one value per row
        Formula returns scalar
        Use RELATED / RELATEDTABLE
        Use LOOKUPVALUE if no relationship
        Stored values increase memory
      Measures
        Filter context: dynamic
        Never stored in model
        Calculated at query time
        Simple = one aggregate
        Compound = references other measures
    Implicit vs Explicit Measures
      Implicit
        Auto from column
        Sigma symbol in Data pane
        Default Sum or Average
        Report author can change
        Limits: simple aggregations only
      Explicit
        DAX formula
        Full control
        Supports complex logic
        Formatting in Measure tools ribbon
        Best practice default
    Aggregator vs Iterator
      Aggregators
        SUM COUNT MIN MAX AVG
        Act on single column
        Internal SUMX under the hood
      Iterators (X suffix)
        SUMX COUNTX MINX MAXX AVERAGEX
        Iterate row by row
        Multi-column expressions
        Reference related tables
        Higher-grain summarization
    Filter Context vs Row Context
      Row context
        Current row evaluation
        Default for calc columns
        Iterator X-functions
      Filter context
        Set by report visuals / CALCULATE
        Default for measures
        Outer container for row context
      HASONEVALUE / ALL / VALUES
        Modify filter context
    Ranking with RANKX
      Default skips ranks for ties
      DENSE removes gaps
      ALL removes filters
      HASONEVALUE hides total row
    Power BI Special Features
      Quick measures
        Generate DAX from UI
        DIVIDE Profit / Revenue
        Great for learning DAX
      Compound measures
        Build on other measures
        Optimize by replacing calc cols
        Test cascading changes
    Best Practices
      Prefer measures over calculated columns
      Prefer Power Query over calc columns when possible
      Set formatting immediately
      Hide columns you don't want authors to use
      Watch performance on large iterator expressions
    Knowledge Check
      Q1 Calculated tables truth
      Q2 Calculated columns truth
      Q3 Measures truth
```

## 🧭 How to view

- **Obsidian**: open this file, Obsidian will render the Mermaid block natively.
- **Web**: paste into <https://mermaid.live> for an editable SVG.
- **Export**: use the Mermaid CLI (`mmdc`) to render PNG/SVG.

## 🔗 Related

- [[_MOC]] — full module index
- [[Unit-1-Introduction]] · [[Unit-2-Calculated-Tables]] · [[Unit-3-Calculated-Columns]] · [[Unit-4-Implicit-Measures]] · [[Unit-5-Explicit-Measures]] · [[Unit-6-Iterator-Functions]] · [[Unit-7-Exercise]] · [[Unit-8-Knowledge-Check]] · [[Unit-9-Summary]]