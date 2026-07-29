---
title: "Unit 6 — Knowledge check"
module: DP-600
unit: 6 of 7
xp: 200
duration_minutes: 3
source: https://learn.microsoft.com/en-us/training/modules/enforce-semantic-model-security/6-knowledge-check
tags:
  - dp-600
  - rls
  - ols
  - power-bi
  - assessment
  - knowledge-check
  - dynamic-security
  - object-level-security
  - security-groups
---

# Unit 6 — Knowledge check

> [!warning] Answer provenance
> Microsoft Learn intentionally does **not** publish the correct answers for knowledge-check questions. The answers below are **derived from the unit content** and the wording of each question. Treat them as best-effort study notes — verify against the live module if you fail the check.

## 📋 Questions

### Question 1

> A data modeler needs to ensure that sales managers see only the sales data for their assigned region. The modeler wants a scalable solution that doesn't require model changes when managers change regions. Which approach should the data modeler use?

- Create a static RLS rule for each region and assign managers to the appropriate role.
- **Create a dynamic RLS rule using `USERPRINCIPALNAME()` with a security table that maps managers to regions.**
- Use object-level security to hide regions that each manager shouldn't access.

### Question 2

> An organization's semantic model contains an Employee table with a Salary column. General managers need access to the Employee table for contact information, but only HR staff should see salary values. Which security feature should the data modeler configure?

- Row-level security to filter salary rows.
- **Object-level security to restrict the Salary column.**
- Remove the Salary column from the semantic model and create a separate model for HR.

### Question 3

> A data modeler configured RLS on a semantic model and published it to the Power BI service. A Viewer reports that they can see all data instead of just their region's data. What is the most likely cause?

- The RLS filter expression contains a syntax error.
- **The user hasn't been assigned to an RLS role in the Power BI service.**
- The semantic model uses DirectQuery instead of import mode.

### Question 4

> A data modeler needs to test whether RLS correctly filters data before publishing the semantic model to the Power BI service. How should the data modeler verify the security configuration?

- **Use the View as feature on the Modeling tab in Power BI Desktop to preview data as a specific role.**
- Publish the model and ask each user to verify their data access.
- Review the DAX filter expressions for syntax errors in the formula bar.

### Question 5

> A data modeler is deciding how to assign users to RLS roles for a semantic model used by 200 sales representatives across five regions. What is the recommended approach for managing role membership?

- Add each sales representative individually to the appropriate regional role.
- **Map Microsoft Entra security groups to roles, with one security group per region.**
- Create a Microsoft 365 group for each region and assign the groups to roles.

## ✅ Answer key (derived)

| # | Correct answer | Why the others are wrong | Source unit |
|---|----------------|--------------------------|-------------|
| 1 | **Dynamic RLS with `USERPRINCIPALNAME()` + security table** | Static RLS for each region requires new roles/republish for every team change — not scalable. OLS hides columns/tables, not rows — it can't filter a manager's data down to a single region. | [[Unit-2-Row-Level-Security]] |
| 2 | **Object-level security on the `Salary` column** | RLS filters *rows*, not columns — every row would still expose the Salary value. Removing the column from the model hurts *all* users; OLS hides it for non-payroll roles only while keeping the model intact. | [[Unit-3-Object-Level-Security]] |
| 3 | **User not assigned to an RLS role in the service** | A syntax error would surface in Desktop validation (View as). Import vs DirectQuery is unrelated to RLS bypass. The classic cause: a Viewer with no RLS role membership sees the *unfiltered* model. | [[Unit-4-Test-Manage-Roles]] |
| 4 | **View as on the Modeling tab in Power BI Desktop** | Asking real users is slow and noisy. Reviewing syntax only catches parse errors, not filter logic. View as previews the report from a role's perspective before publishing. | [[Unit-4-Test-Manage-Roles]] |
| 5 | **Microsoft Entra security groups, one per region** | Adding 200 individuals is unmanageable. M365 groups are **not supported** for Power BI role membership — only Entra security groups, distribution groups, mail-enabled groups, and service principals. | [[Unit-4-Test-Manage-Roles]] |

## 🧠 Why these answers (linking back to the module)

```mermaid
mindmap
  root((Knowledge Check<br/>Module M4 Path 3))
    Q1 Dynamic vs static
      USERPRINCIPALNAME()
      Security table mapping
      Data-driven not model-driven
      Scales with team changes
    Q2 OLS for columns
      Hides column + metadata
      Salary stays for HR only
      RLS would only filter rows
    Q3 RLS bypass cause
      Viewer without role = unfiltered
      Syntax error caught in Desktop
      Import mode irrelevant
    Q4 View as for testing
      Modeling tab in Desktop
      Test dynamic rules with email
      Faster than real-user testing
    Q5 Entra security groups
      One group per region
      Bulk membership updates
      M365 groups NOT supported
```

## 🎯 Re-study pointers

> [!tip] If you missed a question, re-read:
> - Q1 → "Dynamic security with `USERPRINCIPALNAME()`" + "Security table pattern" in [[Unit-2-Row-Level-Security]]
> - Q2 → "Understand when to use OLS" + "Hide specific columns" in [[Unit-3-Object-Level-Security]]
> - Q3 → "Avoid common mistakes — forgetting to assign users to roles" in [[Unit-4-Test-Manage-Roles]]
> - Q4 → "Test roles in Power BI Desktop — View as feature" in [[Unit-4-Test-Manage-Roles]]
> - Q5 → "Use security groups for scalable management" in [[Unit-4-Test-Manage-Roles]]

## 🔑 Key terms (flashcards)

- **Dynamic RLS** — single role that filters by user identity via `USERPRINCIPALNAME()` + security table; data-driven.
- **Object-level security (OLS)** — column/table-level `None` permission scoped per role; hides both data and metadata.
- **View as** — Power BI Desktop Modeling-tab feature for previewing a report as a specific role.
- **Entra security group** — recommended identity object for bulk RLS role membership; M365 groups are not supported.
- **Unassigned Viewer** — a workspace Viewer with no RLS role membership sees **all** rows (no filter applied).

## 🧭 Next

→ [Unit 7 — Summary](./Unit-7-Summary.md)
← [Unit 5 — Exercise](./Unit-5-Exercise.md)
↑ [_MOC](./_MOC.md)