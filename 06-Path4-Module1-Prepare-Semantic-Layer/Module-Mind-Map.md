---
title: "Module — Prepare the semantic layer for AI in Microsoft Fabric · Mind Map"
module: DP-600
type: mind-map
source: _MOC.md
tags:
  - dp-600
  - mind-map
  - mermaid
  - microsoft-fabric
  - power-bi
  - semantic-model
  - ai
  - copilot
  - fabric-iq
  - ontology
---

# Module — Prepare the semantic layer for AI in Microsoft Fabric · Mind Map

```mermaid
mindmap
  root((Prepare Semantic Layer<br/>for AI — Path 4 / M1))
    How AI Consumes Data
      RAG retrieve + generate
      Grounding data
        Names
        Descriptions
        Relationships
        Measures
        Linguistic schema
      Schema reduction
      Nondeterministic
      5-step grounding flow
        Prompt preprocess
        Send to Azure OpenAI
        Generate response
        RAI filters
        Return to user
    Model Complexity Effects
      Duplicate field names
      Complex DAX patterns
      Implicit measures
    Gold Layer Design
      One entity per table
      Star schema
      Business-friendly names
      Full words over abbreviations
      Consistent naming
      Units in column names
      Avoid dim_ / fact_ prefixes
    Descriptions
      Tables columns measures
      200-char truncation
      Copilot can auto-generate
      Then review and revise
    Hiding
      Surrogate keys
      ETL metadata columns
      Deprecated columns
    Linguistic Modeling
      Synonyms
      Linguistic relationships
      Q&A setup
      Field exclusion
    Prep for AI
      AI data schema
        Visibility control
        Hides from AI
      Verified answers
        Predefined visual
        Trigger phrases
        5 to 10 start
      AI instructions
        Free-form text
        Terminology rules scope
        Preferred measures
      Approved for Copilot
        Service designation
        Removes friction banners
        Commitment
    Enterprise Ontology
      Entity types properties rels
      Fabric IQ
      Foundry IQ
      Work IQ
      Generate Ontology
        Direct Lake
        Inbound public access
        Entity type definitions
        Property definitions
        Relationship definitions
        Data bindings
      Verify and complete
        Rename technical names
        Add entity type keys
        Time series bindings
    Validation
      Copilot pane
        Skill picker
        Reopen after changes
      HCAAT
        How Copilot arrived
      Download diagnostics
      Add to page
      9-item AI readiness checklist
      Iterate cycle
        Test identify improve
        Log incorrect answers
```

## 🧭 How to view

- **Obsidian**: open this file, Obsidian will render the Mermaid block natively.
- **Web**: paste into <https://mermaid.live> for an editable SVG.
- **Export**: use the Mermaid CLI (`mmdc`) to render PNG/SVG.

## 🔗 Related

- [[_MOC]] — full module index
- [[Unit-1-Introduction]] · [[Unit-2-Understand-AI-Needs]] · [[Unit-3-Design-Gold-Layers]] · [[Unit-4-Prepare-Semantic-Model]] · [[Unit-5-Enterprise-Ontology]] · [[Unit-6-Validate-Readiness]] · [[Unit-7-Exercise]] · [[Unit-8-Knowledge-Check]] · [[Unit-9-Summary]]
