---
title: Exercise — Manage semantic models through their lifecycle
module: Manage the semantic model development lifecycle
unit: 7
xp: 100
duration_minutes: 45
source: https://learn.microsoft.com/en-us/training/modules/manage-semantic-model-lifecycle/7-exercise
tags: [dp-600, exercise, lab, sempy, deployment-pipeline]
---

# Exercise: Manage semantic models through their lifecycle

> [!info] Lab length
> Approximately 45 minutes. Requires a Fabric-enabled workspace (Fabric trial license is available).

## What the lab does

This exercise practices the **Validate → Deploy** stages of the lifecycle on a real Fabric workspace:

1. **Validate** — open a Fabric notebook and run SemPy to inspect a published semantic model:
   - list tables, columns, and measures,
   - read tables into DataFrames and run `list_relationship_violations()` to catch orphaned foreign keys,
   - evaluate measures and DAX expressions to confirm calculations.
2. **Deploy** — create a deployment pipeline that links the development workspace to a production workspace and promote the validated semantic model through its stages.
3. **Verify** — confirm the deployed model appears in the production workspace with the correct configuration.

## Skills practiced

- Notebook-driven validation with `sempy.fabric`.
- Relationship integrity checks.
- Deployment pipeline creation and selective item promotion.

> [!tip] Before you start
> Have a Fabric workspace ready and a sample semantic model to validate. Skim [[Unit-4-XMLA]] for the SemPy reference and [[Unit-5-Deploy-Stages]] for the pipeline setup.

Next: [[Unit-8-Knowledge-Check]].
