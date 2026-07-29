---
title: "Module 5 — Real-Time Intelligence in Microsoft Fabric · Mind Map"
module: DP-600
type: mind-map
source: _MOC.md
tags:
  - dp-600
  - mind-map
  - mermaid
  - real-time-intelligence
---

# Module 5 — Real-Time Intelligence in Microsoft Fabric · Mind Map

```mermaid
mindmap
  root((Real-Time Intelligence<br/>Fabric Module 5))
    Concepts
      Events
        Discrete records of what happened
        Site clicks purchases sensor readings
      Streams
        Ordered sequences of events
        Continuous flow
      Near real-time
        Seconds to minutes latency
        Always some processing lag
      Use cases
        Delivery tracking
        Equipment monitoring
        Fraud detection
        Website performance
        System health
    Components
      Real-Time hub
        Streaming data catalog
        Data sources browse
        Azure sources connect
        Fabric events subscribe
        Azure events subscribe
      Eventstreams
        Sources
          Azure Event Hubs IoT Hubs Service Bus
          CDC feeds
          Kafka Pub-Sub MQTT
        Transformations
          Filter
          Manage fields
          Aggregate
          Group by
          Expand
          Join
          SQL code
        Destinations
          KQL database
          Lakehouse
          Derived stream
          Activator
          Custom endpoint
      Eventhouse
        KQL databases
          Tables stored functions materialized views shortcuts
        KQL Queryset
          KQL and T-SQL tabs
      Real-Time Dashboards
        Tiles per KQL query
        Auto-refresh
        Drill-in and filter
      Power BI
        Reports over KQL database
      Activator
        Events
        Objects
        Properties
        Rules
    Querying
      KQL syntax
        Pipe operators
        take where summarize project extend join
      T-SQL subset supported
      Copilot for Real-Time Intelligence
      Management commands
        Update policies
          Transform on ingest
        Materialized views
          Pre-aggregated tables
        Stored functions
          Reusable logic
    Ingestion paths
      Eventstream path
        Continuous transformation in line
      Direct ingestion path
        Land then transform
        Update policies automate
    Visualization
      Real-Time Dashboards for live ops
      Power BI for business reporting
      KQL Queryset to pin tiles
    Automation
      Activator rules
        Threshold triggers
        Send email or Teams
        Trigger Power Automate
        Run pipeline or notebook
    Lab
      Ingest real-time data
      Query and visualize
      Define threshold alert
    Assessment
      Component questions
      KQL operator questions
      Activator mental model
      Stream-to-stream join
      Aggregate transformation
      IoT latency diagnosis
```

## 🧭 How to view

- **Obsidian**: open this file, Obsidian will render the Mermaid block natively.
- **Web**: paste into <https://mermaid.live> for an editable SVG.
- **Export**: use the Mermaid CLI (`mmdc`) to render PNG/SVG.

## 🔗 Related

- [[_MOC]] — full module index
- [[Unit-1-Introduction]] · [[Unit-2-Real-Time-Analytics]] · [[Unit-3-RTI-Components]] · [[Unit-4-Ingest-Transform]] · [[Unit-5-Store-Query-KQL]] · [[Unit-6-Visualize-Real-Time]] · [[Unit-7-Automate-Actions]] · [[Unit-8-Exercise]] · [[Unit-9-Module-Assessment]] · [[Unit-10-Summary]]