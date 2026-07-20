# Iteration 1 — Engineering Audit & Dissertation Blueprint
## "Foundation, Core Concept, Data Layer, and Governance Stabilization"

**Status:** Pre-writing reconstruction only. No LaTeX, no prose paragraphs, no dissertation content. This is the design blueprint from which Chapter 4 / Iteration 1 will later be written.

**Scope discipline applied:** This audit is restricted to `Capstone/01_Research_And_Foundation_Report/` — specifically the six documents fully read: `Week_1__Report.pdf`, `Week_2_Report.pdf`, `System_Architecture__Property_Intelligence_Infrastructure.pdf`, `MASTER_STRATEGY_REPORT_FINAL_VERSION.pdf`, `Execution_Plan_for_Portugal_Property_Intelligence_Infrastructure.pdf`, `Property_Intelligence_Engine_(PIE).pdf`. Three items in the folder were **not** opened in this pass (`3rd_Week.pdf`, `Week 1-5.docx`, `Property_Intelligence_Engine_(PIE)-Platform_Report_Week7.pdf`) — see §10 Writing Readiness Report for the effect of this gap.

**Critical boundary finding (read this first):** Every document read in this folder is a **pre-implementation design artifact** — market research, strategy, architecture proposal, scoring-formula specification. None contains working code, a trained model, or a real dataset. The first actual implementation (Ames Housing dataset, working AIRCS prototype, Gradient Boosting Regressor) appears in `Week_6.md`, which lives in `02_Product_1_Aura_AI Platform.../` — a **different folder**, explicitly out of scope for this audit per the task instructions. This means:

> **Iteration 1 = the conceptual and architectural foundation only (research → strategy → designed architecture → designed governance). Iteration 2 = the first working build (PIE on Ames data, seller pivot, V4 crisis, V5–V7 governance rebuild).**

This resolves an apparent tension in the Iteration 1 title: "Data Layer" and "Governance Stabilization" in Iteration 1 refer to the **proposed** lakehouse/AIRCS pipeline and the **proposed** Data Governance Framework (Master Strategy §8.5) — not the real dataset versions (V1/V2/Final) or the real leakage-remediation governance work, which happened much later and belongs in Iteration 2.

---

## 1. Repository Chronology Reconstruction

| # | Milestone | Engineering objective | Evidence | Deliverable produced | Architectural impact | Survived to final ecosystem? |
|---|---|---|---|---|---|---|
| 1 | Week 1, Days 1–2 | Understand the real estate industry and PropTech landscape from zero | `Week_1__Report.pdf` pp.1–4 | Market/stakeholder taxonomy, PropTech phase model (Pre-Development/Construction/Property Mgmt) | None yet — pure orientation | No (background only) |
| 2 | Week 1, Days 3–4 | Map global vs. Portuguese PropTech maturity; identify data-science opportunity | `Week_1__Report.pdf` pp.4–10 | Competitor scan (ButterflyMX, Infraspeak, EliseAI, Guesty, OpenSpace, CorkBrick); conclusion: "predictive pricing and integration are underdeveloped in Portugal" | Strategic thesis: build predictive + integrated intelligence, not another dashboard | Yes — this thesis is the seed of AIRCS/AICF |
| 3 | Week 2 | Deep-dive Portuguese market tools and valuation theory | `Week_2_Report.pdf` | Tool teardown (Casafari, Alfredo AI, OpenSpace), valuation methods (Comparative, Income/Yield+DCF, Cost/Replacement), Due Diligence 5-checks, buyer journey, financing types, ESG/EPC regs, AI compliance (EU AI Act, GDPR, DORA) | Structured domain knowledge base | Establishes the **regulatory drivers** (Simplex, EPBD) later repeated verbatim in `introduction.tex` |
| 4 | (undated, early) | Define system architecture | `System_Architecture__Property_Intelligence_Infrastructure.pdf` | Full 4-figure architecture: Platform Ecosystem, Data Pipeline (Bronze/Silver/Gold), AIRCS Model, Technical Infrastructure | First **complete architecture diagram set** of the whole project | Partially — Bronze/Silver/Gold lakehouse concept persists into all later versions; PostgreSQL+PostGIS/FastAPI/Node stack was later replaced |
| 5 | (undated, mid) | Formalize business + technical strategy | `MASTER_STRATEGY_REPORT_FINAL_VERSION.pdf` | Full AIRCS formula + weight rationale, AICF formula, data governance framework, predictive sourcing engine, business model, revenue scenarios, glossary | The single richest technical-strategic document in the corpus | AIRCS/AICF formulas persist essentially unchanged into `core_context.md` (later report) |
| 6 | (undated, mid-late) | Convert strategy into a 90-day execution plan | `Execution_Plan_for_Portugal_Property_Intelligence_Infrastructure.pdf` | 4-phase roadmap, step-by-step data pipeline (7 stages), pilot design (10–50 properties), team roles (Ash = technical advisor) | Operational plan — first appearance of concrete task lists, acceptance criteria, pilot metrics | Superseded once actual work started; the *pipeline stages* concept persisted |
| 7 | (undated, late) | Specify the analytical engine design in isolation from the platform strategy | `Property_Intelligence_Engine_(PIE).pdf` | 3-layer system design (Data Processing / Analytical Intelligence / Visualization), 10 analytical modules (AIRCS, AICF, Deal Finder, ROI, Renovation Simulator, Market Inefficiency Detection, Clustering, XAI layer, Stress-Test, Digital Twin) | Names PIE as **the core AI system**, distinct from the ecosystem-level PropCheck/REZERVA/InspectOS branding | Deal Finder, ROI modeling, XAI layer, stress-testing all reappear (renamed) in later product reports (Decision Engine, SHAP, Scenario Engine) |

**Inference rule applied:** the four architecture/strategy PDFs (System Architecture, Master Strategy, Execution Plan, PIE) carry no week numbers and cannot be dated relative to each other with certainty. Ordering above (System Architecture → Master Strategy → Execution Plan → PIE) is inferred from internal cross-references: Execution Plan explicitly says "The implementation follows the execution roadmap defined in the Master Strategy Report," and both System Architecture and Master Strategy independently define AIRCS/AICF with identical formulas, suggesting System Architecture is the earlier, narrower technical draft and Master Strategy the consolidated final version. **This ordering is an interpretation, not a documented fact.**

---

## 2. Architecture Evolution Analysis (within Iteration 1)

Unlike later iterations, Iteration 1 shows **no rebuild-triggered pivot** — there was no working system yet to fail. What evolved instead was the **scope and precision of the architecture description** across the four design documents:

```
System Architecture PDF
   (first complete diagram set: 4 figures,
    PostgreSQL+PostGIS, FastAPI/Node, Docker, RabbitMQ)
        ↓
   Gap discovered: no business model, no governance
   detail, no execution sequencing
        ↓
Master Strategy Report
   (adds: AIRCS weight rationale + formula + scoring
    architecture ASCII diagram; AICF cost-estimation
    framework; data governance framework; business
    model + revenue scenarios; competitive landscape
    table; glossary)
        ↓
   Gap discovered: strategy has no day-by-day execution
   plan or pilot design
        ↓
Execution Plan
   (adds: 4-phase 90-day roadmap; explicit 7-stage data
    pipeline; pilot design with success metrics; team
    roles; GDPR/security checklist)
        ↓
   Gap discovered: the analytical engine itself (PIE)
   needs its own system-design document independent of
   platform/business framing
        ↓
PIE System Design
   (adds: 3-layer architecture; 10 named analytical
    modules; explicit workflow: ingestion → feature
    engineering → AIRCS → AICF → ROI/Deal Finder →
    market analysis → simulation → decision/visualization)
```

**Reason for this evolution:** each document fills a gap the previous one left — architecture → strategy/business case → execution sequencing → analytical-engine specification. This is a **planning maturation sequence**, not a technical-failure-driven pivot (which is the pattern seen in later iterations, e.g. the broken-XGBoost crisis).

**What stayed constant across all four documents (evidence of early architectural stability):**
- Three-platform structure: PropCheck (buyer) / REZERVA (seller) / InspectOS (inspection)
- AIRCS weights: 30/25/20/15/10 (Physical Integrity / Regulatory Compliance / Market Alignment / Energy Performance / Environmental Risk) — **identical** in System Architecture and Master Strategy
- Bronze/Silver/Gold lakehouse pattern
- Data flywheel concept (transactions → inspections → better AIRCS → more trust → more transactions)

---

## 3. Engineering Decisions Log (Iteration 1 only)

| Decision | Why introduced | Alternatives considered (if documented) | Evidence | Influence on later development |
|---|---|---|---|---|
| Adopt a **three-platform ecosystem** (PropCheck/InspectOS/REZERVA) rather than a single app | Separate buyer, inspection, and seller concerns from the start | None documented — presented as the chosen design directly | System Architecture §2, Master Strategy §2 | Persists structurally; later products (P1/P2/P3) are a different three-way split, but the "don't build one monolith" instinct is the same |
| **Seller-first strategic priority** stated at the strategy level | REZERVA "operates in the Liminal Space" to capture supply before public listing — framed as more defensible than buyer-side competition | Buyer-first (implicit alternative, rejected) | Master Strategy §12 (REZERVA), §"Strategic Differentiation" | Directly foreshadows the Week 8 seller-first pivot in Iteration 2 — this decision was made at the **strategy level in Iteration 1**, then **executed at the product level in Iteration 2** |
| **AIRCS weighting fixed at 30/25/20/15/10** (Physical/Regulatory/Market/Energy/Environmental) | Physical integrity and regulatory compliance judged to have the largest financial/legal impact on transactions | None numerically alternative documented; qualitative rationale given per dimension | Master Strategy §6.2 "AIRCS Weight Rationale" | These exact weights reappear unchanged in `core_context.md` (Iteration 2 evidence) — a rare case of a Iteration-1 number surviving verbatim |
| **Expert-defined weights now, ML-calibrated weights later** | No data exists yet to fit weights empirically; domain knowledge is the only available signal | Immediate ML fitting (rejected — no data) | Master Strategy §6.1 "AIRCS Model Evolution" | Sets the precedent for the "prototype now, calibrate with data later" philosophy applied throughout the project |
| **Lakehouse (Bronze/Silver/Gold) over a single database** | Separates raw-data preservation (traceability) from cleaned data from analytical features | Direct single-table ingestion (implicit rejected alternative) | System Architecture §5, Execution Plan Phase 1 | Persists as a named pattern through Week 12/13 (data pipeline descriptions) and into the final Dataset A/B/C separation philosophy |
| **Multiple data-acquisition channels (Plan A/B/C: licensed / public / proprietary)** | Mitigate the risk of depending on a single third-party provider (Idealista/CASAFARI could restrict access) | Single-provider dependency (rejected as high risk) | Master Strategy §8.2 "Data Dependency Risk Management" | Foreshadows why the project later builds proprietary InspectOS/VISBO data rather than relying only on scraped listings |
| **AICF = Market Value − Renovation Cost** (simple subtractive correction, not a multiplicative or ML-based correction) | Simplicity and interpretability for a first version; renovation cost is the dominant, explainable driver of valuation gap | Not documented; presented directly | Master Strategy §7, PIE §4.2 | This exact formula persists into `core_context.md` and the Week 6 prototype's simplified AICF |
| **Explainability required "by design," not bolted on** | Supervisor concern (referenced in later reports) that high model performance without explanation is not defensible; principle stated already in PIE's "Explainable AI Layer" (§4.8) | Black-box scoring (rejected) | PIE §4.8 | Becomes a load-bearing principle across the entire ecosystem (SHAP in P1, deterministic explanations in P2/P3) |
| **GDPR/EU AI Act compliance treated as a first-class constraint**, not an afterthought | Regulatory environment (GDPR, EU AI Act, DORA) explicitly researched in Week 2 and re-stated as governance principles in Master Strategy | Not documented as a choice — treated as a hard requirement | Week 2 "Regulations & AI Compliance"; Master Strategy §8.5 | Underlies later "honest failure" and governance-registry design philosophy in Products 2 and 3 |

---

## 4. Initial System Architecture (as designed, not yet implemented)

### 4.1 Core data flow (documented ASCII diagram, System Architecture p.1–2)
```
DATA SOURCES
   ↓
DATA INGESTION LAYER
   ↓
DATA PIPELINE & LAKEHOUSE
   ↓
AIRCS INTELLIGENCE ENGINE
   ↓
APPLICATION PLATFORMS (PropCheck / REZERVA)
   ↓
PROPERTY TRANSACTIONS
   ↓
INSPECTION FEEDBACK
   ↓
DATA FLYWHEEL
```

### 4.2 Architecture layers and responsibilities
| Layer | Responsibility | Components named |
|---|---|---|
| Data Source Layer | Provide heterogeneous raw inputs | Listing Data (Idealista, Imovirtual, CASAFARI), Transaction Data (SIR/Confidencial Imobiliário), Inspection Data (InspectOS), Regulatory Data (PEPU, municipal), FSBO Signals (VISBO) |
| Data Ingestion Layer | Acquire data via multiple mechanisms | API Integrations, Web Scraping, Public Dataset Imports, Internal Data Generation (inspection app) |
| Data Pipeline / Lakehouse | Transform raw → analytical data | Bronze (raw), Silver (cleaned/normalized), Gold (engineered features) |
| Intelligence Layer | Convert features into decisions | AIRCS Engine, AICF Valuation Adjustment, Predictive Sourcing Engine |
| Application Layer | Deliver intelligence to users | PropCheck (buyer), REZERVA (seller), Inspection Marketplace |
| Institutional Interfaces | External consumption | AIRCS API, Bank integrations, Analytics dashboards |

### 4.3 System boundaries
- **Internal/proprietary:** InspectOS inspection data, renovation cost database, compliance indicators, VISBO FSBO signals.
- **External/licensed:** SIR transaction database (Confidencial Imobiliário), listing platforms (Idealista, Imovirtual, CASAFARI), public regulatory datasets (PEPU, INE, municipal).
- **Two user-facing applications:** PropCheck (buyer) and REZERVA (seller), explicitly **not** merged into one interface — this boundary is preserved conceptually (though not literally) in the later Dual-Plane Architecture (Predictive vs. Contextual) documented in Product 1's SCRUM PI.

### 4.4 Technology stack as originally specified (Iteration 1 only — do not confuse with later stacks)
| Layer | Technology (System Architecture p.13–14) |
|---|---|
| Frontend | Next.js / React |
| Backend APIs | FastAPI / Node.js |
| Database | PostgreSQL + PostGIS |
| Data Storage | Lakehouse (Bronze/Silver/Gold) |
| Background Jobs | RabbitMQ / Inngest |
| Data Processing | Python pipelines |
| Inspection App | React Native |
| Hosting | Docker / containerized infrastructure |

**Note for later iterations:** none of this stack matches what Week 6–7 actually implemented (Streamlit prototype → FastAPI+React with GradientBoostingRegressor on Ames data). This is a documented **design-to-implementation gap** worth naming explicitly in Chapter 4 as evidence that Iteration 1 was planning, not building.

---

## 5. Data Architecture (as designed)

### 5.1 Data source inventory (proposed, not yet collected)
| Category | Sources | Attributes | Role |
|---|---|---|---|
| Listing data | Idealista, Imovirtual, CASAFARI | price, location, area, construction year, rooms, EPC rating, listing date | Real-time market signal |
| Transaction data | SIR (Confidencial Imobiliário) | final price, date, characteristics, coordinates | Market alignment / valuation ground truth |
| Inspection data | InspectOS (proprietary, internal) | structural defects, electrical/plumbing condition, roof/façade integrity, energy indicators, renovation cost estimate | Proprietary moat; feeds AIRCS Physical Integrity |
| Regulatory data | PEPU permit system, municipal licensing, zoning | compliance status, permit records | Feeds AIRCS Regulatory Compliance |
| FSBO signals | VISBO platform | property prep activity, doc uploads, early inquiries | Early supply-detection for REZERVA |

### 5.2 Pipeline stages (documented twice, consistently, in System Architecture §5 and Execution Plan §"Data Pipeline—Step-by-Step")
1. Property canonicalization (central index by cadastral reference/address)
2. Bronze ingestion (raw JSON/CSV, scraper/API/inspection outputs)
3. Silver normalization (address standardization, dedup, missing-value handling, schema standardization)
4. Gold feature engineering (structural integrity score, permit compliance score, price deviation, energy efficiency ratings, environmental risk index)
5. AIRCS scoring (weighted combination → 0–100 score + breakdown)
6. AICF calculation (renovation cost aggregation → adjusted valuation)
7. Monitoring & lineage (dataset versioning, logging per version)

### 5.3 Data governance framework (Master Strategy §8.5 — this is the "Governance Stabilization" half of the Iteration 1 title)
| Principle | Mechanism (as designed) |
|---|---|
| Data Quality Control | Standardized inspection templates + automated consistency checks |
| Dataset Versioning | Version-controlled data layers for reproducibility/audit |
| Model Transparency | Logged changes to AIRCS scoring model and weights |
| Data Privacy Compliance | GDPR-compliant processing of all personal/transactional data |
| Bias Monitoring | Periodic evaluation of models for valuation/risk-scoring bias |

**Important distinction for Chapter 4:** this is a **governance framework proposed on paper**, not a governance system that was ever validated against real data in Iteration 1. The real governance stabilization (leakage removal, temporal-safe validation) happens later, in response to actual failures — that belongs in Iteration 2, not here. Iteration 1's contribution is that governance was **designed in from the start**, before any code existed — worth stating as evidence of "governance by design" philosophy, without overstating it as "governance achieved."

### 5.4 Dataset foundation — what existed vs. what was only planned
| Item | Status in Iteration 1 |
|---|---|
| Real Portuguese dataset | **Not yet existing** — only named as intended sources (SIR, Idealista, PEPU, INE) |
| InspectOS inspection dataset | **Not yet collected** — described as a future proprietary moat |
| Pilot dataset | **Planned only** — Execution Plan specifies a 10–50 property pilot (Lisbon/Cascais) that had not yet run |
| Any dataset resembling V1/V2/Final (Cat1–Cat9) | **Does not exist yet** — those are Iteration-2/3+ artifacts (per Dataset Evolution Report, first fused dataset appears at V5/Week 12) |

**Do not describe Dataset V1/V2/Final in this iteration** — they belong to Chapter 3 (already written) and to later iterations.

---

## 6. AIRCS Foundation (the analytical centerpiece of Iteration 1)

### 6.1 Why AIRCS was introduced
Documented reasoning (Master Strategy §1, §6.2): transaction price data does not capture true asset condition ("Transaction truth does not equal asset truth"). A property's real value depends on structural integrity, regulatory compliance, renovation costs, energy efficiency, and market demand — none of which appear in a listing price. AIRCS was designed to convert these multiple, heterogeneous signals into **one standardized, interpretable score**.

### 6.2 Scoring architecture
```
Property Data Sources
│
├── Inspection Data (InspectOS)    → structural condition, defect severity
├── Regulatory Data                → permit compliance, licensing status
├── Market Data                    → transaction comparables, price deviation
├── Energy Data                    → EPC rating, retrofit exposure
└── Environmental Data             → flood risk, zoning restrictions
        ↓
   Feature Engineering (normalize each to 0–100)
        ↓
   Weighted Scoring Model
        ↓
   AIRCS SCORE (0–100 scale)
```

### 6.3 Formula (identical across System Architecture and Master Strategy — high-confidence, stable fact)
```
AIRCS = 0.30 × Physical Integrity
      + 0.25 × Regulatory Compliance
      + 0.20 × Market Alignment
      + 0.15 × Energy Performance
      + 0.10 × Environmental Risk
```

### 6.4 Score interpretation bands
| Score | Risk Level |
|---|---|
| 85–100 | Low risk |
| 65–84 | Moderate risk |
| 40–64 | High risk |
| <40 | Critical risk |

### 6.5 Worked example (Master Strategy §7.2 — useful as a dissertation figure/example)
- Property: Cascais apartment, listed €520,000
- Market comparables → estimated value €490,000
- Inspection finds aging roof insulation, outdated wiring, façade deterioration → renovation cost €55,000
- AIRCS component scores: Physical 62, Regulatory 85, Market 68, Energy 60, Environmental 90 → **Final AIRCS = 69 (Moderate Risk)**
- AICF: €490,000 − €55,000 = **€435,000 adjusted value**

### 6.6 DSRM phase mapping for AIRCS content
| AIRCS element | DSRM phase |
|---|---|
| "Transaction truth ≠ asset truth" problem framing | Problem Investigation |
| Formula, weights, weight rationale, scoring architecture diagram | Solution Design |
| None — no real property was scored against ground truth yet | Design Validation (not yet performed in Iteration 1) |
| None — no code exists yet | Solution Implementation (not yet performed in Iteration 1) |
| Worked numerical example (Cascais property) | **This is a hypothetical illustration, not an evaluation** — classify as Solution Design, not Solution Evaluation |

**Important:** Iteration 1 has *no* Design Validation or Solution Implementation evidence for AIRCS. The worked example is a paper illustration of the formula, not a validated test. This has direct consequences for how thin the Iteration-1 "Design Validation" and "Solution Implementation" subsections should be (see §11).

---

## 7. Product Foundation — what "Product 1" actually contained at this stage

| Category | Item | Status |
|---|---|---|
| Conceptual idea | PropCheck (buyer platform) | Named, described, no code |
| Conceptual idea | REZERVA (seller platform) | Named, described, no code |
| Conceptual idea | InspectOS (inspection infrastructure) | Named, described, no code |
| Conceptual idea | AIRCS engine | Formula fully specified, **not implemented** |
| Conceptual idea | AICF | Formula fully specified, **not implemented** |
| Conceptual idea | Predictive Sourcing Engine | Signal list specified (inheritance filings, tax irregularities, EPC expiry, utility anomalies, permit requests, ownership duration), **no model, no data** |
| Conceptual idea | VISBO (FSBO seller SaaS) | Named and rationalized, not built |
| Planned component | AIRCS API for banks/institutions | Named as future institutional interface, not built |
| Planned component | Buyer Vault (Speed/Alpha/Yield/Portfolio buyer segmentation) | Named only |
| Architecture (designed, not built) | Full lakehouse + PostgreSQL/PostGIS + FastAPI/Node stack | Diagrammed, not implemented |
| Explicit non-existence | Any trained model | **None exists in Iteration 1** |
| Explicit non-existence | Any real dataset | **None exists in Iteration 1** |
| Explicit non-existence | Any deployed API/UI | **None exists in Iteration 1** |

**This table is the single most important control for Chapter 4 accuracy** — it prevents the common mistake of describing Iteration 1 as if the AIRCS engine or PropCheck/REZERVA platforms already existed as software.

---

## 8. Technologies Genuinely Belonging to Iteration 1

| Category | Item | Evidence |
|---|---|---|
| Frontend (proposed) | Next.js, React | System Architecture §8.1 |
| Frontend (inspection app, proposed) | React Native | System Architecture §8.1 |
| Backend (proposed) | FastAPI, Node.js | System Architecture §8.1 |
| Database (proposed) | PostgreSQL + PostGIS | System Architecture §8.1 |
| Data storage pattern (proposed) | Lakehouse (Bronze/Silver/Gold) | System Architecture §5 |
| Background jobs (proposed) | RabbitMQ, Inngest | System Architecture §8.1 |
| Data processing (proposed) | Python pipelines | System Architecture §8.1, Execution Plan |
| Hosting (proposed) | Docker / containerized infrastructure | System Architecture §8.1 |
| Data acquisition methods (proposed) | REST APIs, web scraping, public dataset import | System Architecture §4 |

**Explicitly NOT part of Iteration 1** (these appear only from Week 6 onward, i.e. Iteration 2): Streamlit, scikit-learn GradientBoostingRegressor, LightGBM, XGBoost, joblib, Gemini API, Chart.js, Framer Motion, html2canvas/jsPDF, Ames Housing dataset. None of these names should appear in the Iteration 1 write-up.

---

## 9. Figure Design Specifications

All four figures below are **redrawn from repository evidence** (the source PDFs contain dark-background boxed diagrams unsuitable for direct reuse — screenshots must be avoided per instructions). Recommend clean, minimalist redraws consistent with the Chapter 2/3 visual style already established (see the `aura_development_journey.png` figure already produced for the chapter intro).

### Figure 4.1 — Portugal Property Market Problem Landscape
- **Purpose:** ground the reader in *why* the project exists before any architecture is shown.
- **Subsection:** Problem Investigation
- **Diagram type:** simple layered/funnel diagram
- **Content:** Information asymmetry → no unified MLS → fragmented listings/private transactions → regulatory pressure (Simplex DL 10/2024, EPBD) → valuation gap (market price ≠ asset truth)
- **Abstraction level:** conceptual, no technical labels
- **Orientation:** portrait or landscape, single column, ~0.6–0.8 linewidth
- **Redraw from evidence:** synthesized from Week 1 + Week 2 + Master Strategy §1/§4 (no single source diagram exists — this figure must be newly composed from text, clearly labeled as an authorial synthesis)

### Figure 4.2 — Initial Platform Ecosystem Architecture
- **Purpose:** show the three-platform + AIRCS ecosystem as originally conceived
- **Subsection:** Solution Design
- **Diagram type:** layered box-and-arrow (mirrors System Architecture Figure 1 / Master Strategy §5 diagram)
- **Component hierarchy:** Data Sources (Listing/Transaction/Inspection/Regulatory/FSBO) → Data Ingestion → Data Lakehouse → AIRCS Engine → {PropCheck, REZERVA} → Market Transactions → Inspection Feedback → Data Flywheel (loop back to Data Sources)
- **Flow direction:** top-to-bottom with one feedback loop at the bottom returning to the top (same *shape* as the Ch.4 intro figure, larger and more detailed)
- **Orientation:** portrait, full-page width
- **Redraw source:** System Architecture Figure 1 (p.3) + Master Strategy §5 diagram (near-identical content, safe to merge into one authoritative figure)

### Figure 4.3 — AIRCS Scoring Architecture
- **Purpose:** explain how five heterogeneous data categories become one score
- **Subsection:** Solution Design
- **Diagram type:** funnel/aggregation diagram
- **Component hierarchy:** 5 input categories (Inspection/Regulatory/Market/Energy/Environmental) → Feature Engineering layer → 5 weighted risk-dimension boxes (30/25/20/15/10%) → Weighted Scoring Engine → single AIRCS Score output (0–100)
- **Labels:** include the weight percentages directly on the diagram (high pedagogical value, directly traceable to the formula)
- **Orientation:** portrait, ~0.7 linewidth
- **Redraw source:** System Architecture Figure 3 (p.9) + Master Strategy §6.5 ASCII tree — these two sources describe the same structure; merge

### Figure 4.4 — Data Governance & Lakehouse Pipeline
- **Purpose:** show the Bronze/Silver/Gold pipeline and where governance controls attach
- **Subsection:** Solution Design (pipeline) with a callout box for Design Validation criteria (governance principles)
- **Diagram type:** horizontal pipeline with annotated governance checkpoints
- **Component hierarchy:** Data Sources → Ingestion (API/Scraper/Import) → Bronze (raw) → Silver (cleaned) → Gold (features) → AIRCS Engine; governance annotations (versioning, quality control, bias monitoring, GDPR) attached at Silver/Gold boundary
- **Orientation:** landscape (pipeline reads left-to-right better than top-to-bottom for 5+ stages)
- **Redraw source:** System Architecture Figure 2 (p.8) + Execution Plan "Data Pipeline—Step-by-Step" (7 stages) — Execution Plan's list is more granular; use it to enrich the System Architecture diagram rather than duplicate both

**Do NOT include as a standalone figure (recommend against):** a "Predictive Sourcing Engine" diagram — the repository gives only a bullet list of signals (inheritance filings, tax irregularities, etc.) with no architecture, no data, no model. A figure here would visually overstate what exists. Mention it in text only.

---

## 10. Table Design Specifications

| # | Title | Columns | Rows (source) | Purpose | Subsection |
|---|---|---|---|---|---|
| T4.1 | AIRCS Risk Dimensions and Weights | Dimension, Weight, Purpose | 5 rows (Master Strategy §6, "AIRCS Model") | Anchor the formula in a scannable reference table | Solution Design |
| T4.2 | Score Interpretation Bands | Score range, Risk Level | 4 rows | Show how the 0–100 output becomes an actionable decision | Solution Design |
| T4.3 | Initial Technology Stack (Iteration 1, as designed) | Layer, Technology | 8 rows (System Architecture §8.1) | Give a concrete, falsifiable list of what was *planned*, to contrast later with what was *actually built* in Iteration 2 | Solution Design |
| T4.4 | Data Source Inventory | Category, Source, Attributes, Role | 5 rows (§5.1 above) | Show the heterogeneity the architecture had to integrate | Problem Investigation / Solution Design |
| T4.5 | Data Governance Principles | Principle, Mechanism | 5 rows (Master Strategy §8.5) | Ground the "Governance Stabilization" half of the iteration title in a concrete table rather than prose alone | Solution Design |
| T4.6 | Engineering Decision Log (condensed) | Decision, Rationale, Evidence | 5–6 selected rows from §3 above | Give the reader the DSRM-style "why" behind key choices | Solution Design / Design Validation |

**Avoid as tables (decorative / low value):** the Master Strategy's revenue-scenario table (0.5%/1%/3%/5% market penetration → €2.3M–€23.1M) is a business-model projection, not an engineering artifact — it belongs in a business/commercial appendix, not Chapter 4, and should be excluded or only footnoted.

---

## 11. Subsection-by-Subsection Blueprint

### 11.1 Problem Investigation
**Discuss:**
- Information asymmetry in Portuguese real estate (no unified MLS, private high-value transactions, listing-price-only tools)
- The "transaction truth ≠ asset truth" gap (Master Strategy §1)
- Regulatory pressure: Simplex/DL 10/2024 (shifts verification burden to buyers), EPBD (forces costly energy retrofits)
- Structural market gaps: 10–15% typical asking-vs-final-price discrepancy, fragmented permit databases, high brokerage commissions (~6%), weak agent exclusivity
- FSBO market opportunity as an underused signal source
- Existing tool landscape (Casafari, Alfredo AI, OpenSpace) and their limitations (comps-only, no inspection data, no predictive sourcing)

**Do NOT discuss:** AIRCS formula details (belongs in Design), any dataset specifics (none exist yet), any product-level detail (PropCheck/REZERVA feature lists — save for Design)

**Figures:** Figure 4.1 (Problem Landscape)
**Tables:** T4.4 (Data Source Inventory) — optional here or in Design; better placed in Design since it's about the *proposed* solution's inputs, not the problem itself. Recommend keeping Problem Investigation table-light.

### 11.2 Solution Design
**Discuss:**
- Three-platform ecosystem design (PropCheck/InspectOS/REZERVA) and the seller-first strategic rationale
- Full system architecture (data source → ingestion → lakehouse → AIRCS → applications → flywheel)
- AIRCS formula, weight rationale, scoring architecture
- AICF formula and worked example
- Data governance framework (5 principles)
- Data acquisition risk mitigation (Plan A/B/C)
- Technology stack as designed
- PIE's 3-layer / 10-module analytical framework (as a design artifact — this is where PIE's "Deal Finder," "ROI modeling," "Renovation Simulator," "Explainable AI Layer," "Digital Twin" concepts belong)

**Do NOT discuss:** any implementation detail, any real dataset, any code file names (`pie_engine.py` etc. belong to Iteration 2), Gemini/Streamlit/scikit-learn

**Figures:** 4.2 (Ecosystem Architecture), 4.3 (AIRCS Scoring), 4.4 (Governance Pipeline)
**Tables:** T4.1, T4.2, T4.3, T4.4, T4.5

### 11.3 Design Validation
**Discuss (honestly, and briefly — this is the thinnest subsection in Iteration 1):**
- The AIRCS weighting was validated only **qualitatively**, against domain-knowledge rationale (structural defects and legal irregularities cited as primary cost drivers in real-estate risk literature) — **not against data**
- The worked numerical example (Cascais property, AIRCS=69) is a **hand-computed illustration of formula correctness**, not an empirical validation
- Explicitly state the documented limitation: "the accuracy of the AIRCS scoring model depends on the availability and quality of underlying datasets... during early stages, inspection and transaction datasets may remain limited" (Master Strategy §20.1)
- Governance framework was designed against known regulatory requirements (GDPR, EU AI Act) — this is a compliance-alignment validation, not a technical one

**Do NOT overstate:** do not claim any model was tested, any pilot ran, or any dataset was validated in Iteration 1 — none of this happened yet per the evidence.

**Figures:** none required
**Tables:** none required (could reference T4.6 decision log if useful for flow)

### 11.4 Solution Implementation
**Discuss (also necessarily thin and honest):**
- No code was implemented in this iteration per the available evidence
- What *was* "implemented" is the **execution roadmap itself**: the Execution Plan's 4-phase, 90-day plan with concrete tasks (ingest SIR data, integrate PEPU feed, deploy InspectOS inspection template, complete 10 pilot inspections in Phase 1; build AIRCS scoring model, evaluate 50 properties in Phase 2; launch predictive watchlist, pilot AIRCS API with a bank in Phase 3; expand to 200+ properties, launch PropCheck subscription in Phase 4)
- Team roles were defined (technical architecture advisor, two data-engineering members, supervisor) — this is organizational implementation, not technical
- State explicitly: this roadmap is the **bridge artifact** between Iteration 1 (design) and Iteration 2 (first real build) — Iteration 2 should open by referencing whether/how these 90 days actually unfolded

**Do NOT discuss:** anything from Week 6+ (Ames dataset, Streamlit, GradientBoostingRegressor) — that is Iteration 2's Solution Implementation, not Iteration 1's

**Figures:** could include a simple roadmap/Gantt-style figure of the 4 phases if the chapter wants one, but not required — a table suffices
**Tables:** could add a small "T4.7 — 90-Day Execution Roadmap" (Phase, Objective, Key Tasks, Deliverables) if the committee wants implementation detail; optional, not essential

### 11.5 Solution Evaluation
**Discuss (thinnest of all five, and this should be stated plainly):**
- Iteration 1 produced no deployed artifact to evaluate against real-world performance
- What can be "evaluated" is the **completeness and internal consistency of the design**: architecture, data governance, and AIRCS/AICF formulas are coherent and mutually consistent across three independent documents (System Architecture, Master Strategy, PIE) — itself a form of design-quality evidence
- The stated limitations (Master Strategy §20.1: dataset availability/quality, regulatory data inconsistency across municipalities, heuristic-only predictive sourcing at launch) function as this iteration's honest "evaluation" — a self-assessed readiness gap, not a test result
- This absence is itself meaningful: it justifies why Iteration 2 exists (to build and test what Iteration 1 only designed)

**Do NOT discuss:** any accuracy numbers, R², MAE, or test results — none exist yet (these first appear in Week 6's Ames prototype, R²≈0.95, which is Iteration 2)

**Figures:** none
**Tables:** none

---

## 12. DSRM Mapping Summary

| Repository material | Primary DSRM phase | Secondary phase (if any) | Reasoning |
|---|---|---|---|
| Week 1 market/PropTech research | Problem Investigation | — | Pure problem-space exploration |
| Week 2 tool teardown + valuation theory | Problem Investigation | Solution Design (informs AIRCS/AICF choices) | Establishes both the gap and the vocabulary later reused in design |
| System Architecture PDF | Solution Design | — | Full architecture proposal, no validation/implementation |
| Master Strategy Report | Solution Design | Design Validation (weight rationale, worked example) | Majority is design; the weight-rationale section and worked numerical example lean toward validation-by-reasoning |
| Execution Plan | Solution Implementation (organizational/planning level) | Solution Design (data pipeline step list) | It is a plan to implement, not implementation itself — classify carefully as *planning for implementation*, not implementation |
| PIE System Design | Solution Design | — | Analytical-framework specification, no code |

**Where material spans two phases, and why:** the Master Strategy's AIRCS weight rationale (§6.2) sits between Design and Validation because it both *proposes* weights and *defends* them against domain literature — a genuine boundary case. The Execution Plan sits between Design and Implementation because a roadmap is neither a pure design document nor an executed system; it is the **transition artifact**, which is exactly why it is the natural closing note for Iteration 1's "Solution Implementation" subsection (see §11.4).

---

## 13. Technical Depth Classification

| Topic | Classification | Reasoning |
|---|---|---|
| AIRCS formula, weights, scoring architecture | **Core** | Central analytical artifact of the whole project; formula persists across the entire corpus |
| AICF formula + worked example | **Core** | Directly paired with AIRCS; simple, illustrative, reused later |
| Three-platform ecosystem design (PropCheck/InspectOS/REZERVA) | **Core** | Structural backbone of the original vision |
| Data governance framework (5 principles) | **Core** | This is literally half of the iteration's title |
| Lakehouse (Bronze/Silver/Gold) data pipeline | **Core** | Recurs throughout the entire project's lifetime |
| Seller-first strategic rationale | **Recommended** | Important context, but the actual pivot execution belongs in Iteration 2 |
| 90-day execution roadmap | **Recommended** | Useful transition evidence into Iteration 2; not essential to belabor |
| PIE's 10 analytical modules (Deal Finder, ROI, Clustering, Digital Twin, etc.) | **Recommended** (mention as design intent) / **Optional** (deep individual treatment) | Several of these (Digital Twin, Stress-Test) never appear again in later evidence and may be dead-end ideas — worth one sentence each, not a subsection each |
| Predictive Sourcing Engine (signal list) | **Optional** | Only a bullet list exists; no architecture or data; mention briefly in Problem/Design, do not give it a figure |
| Business model / revenue scenarios (€2.3M–€23.1M projections) | **Exclude** from Chapter 4 | Commercial content, not engineering; consider only for an appendix or the company-context section of the Introduction (already partially covered there) |
| Team roles / Scrum-style responsibilities | **Exclude** or one sentence at most | Organizational, not technical; not dissertation-relevant beyond a footnote |
| Buyer Vault segmentation (Speed/Alpha/Yield/Portfolio buyers) | **Exclude** | Pure business/marketing construct with no technical content |
| Glossary terms from Master Strategy | **Optional** | Useful if the dissertation wants a formal glossary/abbreviations appendix (one already exists — `abbreviations.tex` — cross-check for overlap before duplicating) |

---

## 14. Iteration Boundary Analysis

**Where Iteration 1 starts:** the very first repository evidence of the project — Week 1, Day 1 (2/10/2026), general real-estate industry orientation.

**Where Iteration 1 ends:** the last **pre-implementation design document** — functionally, the PIE System Design specification. There is no dated evidence pinpointing an exact day this ends, but the boundary is architecturally unambiguous: Iteration 1 ends **the moment code is written and a dataset is touched**, which the evidence places at Week 6 (`Week_6.md`, Ames Housing dataset, working Gradient Boosting Regressor, first working AIRCS prototype).

**What belongs to Iteration 2 instead (explicitly, to prevent content leakage):**
- Week 6: PIE built on Ames Housing dataset; first working AIRCS/AICF/Deal Finder/ROI/Decision Engine code; Streamlit dashboard planned
- Week 7: FastAPI + React productization; Gemini chatbot; PDF export; still Ames data, buyer-oriented
- Week 8: seller-first pivot executed (not just proposed); "Fair Price" (FPI) language replaces "predicted price"; Rezerva alignment
- Weeks 9–11: AURA V4 on real Portugal data; stacked ensemble; the broken-XGBoost production crisis
- Week 12: V5/V6 transformation; fused 1.25M-row dataset; governance/leakage remediation (**the real "Governance Stabilization"**, as opposed to Iteration 1's paper governance framework)
- Week 13: V18 enterprise operating system
- All of `core_context.md`, `WEEK_*_CONTEXT.md`, the SCRUM PI, and the V17 notebook

**Why this boundary matters:** without it, a writer could easily blend the *designed* AIRCS (Iteration 1, untested, no data) with the *implemented* AIRCS (Iteration 2, running on Ames data with a simplified formula that "was later stabilized so it would not stay constant on single-row inputs" — a real bug fixed in Week 7). These are evidentially two different things and must be described as such: Iteration 1 gives the *intended* formula; Iteration 2 shows the *first real implementation problems* when that formula met actual single-row inference.

---

## 15. Repository Traceability Matrix

| Engineering Topic | Repository Folder | Report/Document | Week (if any) | Section | Target Dissertation Subsection |
|---|---|---|---|---|---|
| Real estate market orientation | `01_Research_And_Foundation_Report/` | `Week_1__Report.pdf` | Week 1, Days 1–4 | Days 1–4 sections | Problem Investigation |
| Portuguese PropTech tools & valuation theory | `01_Research_And_Foundation_Report/` | `Week_2_Report.pdf` | Week 2 | Full document | Problem Investigation / Solution Design |
| Full system architecture, 4 figures | `01_Research_And_Foundation_Report/` | `System_Architecture__Property_Intelligence_Infrastructure.pdf` | undated | §1–10 | Solution Design |
| AIRCS/AICF formulas, governance, business model | `01_Research_And_Foundation_Report/` | `MASTER_STRATEGY_REPORT_FINAL_VERSION.pdf` | undated | §1–21 + glossary | Solution Design / Design Validation |
| 90-day roadmap, pipeline steps, pilot design, team roles | `01_Research_And_Foundation_Report/` | `Execution_Plan_for_Portugal_Property_Intelligence_Infrastructure.pdf` | undated | §1–13 | Solution Implementation |
| 3-layer PIE architecture, 10 analytical modules | `01_Research_And_Foundation_Report/` | `Property_Intelligence_Engine_(PIE).pdf` | undated | §1–8 | Solution Design |
| — not yet read — | `01_Research_And_Foundation_Report/` | `3rd_Week.pdf` | Week 3 | unknown | likely Problem Investigation/Design — **verify before final draft** |
| — not yet read — | `01_Research_And_Foundation_Report/` | `Week 1-5.docx` | Weeks 1–5 | unknown | possibly consolidates Weeks 1–2 content already captured; **check for new material only** |
| — out of scope, do not use here — | `02_Product_1_...` | `Week_6.md` | Week 6 | full | Iteration 2 |
| — out of scope, do not use here — | `02_Product_1_...` | `WEEK_7_SUMMARIZED_CONTEXT.md` | Week 7 | full | Iteration 2 |

---

## 16. Writing Readiness Report

**Can Iteration 1 be written confidently now?**

**Yes, with one caveat.** The six documents read provide a complete, internally consistent, richly detailed picture of the conceptual/architectural foundation: market problem, competitive landscape, full system architecture (4 diagrams), AIRCS/AICF formulas with worked examples, governance framework, and a concrete execution roadmap. This is sufficient to write all five DSRM subsections at appropriate (and honestly variable) depth — Problem Investigation and Solution Design can be rich; Design Validation, Implementation, and Evaluation must be deliberately thin and self-aware about that thinness, which is itself a defensible academic point (a design iteration has design-only validation).

**What is still missing / should be checked before final drafting:**
1. `3rd_Week.pdf` (Week 3) — not yet opened. Likely continues the Week 1–2 research narrative; should be skimmed to confirm no new architectural or formula content that would change §3, §6, or §9 above.
2. `Week 1-5.docx` — not yet opened. Possibly a consolidated/duplicate version of Weeks 1–5; check once for any content not already captured in Week 1/Week 2 PDFs (e.g., Weeks 4–5 specifically, which have no dedicated PDF in this folder).
3. The exact **chronological placement** of the four undated design PDFs (System Architecture, Master Strategy, Execution Plan, PIE) relative to Weeks 3–5 remains inferred, not documented. If the dissertation requires calendar precision, this should be flagged as a stated limitation rather than invented.

**Recommendation:** proceed to draft Iteration 1 using this blueprint now; treat `3rd_Week.pdf` and `Week 1-5.docx` as a fast confirmatory pass (not a re-audit) before final submission, specifically checking for (a) any Week 4–5 content not yet seen, and (b) any date anchors for the four design PDFs.

---

## 17. Common Mistakes to Avoid When Writing Iteration 1

1. **Do not introduce Product 2 or Product 3** — they do not exist conceptually yet at this stage (first mention of an AI assistant is Week 9–11's "replace Gemini with open-source LLM" note, and Product 3/Intelligence Hub is far later).
2. **Do not mention any dataset version (V1/V2/Final, Cat1–Cat9)** — none exist yet; Chapter 3 already covers these correctly as later artifacts.
3. **Do not mention V4, V17, V18, or any notebook phase** — all post-date this iteration by a wide margin.
4. **Do not mention LightGBM, XGBoost, FT-Transformer, Qwen, the Ames Housing dataset, Streamlit, or Gemini** — all Iteration 2+ implementation details.
5. **Do not describe PropCheck/REZERVA/InspectOS as if they were built** — they were *designed*, not implemented, in this iteration. Use "was designed to," "was proposed to," not "the platform provides."
6. **Do not present the AIRCS worked example as a validated test** — it is a hand-worked illustration of the formula, not an empirical evaluation.
7. **Do not blend the Iteration-1 governance framework (paper design) with the Iteration-2 governance work (real leakage remediation)** — these are different in kind and must be described as such.
8. **Do not overstate Design Validation or Solution Implementation** — the honest, defensible position is that these two subsections are necessarily thin in Iteration 1, and that thinness is itself evidence supporting why Iteration 2 was needed.
9. **Do not include the business-model/revenue-projection content as if it were an engineering result** — keep commercial material out of the engineering narrative or confine it to one sentence of context.
10. **Do not invent exact calendar dates** for the four undated design PDFs — state plainly that their exact chronological position within Weeks 1–5 is not documented.

---

## 18. Dissertation Writing Recommendations

| Aspect | Recommendation | Reasoning |
|---|---|---|
| Length | 3–4 pages total for Iteration 1 (all 5 subsections combined) | Iteration 1 is genuinely thinner in implementation/validation than later iterations; padding it would misrepresent the evidence |
| Figures | 3 figures (4.2 Ecosystem Architecture, 4.3 AIRCS Scoring, 4.4 Governance Pipeline); Figure 4.1 (Problem Landscape) optional if page budget is tight | Three is enough to carry Solution Design without crowding a short iteration |
| Tables | 3–4 tables (T4.1 AIRCS weights, T4.2 score bands, T4.3 stack, T4.5 governance principles); T4.4 and T4.6 optional | Keep tables tightly bound to formulas/specs, not business content |
| Paragraph distribution | Problem Investigation: ~30% of the word count; Solution Design: ~50%; Design Validation: ~8%; Solution Implementation: ~8%; Solution Evaluation: ~4% | Mirrors the actual evidentiary weight — most of what exists is problem framing and design |
| Approximate word count per subsection | Problem Investigation ~350–450 words; Solution Design ~600–750 words; Design Validation ~120–180 words; Solution Implementation ~150–200 words; Solution Evaluation ~80–120 words | Keeps the thin subsections honestly thin rather than artificially inflated |
| Narrative vs. technical balance | Favor technical (formulas, tables, architecture) over narrative prose; use narrative only to connect Problem → Design | The source material is itself technical/specification-style; matching that register keeps the writing "natural" per the ghostwriting style already established |
| Concepts deserving a figure rather than text | AIRCS scoring aggregation (5→1), ecosystem data flow, governance-annotated pipeline | These are inherently structural/relational and are hard to convey in prose without becoming a list |
| Concepts deserving text only, no figure | Predictive Sourcing Engine (signal list only), FSBO/VISBO rationale, seller-first strategic reasoning | Thin evidence; a figure would visually overstate their maturity |

---

## Final Deliverable Statement

This blueprint is a comprehensive, repository-driven, DSRM-structured reference for writing Iteration 1 of Chapter 4. It identifies every engineering decision, architectural element, data-governance principle, AIRCS/AICF specification, and design-versus-implementation boundary documented in `01_Research_And_Foundation_Report/`, while explicitly excluding material that belongs to Iteration 2 and later. The central finding — that Iteration 1 is a pure design/strategy phase with no working code, no real dataset, and correspondingly thin Design Validation, Solution Implementation, and Solution Evaluation content — is the single most important constraint for writing this section honestly. Two files (`3rd_Week.pdf`, `Week 1-5.docx`) remain unread and should receive a short confirmatory pass before final drafting, per §16. With that caveat, this blueprint is sufficient to write Iteration 1 directly, without further repository-wide exploration.
