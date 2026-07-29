---
title: "Module assessment"
module: "Create an ontology with Fabric IQ"
unit: 10
xp: 200
duration_minutes: 5
source: https://learn.microsoft.com/en-us/training/modules/create-ontology-with-fabric-iq/10-knowledge-check
tags: [dp-600, fabric-iq, ontology, knowledge-check, assessment]
---

# Module assessment

> [!warning] Answer provenance
> The questions and options come from Microsoft Learn. Correct answers are derived from the module content; verify against the live assessment if needed.

## Q1 — Generation advantage

**What is the main advantage of generating an ontology from a Power BI semantic model compared to building manually?**

- [ ] It creates relationship data bindings automatically.
- [x] **It automatically creates entity types, properties, keys, and entity data bindings from existing model structure.**
- [ ] It allows you to use business-friendly names from the start.

📐 **Why:** [[Unit-4-Generate-from-Semantic-Model]] lists these generated artifacts. Relationship bindings can still require configuration, and generated technical names often require refinement.

## Q2 — Binding prerequisite

**What must you configure for an entity type before you can bind it to data sources?**

- [ ] Relationship types connecting it to other entities.
- [x] **An entity type key using one or more string or integer properties.**
- [ ] At least one time-series property.

📐 **Why:** [[Unit-3-Build-Ontology-Manually]] explains that a key is required to identify unique entity instances before binding.

## Q3 — Time series versus static

**How does a time series binding differ from a static binding?**

- [x] **Time series bindings connect to eventhouse streams with a timestamp column, while static bindings connect to lakehouse tables.**
- [ ] Time series bindings can be added before static bindings.
- [ ] Time series bindings do not require a key property.

📐 **Why:** [[Unit-5-Connect-to-Data]] distinguishes eventhouse timestamped observations from static lakehouse attributes and requires the static identity first.

## Q4 — Relationship binding inputs

**What information do you need to configure a relationship data binding?**

- [x] **The source table containing identifying information for both entity types and the columns that match each entity type's key.**
- [ ] Only the source entity type and target entity type.
- [ ] The primary key and foreign key columns from your database schema.

📐 **Why:** [[Unit-6-Configure-Relationships]] requires a table with identifiers for both endpoints and explicit mapping to the ontology entity keys. The physical columns need not be declared database PK/FK constraints.

## Self-score

| Q1 | Q2 | Q3 | Q4 | Score |
|---|---|---|---|---|
| ☐ | ☐ | ☐ | ☐ | /4 |

> [!tip] Distractor pattern
> Watch for absolute claims such as “automatically creates all relationship bindings,” “time series first,” or “does not require a key.” The source emphasizes review, ordering, and explicit key mapping.

## Navigation

← [[Unit-9-Exercise-Semantic-Model]] · → [[Unit-11-Summary]] · ↑ [[_MOC]]
