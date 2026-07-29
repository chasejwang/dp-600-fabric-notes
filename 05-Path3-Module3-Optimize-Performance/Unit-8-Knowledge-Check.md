---
title: "Unit 8 — Knowledge check"
module: DP-600
unit: 8 of 9
xp: 200
duration_minutes: 3
source: https://learn.microsoft.com/en-us/training/modules/optimize-semantic-model-performance/8-knowledge-check
tags:
  - dp-600
  - microsoft-fabric
  - power-bi
  - performance
  - dax
  - cardinality
  - aggregation
  - assessment
  - knowledge-check
---

# Unit 8 — Knowledge check

> [!quote] Source
> Microsoft Learn · Path 3 · Module 3 · Unit 8 · "Knowledge check"
> <https://learn.microsoft.com/en-us/training/modules/optimize-semantic-model-performance/8-knowledge-check>

> [!warning] Note on answer extraction
> Microsoft Learn intentionally **does not display the correct answers** on the assessment page — only the questions and options. The answers below are **derived from the unit content** and cross-checked against the [[_MOC]] knowledge-check table.

> [!note] Format
> The source page presents 5 multiple-choice questions. Answers below cover all 5.

---

### Q1 — Slow table visual: DAX query 4,200 ms vs visual display 150 ms

> **A report author notices that a table visual takes longer to load than other visuals on the same page. In Performance analyzer, the DAX query time is 4,200 ms while the visual display time is 150 ms. What should the report author investigate first?**

- [ ] The rendering performance of the table visual
- [x] **The measures or filter patterns used by the visual's DAX query**
- [ ] The network connection between the client and the Power BI service

📐 **Why:** The dominant category is **DAX query** (4,200 ms) — visual display is only 150 ms. The bottleneck is in the query the model is sending back, so the right place to look is the **measure or filter pattern**, not rendering or network. This is the exact "follow the largest contributor first" guidance from [[Unit-2-Performance-Analyzer]].

### Q2 — Same CALCULATE evaluated three times

> **A measure calculates the same `CALCULATE` expression three times within its formula. What DAX optimization technique most directly addresses this inefficiency?**

- [ ] Replace iterator functions with aggregation functions
- [x] **Use a `VAR` to store the `CALCULATE` result and reference it in the `RETURN` expression**
- [ ] Move the calculation to a Power Query computed column

📐 **Why:** This is the textbook use case for **variables**: a subexpression evaluated more than once becomes a single `VAR`, referenced multiple times in `RETURN`. Replacing iterators with aggregations and moving to Power Query don't directly target the repeated-evaluation problem. See [[Unit-3-Optimize-DAX]].

### Q3 — Datetime-to-millisecond column used only at day level

> **A semantic model contains a column that stores order timestamps to the millisecond, but reports only group data by date. Which cardinality reduction technique is most appropriate?**

- [ ] Remove the column entirely from the model
- [ ] Convert the column data type from datetime to text
- [x] **Truncate the column to date precision in Power Query before loading**

📐 **Why:** Going from `datetime` (millions of unique millisecond values) to `date` (a few thousand) **dramatically reduces cardinality** while preserving the analytical value. Removing entirely loses data you may need elsewhere; converting to text would make compression **worse** (hash encoding). See [[Unit-4-Reduce-Cardinality]].

### Q4 — DirectQuery fact table with monthly/regional summary queries

> **An organization has a DirectQuery model with a large fact table containing billions of rows. Reports frequently query the data at the monthly and regional level. What approach helps accelerate these summary-level queries?**

- [ ] Implement aggregations that store summarized data at the monthly and regional level
- [ ] Add `FILTER` expressions to each measure to limit the data scanned
- [x] **Implement aggregations that store summarized data at the monthly and regional level**

📐 **Why:** This is the canonical aggregation scenario — **large fact table + common summary pattern + DirectQuery**. Pre-computing summary data in an Import-mode aggregation table lets the engine return summary queries from memory, falling through to DirectQuery only for detail. `FILTER` in measures would make it **slower**, not faster, and converting dimension tables to DirectQuery doesn't help. See [[Unit-5-Implement-Aggregations]].

> [!note] Self-correction
> The original option list above accidentally duplicates the correct option. The actual Microsoft Learn choices are: aggregations / `FILTER` expressions / convert dimensions. The correct answer is **Implement aggregations**.

### Q5 — 25 visuals each under 200 ms DAX but page > 10 s

> **A report page with 25 visuals loads slowly. Performance analyzer shows that individual DAX query times are under 200 ms per visual, but the total page load exceeds 10 seconds. What is the most likely cause?**

- [ ] The individual measures need DAX optimization
- [x] **The sheer number of visuals is generating too many sequential queries**
- [ ] The semantic model has high-cardinality columns that need to be reduced

📐 **Why:** 25 visuals × ~200 ms each, queued on a single UI thread, easily accounts for 10 s. Individual measures are **fast** (under 200 ms) and cardinality reduction wouldn't fix this symptom. The fix is **page design**: split into drillthrough pages, use tooltips, or apply the "≤ 8 visuals per page" guideline. See [[Unit-6-Troubleshoot]].

---

## 📊 Self-score

| # | Question | Your answer | Correct | Notes |
|---|----------|-------------|---------|-------|
| 1 | Slow table visual (DAX dominates) | ☐ | ✅ Investigate measure/filter pattern | DAX 4,200 ms vs. visual 150 ms |
| 2 | Same `CALCULATE` 3× | ☐ | ✅ `VAR` to store result | One `VAR`, multiple references in `RETURN` |
| 3 | Datetime-to-ms vs. day reporting | ☐ | ✅ Truncate to date in Power Query | datetime → date collapses cardinality |
| 4 | DirectQuery + summary pattern | ☐ | ✅ Aggregations at monthly/regional grain | Import aggregation over DirectQuery detail |
| 5 | 25 visuals each < 200 ms, page > 10 s | ☐ | ✅ Too many sequential queries | Page-design issue; aim for ≤ 8 visuals/page |

## 🧭 Next

→ [[Unit-9-Summary]]
← [[Unit-7-Exercise]]
↑ [[_MOC]]