---
title: "DP-600 Skills Measured — Study Guide Summary"
exam_code: DP-600
skills_as_of: 2026-07-21
source: https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/dp-600
tags:
  - dp-600
  - skills-measured
  - exam-objectives
---

# DP-600 · Skills Measured (exam objectives)

> [!quote] Source
> Microsoft Learn · Study guide for Exam DP-600 · Skills measured as of July 21, 2026
> <https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/dp-600>

> [!note] Microsoft note
> - Bullets under each skill illustrate how that skill is assessed. Related topics may be covered.
> - Most questions cover GA features. Preview features may appear if commonly used.

---

## 👤 Audience profile

Subject matter expertise in **designing, creating, and managing** analytical assets (semantic models, warehouses, lakehouses).

Responsibilities:

- **Prepare** and **enrich** data for analysis
- **Secure** and **maintain** analytics assets
- **Implement** and **manage** semantic models

Works with: stakeholders (business reqs), architects, analysts, engineers, administrators.

Required query languages: **SQL**, **KQL**, **DAX**.

---

## 📊 Skills at a glance

| Domain | Weight |
|--------|--------|
| Maintain a data analytics solution | 25–30% |
| Prepare data | 45–50% |
| Implement and manage semantic models | 25–30% |

---

## 🔐 Domain 1 · Maintain a data analytics solution (25–30%)

### 1.1 Implement security and governance

- Implement **workspace-level** access controls
- Implement **item-level** access controls
- Implement **row-level**, **column-level**, **object-level**, **file-level** access control
- Apply **sensitivity labels** to items
- **Endorse** items

### 1.2 Maintain the analytics development lifecycle

- Configure **version control** for a workspace
- Create and manage a **Power BI Desktop project** (`.pbip`)
- Create and configure **deployment pipelines**
- Perform **impact analysis** of downstream dependencies from lakehouses, warehouses, dataflows, semantic models
- Deploy and manage semantic models by using the **XMLA endpoint**
- Create and update **reusable assets**: Power BI template (`.pbit`), Power BI data source (`.pbids`), shared semantic models

---

## 🛠️ Domain 2 · Prepare data (45–50%)

### 2.1 Get data

- Create a **data connection**
- Discover data by using **OneLake catalog** and **Real-Time hub**
- Ingest or access data as needed
- **Choose between different data stores**
- Implement **OneLake integration for Eventhouse and semantic models**

### 2.2 Transform data

- Create **views, functions, stored procedures**
- Enrich data by adding **new columns or tables**
- Implement a **star schema** for a lakehouse or warehouse
- **Denormalize** data
- **Aggregate** data
- **Merge or join** data
- Identify and resolve **duplicate data, missing data, null values**
- **Convert column data types**
- **Filter** data

### 2.3 Query and analyze data

- Select, filter, aggregate by using **Visual Query Editor**
- Select, filter, aggregate by using **SQL**
- Select, filter, aggregate by using **KQL**
- Select, filter, aggregate by using **DAX**

---

## 🧮 Domain 3 · Implement and manage semantic models (25–30%)

### 3.1 Design and build semantic models

- Choose a **storage mode**
- Implement a **star schema** for a semantic model
- Implement **relationships** — bridge tables, many-to-many
- Write calculations using **DAX variables and functions**: iterators, table filtering, windowing, information functions
- Implement **calculation groups**, **dynamic format strings**, **field parameters**
- Identify use cases for and configure **large semantic model storage format**
- Design and build **composite models**

### 3.2 Optimize enterprise-scale semantic models

- Implement **performance improvements** in queries and report visuals
- Improve **DAX performance**
- Configure **Direct Lake** (default fallback, refresh behavior)
- Choose between **Direct Lake on OneLake** vs **Direct Lake on SQL analytics endpoint**
- Implement **incremental refresh** for semantic models

---

## 🔗 Crosswalk to learning paths

| Exam topic | Learning Path · Module |
|------------|------------------------|
| Workspace/item access controls | Path 5 · Module 1 (Secure data access) |
| RLS / OLS / CLS / file-level | Path 5 · Module 2 (Secure a warehouse) + Path 3 · Module 4 (Enforce semantic model security) |
| Sensitivity labels / endorse | Path 5 · Module 3 (Govern analytics data) |
| Version control / `.pbip` / deployment pipelines | Path 3 · Module 5 (Manage semantic model lifecycle) |
| OneLake catalog / Real-Time hub / Eventhouse integration | Path 1 · Module 2 (Discover and connect to data in OneLake) |
| Data store choice | Path 2 · Module 1 (Choose data stores) |
| Star schema in lakehouse/warehouse | Path 2 · Module 2 (Design dimensional models) |
| Dataflows Gen2 / Notebooks / T-SQL transform | Path 2 · Modules 3, 4, 5 |
| Visual Query Editor / SQL / KQL / DAX | Path 1 + Path 2 + Path 3 |
| DAX calculations (variables, iterators, windowing) | Path 3 · Module 1 (Create DAX calculations) |
| Calculation groups, dynamic format strings, field parameters | Path 3 · Module 2 (Design semantic models for scale) |
| Large semantic model storage, composite models | Path 3 · Module 2 |
| Direct Lake, incremental refresh, performance | Path 3 · Module 3 (Optimize semantic model performance) |
| AI-ready semantic layer / Fabric IQ | Path 4 · Modules 1, 2, 3 |

---

## 🔗 Related

- [[_MOC]] — DP-600 master index
- [[DP-600-Mind-Map]]
- [[Change-Log]]
- [[Skill-Domains/Domain-1-Maintain-Solution]]
- [[Skill-Domains/Domain-2-Prepare-Data]]
- [[Skill-Domains/Domain-3-Semantic-Models]]