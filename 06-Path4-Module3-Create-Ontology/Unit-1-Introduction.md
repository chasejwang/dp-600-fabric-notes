---
title: "Introduction"
module: "Create an ontology with Fabric IQ"
unit: 1
xp: 100
duration_minutes: 3
source: https://learn.microsoft.com/en-us/training/modules/create-ontology-with-fabric-iq/1-introduction
tags: [dp-600, fabric-iq, ontology, introduction]
---

# Introduction

> [!quote] Scenario
> Lamna Healthcare stores hospitals, departments, rooms, and patients in lakehouse tables, while ICU equipment sends continuous vital signs to an eventhouse.

## Core idea

An ontology creates a shared business vocabulary over heterogeneous data. It defines:

- **Entity types**: Hospital, Department, Room, Patient.
- **Properties**: names, identifiers, locations, measurements.
- **Relationship types**: Department *located in* Hospital; Patient *assigned to* Room.
- **Bindings**: mappings from ontology definitions to physical tables, streams, and columns.

```mermaid
flowchart LR
  L[Lakehouse tables] --> O[Fabric IQ ontology]
  E[Eventhouse streams] --> O
  O --> A[AI agents]
  O --> G[Graph exploration]
  O --> N[Natural-language queries]
```

> [!success] Outcome
> Users explore connected business concepts instead of manually writing SQL joins across lakehouse and eventhouse data.

> [!important] An ontology is not another data copy
> It is a semantic graph layer whose definitions and bindings make source data queryable through consistent business concepts.

## Navigation

← [[_MOC]] · → [[Unit-2-Choose-Creation-Approach]] · ↑ [[_MOC]]
