---
title: "Module — Secure a Microsoft Fabric data warehouse"
module: DP-600
unit_index: 2 of 4
status: complete
xp_total: 900
duration_minutes: 74
source: https://learn.microsoft.com/en-us/training/modules/secure-data-warehouse-in-microsoft-fabric/
tags:
  - dp-600
  - microsoft-fabric
  - data-warehouse
  - security
  - ddm
  - dynamic-data-masking
  - rls
  - row-level-security
  - cls
  - column-level-security
  - sql-granular-permissions
  - t-sql
  - grant
  - deny
  - revoke
  - unmask
  - predicate
  - security-policy
---

# Module — Secure a Microsoft Fabric data warehouse

> [!info] Module map
> This is the **warehouse data-protection** module of Path 5 (Secure data access) in the Fabric Analytics Engineer track. Workspace roles decide **who** can touch a warehouse; **item permissions** share a warehouse without exposing the workspace; **data protection** decides **what each user actually sees** once they're in. This module focuses on that innermost layer: **dynamic data masking (DDM)**, **row-level security (RLS)**, **column-level security (CLS)**, and **SQL granular permissions** (`GRANT` / `DENY` / `REVOKE`). All four are applied through T-SQL against the warehouse — no application changes required.

## 🎯 Learning objectives (from Microsoft Learn)

By the end of this module you should be able to:

1. **Describe security layers** in a Fabric warehouse — workspace roles, item permissions, data protection, audit logs, and encryption.
2. **Apply dynamic data masking (DDM)** to obscure column values in query results without changing the underlying data, using `default()`, `email()`, `partial()`, and `random()` mask functions.
3. **Manage masking permissions** with `UNMASK` and `ALTER ANY MASK`.
4. **Implement row-level security (RLS)** using an inline table-valued **filter predicate** and a `CREATE SECURITY POLICY` binding.
5. **Implement column-level security (CLS)** by combining `GRANT SELECT` on the table with `DENY SELECT` on a specific column for selected roles.
6. **Configure SQL granular permissions** with `GRANT` / `DENY` / `REVOKE` on tables, views, functions, and stored procedures.
7. **Apply the principle of least privilege** to warehouse object access.

## 🧠 Module mind map

> [!tip] How to use
> The mind map below is duplicated as a standalone Mermaid file (`Module-Mind-Map.md`) you can open in Obsidian's Mermaid preview or the [Mermaid Live Editor](https://mermaid.live). It is the **single-page view** of the entire module.

```mermaid
mindmap
  root((Secure a Microsoft Fabric<br/>data warehouse<br/>Path 5 / Module 2))
    Security layers
      Workspace roles
        Admin / Member / Contributor / Viewer
      Item permissions
        Share warehouse downstream
      Data protection
        DDM / RLS / CLS / SQL granular
        T-SQL driven
      Audit logs
        Purview + PowerShell
        Compliance reporting
      Encryption at rest
        Microsoft-managed by default
        CMK via Key Vault
    Dynamic Data Masking
      Query-time obfuscation
      No storage change
      No schema change
      Mask functions
        default()
        email()
        partial(prefix, padding, suffix)
        random(low, high)
      Apply
        ALTER TABLE ALTER COLUMN ADD MASKED WITH
        ALTER TABLE ALTER COLUMN DROP MASKED
      Permissions
        CONTROL = unmasked
        GRANT UNMASK per user
        ALTER ANY MASK for engineers
      Limitation
        Inference attacks
        Divide-by-zero signals
        One layer, not a wall
    Row-Level Security
      Filter predicate
        Inline table-valued function
        WITH SCHEMABINDING
        true / false per row
      Security policy
        Binds predicate to table
        STATE = ON / OFF
        Affects SELECT UPDATE DELETE
        INSERT NOT filtered
      Applies to ALL users
        Admins too
        Always add admin exception
      Side-channel attacks
        Divide-by-zero probes
        Combine with CLS + DDM
        Restrict ALTER ANY SECURITY POLICY
    Column-Level Security
      GRANT + DENY per column
      Roles
        Doctor / Nurse / Receptionist / Patient
      Errors look like missing column
      Power BI Direct Lake
        Falls back to Direct Query
        Security still enforced
        Performance trade-off
    SQL Granular Permissions
      GRANT DENY REVOKE
      DENY always wins
      Table / view
        SELECT INSERT UPDATE DELETE
      Function / proc
        EXECUTE ALTER CONTROL
      Least privilege
        EXECUTE on procs only
        DENY on underlying tables
        Revoke temp access
```

## 📑 Unit breakdown

| # | Unit | XP | Minutes | Focus |
|---|------|----|---------|-------|
| 1 | [Introduction](./Unit-1-Introduction.md) | 100 | 2 | Why warehouse needs layered security; five layers (workspace roles, item permissions, data protection, audit logs, encryption) |
| 2 | [Explore dynamic data masking](./Unit-2-Dynamic-Data-Masking.md) | 100 | 5 | DDM concept; `default()` / `email()` / `partial()` / `random()` masks; `ALTER TABLE ... ADD MASKED WITH`; `UNMASK` and `ALTER ANY MASK`; inference attack warning |
| 3 | [Implement row-level security](./Unit-3-Row-Level-Security.md) | 100 | 5 | Filter predicate (inline TVF with `SCHEMABINDING`); `CREATE SECURITY POLICY`; predicate applies to admins too; side-channel attacks; combine with CLS + DDM |
| 4 | [Implement column-level security](./Unit-4-Column-Level-Security.md) | 100 | 3 | Healthcare scenario with `Patients.MedicalHistory`; `CREATE ROLE` + `GRANT SELECT` + `DENY SELECT`; Power BI Direct Lake → Direct Query fallback |
| 5 | [Configure SQL granular permissions](./Unit-5-SQL-Granular-Permissions.md) | 100 | 4 | `GRANT` / `DENY` / `REVOKE`; `DENY` always wins; DML perms (`SELECT/INSERT/UPDATE/DELETE`); routine perms (`EXECUTE/ALTER/CONTROL`); least-privilege patterns |
| 6 | [Exercise — Secure a warehouse in Microsoft Fabric](./Unit-6-Exercise.md) | 100 | 45 | Hands-on lab: apply DDM, RLS, CLS, and SQL granular permissions; optional second Entra user for verification |
| 7 | [Knowledge check](./Unit-7-Knowledge-Check.md) | 200 | 8 | 3 knowledge-check questions |
| 8 | [Summary](./Unit-8-Summary.md) | 100 | 2 | Recap + further reading links |

**Total: 900 XP · 74 minutes (1 hr 14 min)**

## 🔗 Knowledge-check answers (unit 7)

> [!warning] Answer provenance
> Microsoft Learn intentionally does not publish the correct answers for knowledge-check questions. The answers below are **derived from the unit content** for this module and the wording of each question. Treat them as best-effort study notes — verify against the live module if you fail the check.

| Q | Question | Correct answer |
|---|----------|----------------|
| 1 | Primary advantage of Dynamic Data Masking (DDM)? | **It limits data exposure by obscuring sensitive information in real time.** Masking is query-time only — storage and schema are unchanged. |
| 2 | Purpose of a security predicate function in RLS? | **It determines whether a row is accessible to a user based on certain conditions.** The inline TVF returns `true`/`false` per row; rows where it's `false` are invisible for SELECT/UPDATE/DELETE. |
| 3 | A user has both `GRANT` and `DENY` on the same permission — what happens? | **The `DENY` always supersedes the `GRANT`, and the user is denied access.** Conflicts resolve in favor of `DENY` regardless of role membership. |

## 🧭 Downstream links

- [[Unit-1-Introduction]] · [[Unit-2-Dynamic-Data-Masking]] · [[Unit-3-Row-Level-Security]] · [[Unit-4-Column-Level-Security]] · [[Unit-5-SQL-Granular-Permissions]] · [[Unit-6-Exercise]] · [[Unit-7-Knowledge-Check]] · [[Unit-8-Summary]]
- [[Module-Mind-Map]]
- Sister modules in Path 5 (Secure data access):
  - [[../07-Path5-Module1-Secure-Data-Access/_MOC|Module M1 — Secure data access]] (OneLake / workspace-level controls)

## 📚 External references

- Microsoft Learn module page: <https://learn.microsoft.com/en-us/training/modules/secure-data-warehouse-in-microsoft-fabric/>
- [Security for data warehousing in Microsoft Fabric](https://learn.microsoft.com/en-us/fabric/data-warehouse/security)
- [Dynamic data masking in Fabric data warehousing](https://learn.microsoft.com/en-us/fabric/data-warehouse/dynamic-data-masking)
- [Row-level security in Fabric data warehousing](https://learn.microsoft.com/en-us/fabric/data-warehouse/row-level-security)
- [Column-level security in Fabric data warehousing](https://learn.microsoft.com/en-us/fabric/data-warehouse/column-level-security)
- [SQL granular permissions in Microsoft Fabric](https://learn.microsoft.com/en-us/fabric/data-warehouse/sql-granular-permissions)
- [DP-600 learning path](https://learn.microsoft.com/en-us/training/paths/implement-analytics-solutions-microsoft-fabric/)