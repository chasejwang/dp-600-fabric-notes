---
title: Create reusable Power BI assets
module: Manage the semantic model development lifecycle
unit: 2
xp: 100
duration_minutes: 5
source: https://learn.microsoft.com/en-us/training/modules/manage-semantic-model-lifecycle/2-reusable-assets
tags: [dp-600, power-bi, shared-semantic-model, pbit, pbids, reusable-assets]
---

# Create reusable Power BI assets

Reusable assets provide shared foundations and reduce duplicated connection settings, metrics, and report layouts.

## Shared semantic models

A shared semantic model centralizes business metrics, relationships, and calculations. Reports connect to it rather than embedding separate model logic.

> [!success] Core-plus-specialized pattern
> Put authoritative measures such as revenue, cost, and margin in the core model. Let specialized reports add their own visuals and filters. A change to the core definition is then reflected by every connected report.

In Power BI Desktop, choose **Power BI semantic models** as the data source and select the published model. Queries run against the shared model at run time.

> [!important] Single source of truth
> Endorsed shared models are preferred for consistent human and AI/Fabric IQ consumption. Duplicated, unmanaged models create ambiguity.

## Power BI templates (`.pbit`)

A `.pbit` stores report pages, visuals, model definitions, queries, and parameters **without data**. Opening it prompts for parameter values and credentials, then creates a fresh report.

Create one with **File → Export → Power BI template**. Templates are compact and useful for standardized regional, monthly, or financial reports. Parameters can be text (server/database), Boolean, or date values.

## Data source files (`.pbids`)

A `.pbids` preserves only connection information. Opening it launches Power BI Desktop with the source preconfigured; the user authenticates.

| Asset | Best fit | Benefit |
|---|---|---|
| Shared semantic model | Many reports need common logic | Centralized business definitions |
| `.pbit` template | Same structure across teams | Consistent layout and query patterns |
| `.pbids` file | Standardize connection setup | Faster, repeatable connectivity |

> [!tip] Combine assets
> A template connected to a shared semantic model gives teams a consistent report structure backed by centralized logic.

These assets establish the **Develop** stage. Next: [[Unit-3-Power-BI-Projects]].
