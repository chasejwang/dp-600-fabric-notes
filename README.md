# DP-600 · Microsoft Fabric Analytics Engineer — Study Notes

> Personal study repository for the **Microsoft Certified: Fabric Analytics Engineer Associate** (Exam DP-600).
> 222 markdown files distilled from the official Microsoft Learn DP-600T00 course, structured as Obsidian-friendly notes with MOC indexes, mind maps, and frontmatter metadata on every unit.

## 📚 What's inside

| Type | Count | Purpose |
|---|---|---|
| **Unit notes** | 168 | Per-unit study notes with source URL, key takeaways, mermaid diagrams, and callout boxes |
| **Module mind maps** | 18 | One Mermaid mind map per learning module, rendered natively on GitHub |
| **MOC (Map of Content) indexes** | 22 | Hub pages that link to all units in a module, with prerequisites / next steps |
| **Master index + skills measured** | 5 | Top-level navigation, exam blueprint, and skill-domain coverage map |
| **Total** | **222** | 2.3 MB of focused study material |

All content is in **English** (per Microsoft Learn source) and renders cleanly on GitHub — Mermaid diagrams, YAML frontmatter, and Obsidian callout syntax are all GitHub-compatible.

## 🗂 Repository layout

```
dp-600-fabric-notes/
├── 01-Module-Intro-to-Fabric/                 # 1 module (Intro to Microsoft Fabric)
├── 02-Study-Guide-Index/                      # Skills measured + master mind map
│   ├── Learning-Paths/                        # 5 learning-path mind maps
│   └── Skill-Domains/                         # Per-domain deep dives
├── 03-Path1-Module{2-5}-…/                    # Path 1: Get started with Fabric (4 modules)
│   ├── 03-Path1-Module2-Discover-OneLake
│   ├── 03-Path1-Module3-Lakehouses
│   ├── 03-Path1-Module4-Warehouses
│   └── 03-Path1-Module5-Real-Time-Intelligence
├── 04-Path2-Module{1-5}-…/                    # Path 2: Ingest & transform data (5 modules)
├── 05-Path3-Module{1-5}-…/                    # Path 3: Implement & manage semantic models (5 modules)
├── 06-Path4-Module{1-3}-…/                    # Path 4: Build the semantic layer with Fabric IQ (3 modules)
├── 07-Path5-Module{1-3}-…/                    # Path 5: Secure & govern data (3 modules)
└── README.md                                  # ← you are here
```

Each module folder follows a consistent shape:

```
XX-PathY-ModuleN-Topic/
├── _MOC.md                # Map of Content — hub with nav + summary
├── Module-Mind-Map.md     # Mermaid mind map of the entire module
├── Unit-1-…-Title.md      # Per-unit notes (typically 4-12 units per module)
├── Unit-2-…-Title.md
├── …
├── Unit-N-Knowledge-Check.md    # Module assessment
└── Unit-N+1-Summary.md         # Module summary
```

## 🎯 Exam coverage (Microsoft blueprint)

DP-600 measures **5 functional groups** (weights from the official study guide):

| Domain | Weight | Modules in this repo |
|---|---|---|
| **Maintain a data analytics solution** (security, governance, DevOps lifecycle) | 25–30% | 07-Path5-Module{1-3} |
| **Prepare data** (ingestion, transformation, T-SQL, Spark) | 45–50% | 03-Path1-Module{2-5}, 04-Path2-Module{1-5} |
| **Implement and manage semantic models** (DAX, optimization, security) | 15–20% | 05-Path3-Module{1-5} |
| **Build the semantic layer with Fabric IQ** (ontology, semantic models) | 5–10% | 06-Path4-Module{1-3} |
| **Get started with Microsoft Fabric** (intro, OneLake, workloads) | 0–5% | 01-Module-Intro-to-Fabric |

> Source: <https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/dp-600>

## 🚀 How to use

### Read on GitHub (fastest)
1. Start at `02-Study-Guide-Index/_MOC.md` for the master index and skill map.
2. Pick a module folder → open `_MOC.md` for that module's nav.
3. Read `Module-Mind-Map.md` for the big picture, then drill into `Unit-N-…-Title.md` files.
4. Mermaid mind maps render inline. YAML frontmatter is preserved at the top of every unit.

### Read in Obsidian (richest)
1. Clone or download as ZIP.
2. Open the folder as a vault in Obsidian (or copy the folders into your existing vault).
3. Internal `[[wikilinks]]` become clickable cross-references; the graph view reveals the dependency structure.
4. The `![[…]]` embed syntax is intentionally not used — all cross-references are file-level so they survive a flat GitHub clone.

### Use as exam prep
- For each module, read `_MOC.md` → `Module-Mind-Map.md` → all `Unit-N-…md` files in order.
- End each module with `Unit-N-Knowledge-Check.md` (graded self-test) and `Unit-N+1-Summary.md` (recap).
- Track your progress with `02-Study-Guide-Index/Study-Guide-Skills-Measured.md` (skill-by-skill checklist).

## 🛠 Source

All content is derived from the official Microsoft Learn DP-600T00 course:
- Course: <https://learn.microsoft.com/en-us/training/courses/dp-600t00/>
- Exam: <https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/dp-600>

Each `Unit-N-…md` includes a `source:` frontmatter field linking to the exact Microsoft Learn page it summarizes, so the originals are always one click away for verification.

## 📜 License

This is a **personal study aid**. The underlying course content is © Microsoft. Notes are paraphrased and re-organized for personal learning; no commercial use. If you're preparing for the exam yourself, the official Microsoft Learn modules are free and recommended as the primary source.

---

<sub>Built July 2026 with parallel AI summarization + manual structure pass. 222 files, ~2.3 MB.</sub>
