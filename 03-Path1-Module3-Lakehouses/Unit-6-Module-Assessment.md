---
title: "Unit 6 — Module assessment"
module: DP-600
unit: 6 of 7
xp: 200
duration_minutes: 5
source: https://learn.microsoft.com/en-us/training/modules/get-started-lakehouses/6-knowledge-check/
tags:
  - dp-600
  - microsoft-fabric
  - lakehouse
  - assessment
  - knowledge-check
---

# Unit 6 — Module assessment

> [!quote] Source
> Microsoft Learn · Module 3 · Unit 6 · "Module assessment"
> <https://learn.microsoft.com/en-us/training/modules/get-started-lakehouses/6-knowledge-check/>

> [!warning] Note on answer extraction
> Microsoft Learn's **knowledge-check pages publish the questions and options** but **do not display the correct answers** when you take the assessment. The "correct" answers below are **derived from the unit content** (units 2–5) per Microsoft Fabric's documented behavior, then cross-checked against the option wording in the source.

## Q1 — What is a Microsoft Fabric lakehouse?

> What is a Microsoft Fabric lakehouse?
>
> - [ ] A relational database based on the Microsoft SQL Server database engine.
> - [x] **An analytical store that combines the file storage flexibility of a data lake with the SQL-based query capabilities of a data warehouse.**
> - [ ] A hierarchy of folders and files in Azure Data Lake Store Gen2.

📐 **Why:** See [[Unit-1-Introduction]] · [[Unit-2-Lakehouse-Features]]. The lakehouse is **unification** — lake flexibility + warehouse SQL, on OneLake with Delta tables.

## Q2 — Lakehouse explorer vs SQL analytics endpoint

> What is the main difference between the lakehouse explorer and SQL analytics endpoint?
>
> - [ ] The lakehouse explorer provides read-only access, while the SQL analytics endpoint allows data modifications.
> - [x] **Lakehouse explorer enables interaction with tables, files, and folders, while SQL analytics endpoint provides read-only T-SQL querying of Delta tables.**
> - [ ] Both provide identical functionality with different user interfaces.

📐 **Why:** See [[Unit-3-Ingest-and-Transform]] · [[Unit-4-Query-and-Analyze]]. The explorer is for **interacting with data** (upload, manage tables, add reference lakehouses); the SQL endpoint is **read-only T-SQL** over Delta tables — you can create views/functions and apply SQL security, but cannot modify the underlying data.

## Q3 — External ADLS Gen2 data, no copy

> You want to include data in an external Azure Data Lake Store Gen2 location in your lakehouse, without the requirement to copy the data. What should you do?
>
> - [ ] Create a Data pipeline that uses a Copy Data activity to load the external data into a file.
> - [x] **Create a shortcut.**
> - [ ] Create a Dataflow Gen2 that extracts the data and loads it into a table.

📐 **Why:** See [[Unit-3-Ingest-and-Transform]] — **Shortcuts are the zero-copy pattern**. A pipeline / Dataflow Gen2 would **copy** the data. Shortcuts reference external storage and present it as a folder in your lakehouse.

> [!tip] Common distractor to recognize
> "Copy Data activity" is a fine answer for ingestion, but the question explicitly says **without copying** — so the only valid answer is the **shortcut**. Watch for "no-copy" framing in exam questions.

## Q4 — CSV → Delta tables, no code

> You have CSV files in your lakehouse Files area and want to create Delta tables without writing code. What should you use?
>
> - [ ] A notebook with PySpark code
> - [x] **Load to Table**
> - [ ] The SQL analytics endpoint

📐 **Why:** See [[Unit-3-Ingest-and-Transform]] — **Load to Table** is the no-code path that turns a file/folder in Files into a Delta table (Parquet + CSV; append or overwrite). A notebook requires code; the SQL endpoint is read-only (cannot create tables from files).

## Q5 — Interactive Spark exploration

> You want to use Apache Spark to interactively explore data in a file in the lakehouse. What should you do?
>
> - [x] **Create a notebook.**
> - [ ] Switch to the SQL analytics endpoint mode.
> - [ ] Create a Dataflow Gen2.

📐 **Why:** See [[Unit-4-Query-and-Analyze]] — **Notebooks** are the Spark environment for interactive, code-based exploration. The SQL endpoint is **read-only T-SQL** (not Spark). Dataflow Gen2 is a Power-Query transform surface, not an interactive Spark notebook.

## Q6 — Default Power BI connection mode

> What connection mode does Power BI use by default when connecting to a lakehouse semantic model?
>
> - [ ] Import mode, which copies data into Power BI.
> - [ ] DirectQuery mode, which queries the source in real-time.
> - [x] **Direct Lake mode, which reads directly from Delta Lake files without copying data.**

📐 **Why:** See [[Unit-4-Query-and-Analyze]] — **Direct Lake is the default mode** for lakehouse semantic models; it reads **Delta Parquet files directly** without import/copy. Import and DirectQuery are other Power BI modes but **not** the default for lakehouses.

## 📊 Self-score

| Question | Your answer | Correct | Notes |
|----------|-------------|---------|-------|
| 1 | ☐ | ✅ | "combines … lake … warehouse" — memorize this framing |
| 2 | ☐ | ✅ Explorer interactive / SQL read-only T-SQL | Easy to flip — read the option carefully |
| 3 | ☐ | ✅ Shortcut = zero-copy | Watch for "without copying" wording |
| 4 | ☐ | ✅ Load to Table = no-code CSV/Parquet → Delta | Notebook = code; SQL endpoint = read-only |
| 5 | ☐ | ✅ Notebook = Apache Spark interactive | Endpoint is T-SQL, not Spark |
| 6 | ☐ | ✅ **Direct Lake** is the default for lakehouses | Common wrong answer: DirectQuery |

## 🧭 Next

→ [[Unit-7-Summary]]
← [[Unit-5-Exercise-Create-Lakehouse]]
↑ [[_MOC]]
