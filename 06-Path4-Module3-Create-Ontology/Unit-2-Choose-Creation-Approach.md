---
title: "Choose an ontology creation approach"
module: "Create an ontology with Fabric IQ"
unit: 2
xp: 100
duration_minutes: 7
source: https://learn.microsoft.com/en-us/training/modules/create-ontology-with-fabric-iq/2-evaluate-ontology-creation-approaches
tags: [dp-600, fabric-iq, ontology, direct-lake, power-bi]
---

# Choose an ontology creation approach

## The two approaches

| Consideration | Generate from semantic model | Build directly from OneLake |
|---|---|---|
| Starting point | Existing **Direct Lake** Power BI semantic model | Empty ontology plus lakehouse/eventhouse sources |
| Automation | Tables → entities; columns → properties; relationships → relationship types | You define every entity, property, key, and relationship |
| Main benefit | Fast initial structure based on a trusted analytical model | Full vocabulary control from the beginning |
| Follow-up work | Review names, keys, bindings, and generated relationships | Bind every definition and connection manually |
| Best when | Model clearly represents the business domain | No suitable model exists, or reporting structure is a poor ontology |

```mermaid
flowchart TD
  A[Need an ontology] --> B{Suitable Direct Lake semantic model?}
  B -->|Yes| C[Generate initial ontology]
  C --> D[Refine technical names and configuration]
  B -->|No| E[Build directly from OneLake]
  E --> F[Design business vocabulary intentionally]
  D --> G[Complete bound ontology]
  F --> G
```

> [!important] Direct Lake prerequisite
> Ontology generation requires a Power BI semantic model in Direct Lake mode, preserving the connection to OneLake data in place.

> [!tip] Suitability test
> Prefer generation when you can explain every included table as a business concept, relationships reflect real business behavior, and most model content belongs in the desired vocabulary.

> [!warning] Generated does not mean finished
> Technical names such as `hospitals_has_departments` may need conversion into natural business language.

## Navigation

← [[Unit-1-Introduction]] · → [[Unit-3-Build-Ontology-Manually]] · ↑ [[_MOC]]
