---
title: "Unit 1 — Introduction"
module: DP-600
unit: 1 of 7
xp: 100
duration_minutes: 2
source: https://learn.microsoft.com/en-us/training/modules/fabric-govern-analytics-data/1-introduction
tags: [dp-600, microsoft-fabric, governance, data-estate]
---

# Unit 1 — Introduction

## 🎯 Why this matters

As Fabric adoption grows, lakehouses, warehouses, semantic models, and reports multiply. Without governance, consumers cannot reliably distinguish authoritative assets from experiments, and sensitive data can reach unauthorized users or AI agents.

> [!quote] Scenario
> An uncertified dataset produces incorrect executive projections while an AI agent surfaces confidential salary data because the source has no sensitivity label.

## 🔑 Governance outcomes

- **Classification** identifies sensitivity and enables protection.
- **Endorsement** signals whether an asset is trustworthy and reusable.
- **Documentation** makes meaning, scope, and lineage discoverable.
- **OneLake catalog** centralizes discovery and governance posture.
- **AI governance** ensures agents use permitted, authoritative, understandable data.

```mermaid
flowchart LR
  U[Ungoverned estate] --> R[Risk]
  R --> R1[Wrong source selected]
  R --> R2[Sensitive data exposed]
  R --> R3[Duplicate assets]
  R --> R4[Poor AI answers]
  U --> G[Governed estate]
  G --> C[Classified]
  G --> E[Endorsed]
  G --> D[Documented]
  G --> A[AI-ready]
```

> [!success] Target state
> Humans and AI agents can find, evaluate, and consume trusted data while respecting protection boundaries.

## 🧭 Next

→ [[Unit-2-Classify-and-Protect]]  
↑ [[_MOC]]
