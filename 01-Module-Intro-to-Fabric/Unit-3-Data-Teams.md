---
title: "Unit 3 — Explore data teams and Microsoft Fabric"
module: DP-600
unit: 3 of 6
xp: 100
duration_minutes: 4
source: https://learn.microsoft.com/en-us/training/modules/introduction-end-analytics-use-microsoft-fabric/3-data-team/
tags:
  - dp-600
  - microsoft-fabric
  - data-teams
  - collaboration
  - roles
---

# Unit 3 — Explore data teams and Microsoft Fabric

## 🎯 Why this matters

Fabric's *organizational* value is breaking down role silos. The unit contrasts the **traditional handoff-heavy analytics process** with the **Fabric collaborative model** where each role works on the *same* data in OneLake.

## 🚧 Traditional roles and challenges

> [!warning] Pain points before Fabric

| Role | What they did | Pain |
|------|---------------|------|
| **Data engineer** | Process & curate data for analysts | Heavy coordination, delays, misinterpretation |
| **Data analyst** | Downstream transformations → Power BI reports | Time-consuming, lacks context, disconnected from raw data |
| **Data scientist** | Integrate ML with existing systems | Complex plumbing, hard to ship data-driven insights |

## 🤝 Evolution of collaborative workflows

> [!success] Fabric's promise
> Fabric unifies tools into a **SaaS platform**. Different roles **collaborate effectively without duplicating efforts**.

### Role-by-role

#### 🛠️ Data engineers
- Ingest, transform, load data **directly into OneLake** using **Pipelines** (automated, schedulable).
- Store data in **lakehouses** using the **Delta-Parquet** format — efficient storage + versioning.
- Use **Notebooks** for advanced scripting on complex transformations.

#### 🔗 Analytics engineers
- **Bridge** data engineering and analysis.
- Curate data assets in **lakehouses**, ensure **data quality**, enable **self-service analytics**.
- Create **semantic models in Power BI** to organize and present data effectively.

#### 📊 Data analysts
- Transform data **upstream** using **dataflows**.
- Connect **directly** to OneLake with **Direct Lake mode** → less downstream transformation.
- Build interactive reports more efficiently with **Power BI**.

#### 🔬 Data scientists
- Use **integrated notebooks** (Python + Spark) to build/test ML models.
- Store/access data in **lakehouses**, integrate with **Azure Machine Learning** to operationalize & deploy.
- Their predictions can serve as **grounding data for Copilot and AI agents**.

#### 🧑‍🤝‍🧑 Low-to-no-code users / citizen developers
- Discover curated datasets via the **OneLake catalog**.
- Use **Power BI templates** to spin up reports & dashboards quickly.
- Use **dataflows** for simple ETL — no data engineer required.
- **Ask questions of their data in natural language using Copilot**.

> [!important] Foundation for AI
> Every role contributes to the organization's ability to use AI effectively.
>
> - **Data engineers** who maintain clean, well-governed data in OneLake build the **foundation** that Copilot and AI agents rely on.
> - **Analytics engineers** who create consistent **semantic models** give AI tools the **business context** needed to generate accurate, meaningful answers.

## 🧠 Visual — role map

```mermaid
flowchart LR
    subgraph Fabric[Microsoft Fabric · OneLake]
      DE[Data Engineer<br/>Pipelines · Lakehouse · Delta-Parquet]
      AE[Analytics Engineer<br/>Curate · Semantic Models]
      DA[Data Analyst<br/>Direct Lake · Dataflows · PBI]
      DS[Data Scientist<br/>Notebooks · Spark · Azure ML]
      CD[Citizen Developer<br/>Catalog · Templates · Copilot]
    end
    DE -->|curated lakehouse| AE
    AE -->|semantic model| DA
    DA -->|insights| CD
    DE -->|raw + clean data| DS
    DS -->|predictions → Copilot/agents| Fabric
    AE -->|business context| Agents[Copilot · Data Agents · IQ workloads]
    DE -->|governed data| Agents
```

## 🧠 Visual — before vs after

```mermaid
flowchart TB
    subgraph Before[Traditional stack]
      direction LR
      E1[Data Engineer] -->|handoff| A1[Data Analyst]
      A1 -->|more handoff| DS1[Data Scientist]
      DS1 -->|complex plumbing| PBI1[Power BI Report]
    end
    subgraph After[Fabric · shared OneLake]
      direction LR
      E2[Data Engineer]:::role
      AE[Analytics Engineer]:::role
      A2[Data Analyst]:::role
      DS2[Data Scientist]:::role
      CD[Citizen Dev]:::role
      L[(OneLake + lakehouses + semantic models)]:::core
      E2 --- L
      AE --- L
      A2 --- L
      DS2 --- L
      CD --- L
    end
    classDef role fill:#e0f2fe,stroke:#0369a1,color:#0c4a6e
    classDef core fill:#fef9c3,stroke:#ca8a04,color:#713f12
```

## 🔑 Key terms (flashcards)

- **Direct Lake mode** — Power BI connects directly to OneLake without import-mode duplication.
- **Semantic model** — A business-friendly abstraction of tables/relationships that Power BI reports consume.
- **Self-service analytics** — Business users build their own reports on curated, governed data.
- **Grounding data** — The high-quality data that an LLM/agent uses as its source of truth.

## 🧭 Next

→ [[Unit-4-Enable-and-Use-Fabric]]
← [[Unit-2-Explore-Analytics-Fabric]]
↑ [[_MOC]]