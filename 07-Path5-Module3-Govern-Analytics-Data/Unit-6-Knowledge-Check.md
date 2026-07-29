---
title: "Unit 6 — Knowledge check"
module: DP-600
unit: 6 of 7
xp: 200
duration_minutes: 3
source: https://learn.microsoft.com/en-us/training/modules/fabric-govern-analytics-data/6-knowledge-check
tags: [dp-600, microsoft-fabric, knowledge-check, assessment, governance]
---

# Unit 6 — Knowledge check

> [!warning] Answer provenance
> The static source presents questions and options but does not mark correct choices. Answers below are **derived directly from the concept units**; verify against the live assessment if needed.

## Q1 — Protect the entire lineage

> A lakehouse containing customer personal data must remain protected through downstream semantic models and reports. Which capability propagates the label automatically?

- [ ] Default labeling
- [ ] Mandatory labeling
- [x] **Downstream inheritance**

📐 **Why:** Downstream inheritance propagates an upstream label to dependent items. See [[Unit-2-Classify-and-Protect]].

## Q2 — Authoritative reference data

> Which endorsement level best designates a semantic model as the authoritative single source of truth for product reference data?

- [ ] Promoted
- [ ] Certified
- [x] **Master data**

📐 **Why:** Master data identifies core organizational reference data and its single source of truth. See [[Unit-3-Endorse-and-Document]].

## Q3 — Governance recommendations

> Which OneLake catalog tab recommends actions for missing descriptions and sensitivity labels?

- [ ] Explore
- [x] **Govern**
- [ ] Secure

📐 **Why:** Govern reports governance posture and improvement recommendations. Explore discovers assets; Secure manages roles.

## Q4 — Endorsement and data agents

> A data agent can access a certified semantic model and an unpromoted experimental dataset. How does endorsement affect its behavior?

- [ ] It ignores endorsement and queries both equally.
- [x] **It prioritizes the certified semantic model as more authoritative.**
- [ ] It queries only Master data items.

📐 **Why:** Endorsement is a trust signal; agents prioritize certified sources over unendorsed alternatives. See [[Unit-4-Govern-Data-for-AI]].

## Q5 — Detailed descriptions

> How does a detailed description of scope and refresh frequency affect AI responses compared with a generic description?

- [ ] It has no effect because agents use only sensitivity labels.
- [x] **It supplies context that supports specific, accurate responses about scope and refresh frequency.**
- [ ] It affects catalog users only, not agents.

📐 **Why:** AI agents use descriptions and metadata for semantic context.

## 📊 Self-score

| Question | 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|---|
| Correct? | ☐ | ☐ | ☐ | ☐ | ☐ |

> [!tip] Re-study map
> Q1 → [[Unit-2-Classify-and-Protect]] · Q2–Q3 → [[Unit-3-Endorse-and-Document]] · Q4–Q5 → [[Unit-4-Govern-Data-for-AI]]

## 🧭 Next

→ [[Unit-7-Summary]]  
← [[Unit-5-Exercise]]  
↑ [[_MOC]]
