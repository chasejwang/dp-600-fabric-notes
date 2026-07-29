---
title: Manage semantic models with the XMLA endpoint
module: Manage the semantic model development lifecycle
unit: 4
xp: 100
duration_minutes: 9
source: https://learn.microsoft.com/en-us/training/modules/manage-semantic-model-lifecycle/4-manage-models-xmla
tags: [dp-600, xmla, sempy, tabular-editor, dax-studio, alm-toolkit, validation]
---

# Manage semantic models with the XMLA endpoint

Version control tracks changes; the XMLA endpoint **verifies** them by giving programmatic access to model structure and data.

## What the XMLA endpoint is

The XMLA (XML for Analysis) protocol is the API between clients and the Power BI/Fabric Analysis Services engine. Every Premium/Fabric workspace exposes one. All traffic is fully encrypted.

- **Read-only (default):** query data and metadata.
- **Read-write (admin-enabled):** scripted deploys, programmatic refresh, and model updates.

Connection string:

```
powerbi://api.powerbi.com/v1.0/[tenant name]/workspace name]
```

## SemPy in Fabric notebooks

SemPy (`sempy.fabric`) is the Python library for notebook-based validation. It ships with Fabric Runtime 1.2+.

### Inspect metadata

```python
import sempy.fabric as fabric

fabric.list_tables("Sales Model", workspace="Sales Workspace")
fabric.list_columns("Sales Model", workspace="Sales Workspace")
fabric.list_measures("Sales Model", workspace="Sales Workspace")
```

### Validate relationships

Orphaned foreign keys cause blank rows and bad aggregations.

```python
relationships = fabric.list_relationships("Sales Model", workspace="Sales Workspace")
tables = {t: fabric.read_table("Sales Model", t, workspace="Sales Workspace")
          for t in fabric.list_tables("Sales Model", workspace="Sales Workspace")["Name"]}
violations = fabric.list_relationship_violations(tables)
```

> [!info] `list_relationship_violations()`
> Compares foreign-key values against primary-key values for every relationship and returns rows that don't match.

### Test measure calculations

```python
fabric.evaluate_measure(
    "Sales Model",
    measure="Total Revenue",
    groupby_columns=["Date[Year]", "Product[Category]"],
    workspace="Sales Workspace",
)

fabric.evaluate_dax(
    "Sales Model",
    'EVALUATE SUMMARIZECOLUMNS(Date[Year], "Revenue", [Total Revenue])',
    workspace="Sales Workspace",
)
```

Assert known values in Python to flag discrepancies automatically.

### Check data quality

```python
df = fabric.read_table("Sales Model", "Customers", workspace="Sales Workspace")
df[["CustomerKey", "CustomerName"]].isnull().sum()
df["CustomerKey"].duplicated().sum()
```

> [!tip] Repeatable validation
> Saving these checks in a notebook turns it into a pre-deployment validation suite.

## External tools

Same XMLA endpoint, different UX:

- **DAX Studio** — interactive DAX query testing.
- **Tabular Editor** — visual model tree + Best Practice Analyzer (BPA).
- **ALM Toolkit** — schema diff between environments.

Fabric also includes a built-in **Best Practice Analyzer** in the semantic model menu. It generates a notebook that runs 60+ rules across Performance, DAX Expressions, Error Prevention, Maintenance, and Formatting — no external install needed.

## Choose the right approach

| Task | SemPy (notebooks) | External tool |
|---|---|---|
| Inspect metadata | `list_tables/list_measures/list_columns` | Tabular Editor |
| Validate relationships | `list_relationship_violations` | Tabular Editor |
| Test measures | `evaluate_measure`, `evaluate_dax` | DAX Studio |
| Data quality | `read_table` + Python asserts | — |
| Best-practice audit | Built-in BPA | Tabular Editor BPA |
| Schema compare | — | ALM Toolkit |

> [!warning] Endpoint must be enabled
> If the XMLA endpoint is disabled, neither SemPy nor external tools will connect.

The **Validate** stage is complete. Next: [[Unit-5-Deploy-Stages]].
