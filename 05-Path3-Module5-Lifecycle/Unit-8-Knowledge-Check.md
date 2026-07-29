---
title: Module assessment — knowledge check
module: Manage the semantic model development lifecycle
unit: 8
xp: 200
duration_minutes: 3
source: https://learn.microsoft.com/en-us/training/modules/manage-semantic-model-lifecycle/8-knowledge-check
tags: [dp-600, knowledge-check, assessment, qa]
---

# Module assessment

> [!warning] Pass to earn credit
> Answer all questions correctly to earn the pass designation. You must be signed in.

## Question 1

A team needs every regional report to use the same visuals, measures, and layout but connect to a different data source. Which Power BI asset type best fits?

- A. Power BI template (`.pbit`)
- B. Power BI data source file (`.pbids`)
- C. Shared semantic model with DirectQuery

> [!success] Answer
> **A. Power BI template (`.pbit`)**
>
> A template preserves the report structure (pages, visuals, model, queries, parameters) without data. When a regional user opens it, Power BI Desktop prompts for parameter values and credentials and rebuilds a fresh report from the saved structure — same layout, region-specific data source.

## Question 2

A developer commits changes to a semantic model via Git integration, and the workspace shows a conflict. What does a conflict indicate?

- A. The same item changed in both the workspace and the repository since the last sync.
- B. The workspace contains items that don't exist in the repository.
- C. The Git provider rejected the connection because of insufficient permissions.

> [!success] Answer
> **A. The same item changed in both the workspace and the repository since the last sync.**
>
> Git reports a conflict when both sides have moved since the last sync. Resolve by choosing one version or merging manually.

## Question 3

Before deploying, an analyst wants to verify that all relationships are valid and no orphaned foreign keys exist. Which SemPy function identifies relationship violations?

- A. `list_relationship_violations()`
- B. `list_relationships()`
- C. `evaluate_measure()`

> [!success] Answer
> **A. `list_relationship_violations()`**
>
> It takes a dictionary of table DataFrames and uses the model's relationship metadata to find foreign-key values that have no matching primary key. `list_relationships()` only lists relationship definitions; `evaluate_measure()` runs DAX.

## Question 4

A pipeline has dev, test, and production stages. Development connects to a test database; production must connect to the live database. How should the team handle this difference?

- A. Configure a data source deployment rule that changes the connection when deploying to the production stage.
- B. Manually update the data source connection in the production workspace after each deployment.
- C. Create separate semantic models for each stage with different hardcoded connection strings.

> [!success] Answer
> **A. Configure a data source deployment rule that changes the connection when deploying to the production stage.**
>
> Deployment rules substitute the right data source at deploy time. Manual edits are error-prone, and hardcoded models duplicate the model and break the "single source of truth" goal.

## Question 5

A semantic model depends on upstream data in a lakehouse. The model refresh is currently scheduled one hour after the lakehouse load, but the lakehouse load sometimes takes longer. Which approach solves this?

- A. Use a Data Factory pipeline with a semantic model refresh activity that runs after the lakehouse load succeeds.
- B. Schedule the semantic model refresh two hours after the lakehouse load instead of one.
- C. Enable real-time refresh on the semantic model so it always has current data.

> [!success] Answer
> **A. Use a Data Factory pipeline with a semantic model refresh activity that runs after the lakehouse load succeeds.**
>
> A pipeline enforces sequential ordering and can add conditional logic (skip the refresh and alert if the lakehouse load fails). A longer delay is still a guess; real-time refresh doesn't apply to lakehouse-backed models and adds cost.

Next: [[Unit-9-Summary]].
