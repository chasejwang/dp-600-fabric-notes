---
title: "Module Mind Map — Secure data access in Microsoft Fabric"
module: DP-600
unit_index: 1 of 5
xp_total: 800
duration_minutes: 70
source: https://learn.microsoft.com/en-us/training/modules/secure-data-access-in-fabric/
tags:
  - dp-600
  - mind-map
  - microsoft-fabric
  - security
  - workspace-roles
  - item-permissions
  - onelake-security
  - t-sql-permissions
  - defaultreader
  - least-privilege
---

# Module Mind Map — Secure data access in Microsoft Fabric

> [!info] Single-page overview
> This file mirrors the mind map in `[[_MOC]]` as a standalone Mermaid document. Open in Obsidian's Mermaid preview or paste into [Mermaid Live Editor](https://mermaid.live).

## 🗺️ Mind map

```mermaid
mindmap
  root((Secure Data Access in Fabric<br/>Module — Path 5 / M1))
    Fabric security model
      Three evaluation levels
        Microsoft Entra ID auth
          Can the user sign in
        Fabric access
          License tenant capacity
        Data security
          Four controls below
      Four data-security controls
        Workspace roles
        Item permissions
        Compute or granular
        OneLake security
      Broad to narrow
        Layered by design
    Workspace roles
      Admin
        Everything plus manage perms
      Member
        Everything except manage perms
        Can share
      Contributor
        Create view modify
        No share no perm mgmt
        Default for data engineers
      Viewer
        View only
        No OneLake data by default
      Assign via Manage access
        Users groups M365 dist lists
      Apply to all items
    Item permissions
      Share a specific item
      Read always granted
        Metadata plus reports
        Not underlying data
      Lakehouse extra permissions
        Read all SQL endpoint data
        Read all Apache Spark
          Adds recipient to DefaultReader
        Build reports on default SM
      Use Manage permissions
        Item context menu
    Granular permissions
      T-SQL DCL
        GRANT
        DENY
          Overrides GRANT
        REVOKE
        Row-level security
          Filter rows
        Column-level security
          Hide columns
        Dynamic data masking
          Mask values not data
      OneLake security roles
        RBAC model
        Data
          Tables or folders
        Permission
          Read
          ReadWrite
        Members
          Users or groups
        Constraints
          Optional row filters
          Optional column filters
        Enforced across engines
          Spark
          SQL
          OneLake APIs
      DefaultReader role
        Auto-created per lakehouse
        Full read access to all data
        Custom roles ignored if still in it
        Remove when using custom role
        Two-step rule
    Compute engines
      Spark
      SQL analytics endpoint
      OneLake APIs
    Common gotchas
      Custom OneLake role but still in DefaultReader
      Workspace role for table-level need
      Item permission for folder-level need
      Viewer without OneLake role sees item no data
      Admin Member Contributor unaffected by OneLake
    Knowledge check
      Three-level evaluation order
      Contributor for data engineer
      OneLake for Viewer with specific tables
      Custom role to fix DefaultReader folder access
      Column-level via OneLake
      Contributor scope no share
      Granular over workspace advantage
      OneLake Read for folder
      Item over workspace
      Viewer for read-only
      Healthcare table-restrict
      Sees item no data
```

## 🔁 Three evaluation levels (auxiliary diagram)

```mermaid
flowchart TD
    R["User request<br/>(report, notebook, T-SQL, OneLake API)"] --> L1{"Level 1: Microsoft Entra ID authentication<br/>Can the user sign in?"}
    L1 -- "No" --> D1[❌ Denied]
    L1 -- "Yes" --> L2{"Level 2: Fabric access<br/>License / tenant / capacity?"}
    L2 -- "No" --> D2[❌ Denied]
    L2 -- "Yes" --> L3{"Level 3: Data security<br/>Workspace role / item perm / T-SQL / OneLake role?"}
    L3 -- "No" --> D3[❌ Denied]
    L3 -- "Yes" --> OK[✅ Access granted]
```

## 🛡️ Four data-security controls (auxiliary diagram)

```mermaid
flowchart LR
    A["Data security<br/>(level 3)"] --> W["Workspace role<br/>all items · broadest"]
    A --> I["Item permission<br/>one item · medium"]
    A --> C["Compute permission<br/>one engine · narrow"]
    A --> O["OneLake security role<br/>tables or folders · narrowest"]
    W --> E["Effective access"]
    I --> E
    C --> E
    O --> E
    E --> R["Result: intersection<br/>of every layer granted"]
```

## ⚠️ The `DefaultReader` gotcha (auxiliary diagram)

```mermaid
flowchart TB
    U["User added to custom OneLake role<br/>(e.g., Read on Patient table)"] --> Q{"Is the user also in DefaultReader?"}
    Q -- "Yes (default after Read all Apache Spark)" --> L["❌ User still has full read access via DefaultReader<br/>Custom role is a no-op for Spark and OneLake API access"]
    Q -- "No (removed from DefaultReader)" --> R["✅ User sees only the custom role's data<br/>(e.g., only the Patient table)"]
    Q -- "Not sure" --> S["⚠️ Assume yes until verified"]
```

## 🧭 Decision rule (auxiliary diagram)

```mermaid
flowchart TD
    A["What does the user need?"] --> B{"All items in<br/>a workspace?"}
    B -- "Yes" --> W["Workspace role"]
    B -- "No" --> C{"One specific item?"}
    C -- "Yes" --> I["Item permission"]
    C -- "No, granular" --> E{"Which engine?"}
    E -- "SQL analytics endpoint" --> S["T-SQL permissions<br/>GRANT / DENY / REVOKE<br/>+ RLS / CLS / DDM"]
    E -- "Spark / OneLake APIs" --> O["OneLake security role<br/>+ remove from DefaultReader"]
```

## 🧭 Related

- [[_MOC]] — module index
- [[Unit-1-Introduction]] · [[Unit-2-Understand-Fabric-Security-Model]] · [[Unit-3-Configure-Workspace-and-Item-Permissions]] · [[Unit-4-Apply-Granular-Permissions]] · [[Unit-5-Exercise]] · [[Unit-6-Knowledge-Check]] · [[Unit-7-Summary]]
- Sister modules:
  - [[../05-Path3-Module4-Enforce-Security/_MOC|Module P3-M4 — Enforce semantic model security]] (RLS + OLS at the *model* layer)
