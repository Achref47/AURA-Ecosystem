# AURA Ecosystem — Master Engineering Reconstruction Report

**Role of this document:** authoritative, repository-derived technical reference used to write Chapter 4 (Iterative Development), Chapter 5 (Results & Findings), Discussion, Conclusion, and the defense.
**Source of truth:** the repository only. Where a claim is inference rather than documented fact, it is marked **[INTERPRETATION]**. Where documents disagree, the disagreement is stated explicitly **[CONFLICT]**. Where evidence is thin, it is marked **[WEAK EVIDENCE]**.
**Compiled from:** the LaTeX chapter sources (`introduction.tex`, `methodology.tex`, empty `ITERATIONS/results-findings/discussion`), the weekly context files (Week 6–13), `core_context.md`, `AURA_PRODUCT1_SCRUM_PROGRAM_INCREMENT.md`, `PRODUCT2_ITERATIONS.md`, `PRODUCT3_ITERATIONS.md`, `AURA Dataset Version Evolution Report.md`, `AURA_Deep_Feature_Audit.md`, and `AURA_V17_Production_final.ipynb`.

---

## 1. Repository Overview

### 1.1 Top-level layout

| Path | Role |
|---|---|
| `Aura Datasets/` | Three dataset generations: `Aura -Dataset -First Version`, `-Second Version`, `-Datasets -Final Version` (Dataset A / B / C Final) |
| `Aura-AI Platform -Product 1/` | **Product 1 — Core prediction engine / Seller Intelligence Platform.** `Version 1–4`, `Aura Platform Version 1/PIE`, `Aura Product 1 final Version/` (V17 exports + `docs/` governance set) |
| `Aura-AI Assistant-Product 2/` | **Product 2 — AI Assistant.** `Aura AI assistant/backend`, `Phases/` (Phase 6–9), `Runtime Phase 8/9`, `Rezervaa Files`, `Test` |
| `Aura-AI Intellignece Hub -Product 3/` | **Product 3 — Intelligence Hub.** `Intelligence Hub-backend` (api/, config/, ~207 `reports/`), `Intelligence Hub-frontend/src`, `.github` CI |
| `Capstone/` | Dissertation source: reports 01–06, LaTeX final report, `AURA_V17_Production_final.ipynb`, figures |

**Documented fact:** the ecosystem is three separately-built, independently-frozen products plus a shared, three-generation data layer. The products are *not* a single integrated runtime; they compose only conceptually (Product 3 explicitly declares itself standalone, not an integration layer for its siblings).

### 1.2 Company / problem framing (from `introduction.tex`)
- **AURA = Adaptive Unified Real Estate Intelligence Engine.** Built during a data-science capstone internship at **FAIRBANK**, a Lisbon PropTech incubator.
- FAIRBANK ecosystem (external to AURA): **InspectOS** (inspection/certification), **Rezerva** (off-market transactions), **HomeOS** (post-purchase compliance). AURA is positioned as the **intelligence layer** connecting them.
- Regulatory drivers cited: **Decreto-Lei n.º 10/2024** (buyer liability for undisclosed defects) and **EPBD Directive 2024/1275/EU** (mandatory energy upgrades).
- Problem: fragmented Portuguese property data, no unified MLS, information asymmetry, listing-price-only valuation. 8 research questions, 5 objectives (unified pipeline, explainable valuation, risk detection, decision support, scalable/GDPR-aware platform).

**[CONFLICT / naming]** `core_context.md` and early weekly files expand AURA as "Adaptive Unified Real Estate Intelligence **Architecture**" (SCRUM PI) and "…**Engine**" (core_context). The dissertation uses **Engine**. Adopt "Engine" as canonical; footnote the variant.

---

## 2. Chronological Timeline

Two clocks run in parallel and must not be conflated:
1. **Calendar clock** — weekly internship reports (Week 1–13).
2. **Model-version clock** — AURA V4 → V18/V19, defined inside the notebook.

| Phase | Evidence | What happened |
|---|---|---|
| **Weeks 1–5** | `01_Research_And_Foundation_Report` PDFs | Problem framing, PIE concept, ecosystem/architecture design, Master Strategy, seller-first direction. (PDFs not fully text-extracted — see §13.) |
| **Week 6** | `Week_6.md` | First working **PIE** on the **Ames Housing dataset** (simulated, US data). Gradient Boosting Regressor, MAE≈10k, R²≈0.95. Prototype AIRCS, AICF, Deal Finder, ROI, Investment Score, Decision Engine (BUY/HOLD/REJECT), explainability. |
| **Week 7** | `WEEK_7_SUMMARIZED_CONTEXT.md` | PIE productized: FastAPI `/predict` + `/chat`, React frontend, simulation page, **Gemini chatbot**, PDF export. Still Ames data, still **buyer/investor-oriented**. GradientBoostingRegressor final. R²≈0.88–0.89. |
| **Week 8** | `WEEK_8_SUMMARIZED_CONTEXT.md` | **Seller-first pivot.** Rezerva alignment. "Predicted price" → "Fair Price" (FPI) language. Endpoints `/valuate`, `/market-intelligence`, `/decision`, `/report`. Buyer flow (PropCheck) demoted to secondary. |
| **Weeks 9–11** | `WEEK_9_10_11_CONTEXT.md`, `core_context.md` | **AURA V4** production era: real Portugal data, stacked ensemble **LGBM+XGB+ET+RF→Ridge**, 204 engineered features, target `log1p(price)`. **Production crisis:** valuation collapse €250k→€85k; root cause a **broken `xgb_model.pkl`** (xgb≈0.83 vs 12.xx); `meta_learner.pkl` corrupted downstream. Strategic decision: replace Gemini with a local open-source LLM (Qwen). |
| **Week 12** | `WEEK12_CONTEXT.md` | **V4→V5→V6.** Fused **1.25M-row / 174-feature** panel (2019–2025, CAT1–CAT8, 0% missing). Hybrid valuation (bias correction + market anchor), temporal validation (train 2019–23 / val 24 / test 25), feature governance, uncertainty, sale-probability, TOM, decision engine. |
| **Week 13** | `WEEK13_CONTEXT.md` | **V18 Enterprise Operating System.** Unified runtime, API gateway, request router (standard/batch/shadow/canary/scenario), unified prediction contract, security/governance, caching, checkpoint recovery (~1.28 GB). "Architecture became more important than model performance." |
| **Notebook consolidation** | `AURA_V17_Production_final.ipynb` | 17-phase production notebook: FT-Transformer + LightGBM deep hybrid, V7 leakage autopsy, conformal uncertainty, live API/telemetry, ending with a **V19 Institutional AI OS** cell. |
| **Product-ization** | SCRUM PI, `PRODUCT2/3_ITERATIONS.md`, P3 `data/`, DuckDB | Three deployable products built and frozen on top of the notebook intelligence + final datasets. |

**[INTERPRETATION]** The weekly clock (≤ Week 13) and the version clock (V4→V18) overlap: V4 ≈ Weeks 9–11, V5/V6 ≈ Week 12, V18 ≈ Week 13. V7–V17 are notebook-internal refinements compressed into the same late period, not separate calendar weeks.

---

## 3. Dataset Evolution

Three generations (confirmed by `AURA_Deep_Feature_Audit.md` and `AURA Dataset Version Evolution Report.md`).

### 3.0 Pre-Portugal origin (Weeks 6–7)
**Documented fact:** the earliest engine used the **Ames Housing dataset** (`train.csv`, US), a simulated stand-in. Portugal data only entered at the V4 stage. This is the true zero-point of the data story and is easy to miss.

### 3.1 Version 1 — Prototype fusion
- File: `aura_master_dataset_Version 1.csv`, **152 features**.
- Character: heterogeneous, mixed schemas, over-extended joins, hidden temporal assumptions, very high missingness in many columns (publish/context/socio blocks 74–98% null). Contains `cal_sale_*`, `hpi_*`, `macro_*`, `socio_pordata_*`, `al_muni_*`.
- Outcome: proved feasibility (collect data, generate outputs) but **too fragile for commercial defense**. Listing price ≠ fair market value.

### 3.2 Version 2 — Fused, governed panel
- File: `aura__fused_dataset_Version 2.csv`, **174 features**, **1.25M rows, 2019–2025, 0% missing** (matches Week 12 "V5 data foundation").
- Adds: spatial morphology/ESG (`compactness`, `elongation_ratio`, `sustainability_index`, `esg_index`, `urban_pressure_score`), tourism (`beds`, `guests`, `tourism_capacity_score`, `tourism_pressure_index`, `occupancy_ratio`), volatility/macro (`macro_stress_score`, `shock_proxy`, `affordability_score`, `macro_regime`), and the later-frozen signals.
- Outcome: stable enough to behave like an institutional runtime.

### 3.3 Final Version — Domain separation (Dataset A / B / C)
The decisive pivot: **stop forcing one fused master; separate into bounded domains.**
- **Dataset A — Spatial:** `AURA_SPATIAL_MASTER_V6_FINAL.csv`, 41 features (OSM building morphology, ESG proxies, POI density, grid density). ~2.07M rows (Product 3 figure).
- **Dataset B — Market:** `AURA_MARKET_MASTER_V2.csv` (104 feat, district sale/rental €/m², transactions, BPSTAT interest rate, socio/macro) and `AURA_MARKET_MASTER_V3.csv` (80 feat, property-grain with `_cat1_row_id`, `cat2_*`, `cat3_*`, `cat4_*` prefixes). **~4.69M rows** (Product 2/3 backbone).
- **Dataset C — Tourism + Volatility:** `aura_cat6_tourism_aggregated.csv` (10 feat, municipality Airbnb aggregates), `aura_cat6_tourism_raw.csv` (78 feat, raw Airbnb 2026 scrape), `aura_cat7_volatility_backbone.csv` (9 feat, quarterly price volatility 2019–2032).
- Rule: **Cat6 (current tourism snapshot) and Cat7 (quarterly volatility time-series) stay separate; join only at query time when semantics require it.**

### 3.4 Data category taxonomy (Cat1–Cat9)
Reconstructed from Week 12 (CAT1–CAT8 named) + the V3 market master column prefixes + Dataset C filenames.

| Cat | Domain | Source (documented/inferred) | Role | Status |
|---|---|---|---|---|
| **Cat1** | Property structure | Listings (Idealista/CASAFARI/Imovirtual per core_context) | Core valuation inputs; `_cat1_row_id` in V3 | Active; **valuation layer, not forecasting** (V2 correction) |
| **Cat1.2** | Property sub-layer | — | Named in prompt; **[WEAK EVIDENCE]** no explicit definition found | Ambiguous |
| **Cat2** | Market truth / HPI | INE house price index | Price index, momentum, liquidity proxies | **Largely deprecated/empty** — all `cat2_*` columns 100% null in V3 market master [CONFLICT below] |
| **Cat3** | Macro / rates | Banco de Portugal **BPstat** (Euribor / new-business loan rate) | Interest-rate context | Active but sparse (37.5% missing) |
| **Cat4** | Socio-economic | **PORDATA** (population, unemployment, immigration, construction) | Macro demand/supply context | Active but coarse (annual, 75% missing at quarter grain) |
| **Cat5** | Spatial intelligence | **OpenStreetMap** morphology + POI | Location/urban intelligence → Dataset A | Active; added in V2 |
| **Cat6** | Tourism | **Airbnb** scrape (2026) | Short-term-rental pressure | Active → Dataset C |
| **Cat7** | Volatility | Price-per-m² quarterly series | Market volatility/regime | Active → Dataset C, **kept separate from Cat6** |
| **Cat8** | Accessibility | POI/road distance (in V2) | Accessibility scoring | Named Week 12; folded into spatial [WEAK EVIDENCE as standalone] |
| **Cat9** | — | — | Named in prompt only | **[WEAK EVIDENCE]** no definition found; do not assert |

**[CONFLICT]** Cat2 (HPI/market-index block) appears fully populated in V1/V2 but is **100% NULL** in `AURA_MARKET_MASTER_V3.csv` (`cat2_hpi_value`, `cat2_price_sqm_proxy`, etc. all empty). Interpretation: the HPI block was superseded by direct district sale/rental price series in Dataset B and left as dead schema. Confirm before writing Cat2 as "active."

**[CONFLICT]** The five **frozen signals** — `tourism_pressure_index`, `macro_stress_score`, `seller_urgency_score`, `shock_proxy`, `investor_risk_score` — **physically exist with values** in `aura__fused_dataset_Version 2.csv` (feature audit), yet Products 2 & 3 treat them as permanently unrecoverable because their **derivation formulas were lost**. Correct framing: the columns survived; the provenance did not. Never invent formulas; never claim the data never existed.

---

## 4. Architecture Evolution

### 4.1 Ecosystem-level shape (final)
```
                 ┌───────────────── Final Data Layer ─────────────────┐
                 │  Dataset A (Spatial) · B (Market) · C (Tourism/Vol) │
                 └───────────────┬─────────────────┬──────────────────┘
                                 │                 │
        ┌────────────────────────┘                 └───────────────┐
        ▼                                                          ▼
 Product 1 — Core Engine                                  Product 3 — Intelligence Hub
 (V17 predictive runtime,                                 (deterministic executive
  Dual-Plane, FastAPI)                                     dashboard, no ML/LLM)
        │
        ▼
 Product 2 — AI Assistant
 (DuckDB 4.69M rows + local Qwen LLM)
```

### 4.2 Product 1 internal architecture — Dual-Plane (ADR-009)
**Documented fact (SCRUM PI):** Product 1 formally separates two planes, composed only at the presentation layer; **semantic fusion prohibited**.
- **Plane 1 — Predictive Intelligence:** the frozen V17 runtime (valuation, fair value, confidence, uncertainty, liquidity, P(sale), TOM, strategy, explainability). Frozen runtime + feature contract; only subsystem allowed to produce model-derived decisions.
- **Plane 2 — Contextual Intelligence:** read-only domain services over the final datasets (spatial, market, tourism, volatility, municipality). Never contributes features to prediction.

### 4.3 V17 notebook architecture (master technical reference)
Phase pipeline (from notebook markdown cells 0–19):
```
Raw Data → Feature Governance (V7 strict) → Deep Hybrid Layer (FT-Transformer + LGBM[+XGB+CatBoost])
→ Latent Representation (embeddings + retrieval + Incremental PCA) → Ensemble Meta-Learner
→ Bias Correction (learned α*) → Fair Value Engine (constrained Ridge, w≥0, Σw=1)
→ Uncertainty (quantile + conformal calibration) → Market Liquidity (P_sell + TOM)
→ Strategic Decision (expected-value optimization) → SHAP Explainability
→ Scenario Simulation (Monte Carlo + macro stress) → Production Inference
→ Drift Monitoring (PSI) + Telemetry → Continuous Learning → Enterprise OS
```
17 markdown phase cells + 26 code cells; final cell declares **V19 Institutional AI Operating System** (retrieval-augmented, governance-aware, memory-driven).

### 4.4 Product 2 architecture
Semantic guards → intent router (accent-folded, precedence overrides) → planner (locked intents) → reasoning graph (skipped for chat/comparison/sql) → handlers (SQL / deterministic comparison / forecast) → explanation engine (deterministic for ranking/comparison, LLM for general SQL) → memory manager. Backbone: read-only DuckDB `AURA_ENTERPRISE.duckdb` (~4.69M rows, 30 cols) with `aura_data_bridge` view over MARKET_MASTER, ACCOMMODATION_REGISTRY, TOURISM_LAYER_AGG, VOLATILITY_LAYER, SPATIAL_MASTER, CAT2_ENHANCED, HICP. Model: qwen2.5:7b-instruct default; qwen3:4b fast mode with fallback.

### 4.5 Product 3 architecture
Layered: React 18/TS/Vite/Zustand frontend → FastAPI thin routers (Pydantic, correlation IDs) → service layer (`ExecutiveSummaryService` → `AuraOrchestrator` → Market/Tourism/Volatility/Spatial services + Portfolio/Diversification/Matcher/Benchmark/Strategy/Decision/Opportunity/Alert) → `config/scoring_registry.py` + `config/scoring_config.py` governance → `data_loader.py` (`@lru_cache`) + JSON `PortfolioRepository` behind `PortfolioStore` Protocol. **No ML/LLM in scoring path** — aggregation, not fusion.

---

## 5. Product 1 Evolution (Core Engine / Seller Intelligence Platform)

### 5.1 Purpose
Predictive core of AURA: transform property attributes into fair value, confidence, liquidity, strategy, and explanation. Evolved from "what is my property worth?" to "what should I do next?" (seller copilot).

### 5.2 Version history (notebook table, cell 19)
| Version | Evolution | Maturity |
|---|---|---|
| V4 | Initial predictive engine (RF, XGBoost, feature engineering, baseline regression) | Prototype |
| V5 | Ensemble + governance foundations; leakage control, temporal-safe validation, correlation governance | Advanced Prototype |
| V6 | Institutional fair-value + explainability; economic anchors, seller intelligence | Research System |
| V7 | Production-oriented; rolling CV, LGBM+XGB+CatBoost, decision optimization, risk scoring | Early Production |
| V8 | FT-Transformer latent ecosystem; embeddings, Incremental PCA, retrieval, hybrid ensembles | Institutional AI Platform |
| V9 | Market liquidity; sale probability + TOM, overpricing elasticity | Enterprise Market Intelligence |
| V10 | Strategic seller optimization; expected-value, strategic ranking | Strategic Decision Platform |
| V11 | Enterprise explainability; SHAP, ensemble attribution, uncertainty explainability | Explainable Enterprise AI |
| V12 | Scenario/macro; Monte Carlo, macro stress, liquidity contagion | Scenario Intelligence |
| V13 | Production inference; routing, retrieval inference, prediction contracts | Production AI Infrastructure |
| V14 | Drift/deployment governance; PSI, telemetry | Deployment Governance |
| V15 | Continuous learning/MLOps; registry, shadow, canary, rollback, feature store | Enterprise MLOps |
| V18 | Unified enterprise OS; runtime, API gateway, orchestration, caching, queues | Commercial AI OS |

**[CONFLICT]** Notebook is titled **V17** but its own history table skips V16/V17 (V15 → V18) and its final cell describes **V19**. Weekly file calls the enterprise OS **V18**. Treat "V17/V18/V19" as overlapping labels for the same late-stage runtime; define one canonical scheme in the dissertation.

### 5.3 Models / pipeline
- **V4 stack:** LGBM(1500 est, lr 0.025, depth 7, 50 leaves) + XGB(1500, lr 0.025, depth 6) + RF(600, depth 18) + ExtraTrees(600, depth 18) → Ridge(α=0.5) meta; RobustScaler(25–75). Target `LogPrice = log1p(price)`; `fair_price = expm1(pred)`. 204 engineered features.
- **V7+ hybrid:** `P_model = 0.5·FT-Transformer + 0.5·LightGBM`; asymmetric loss penalizing overpricing more than underpricing; bias correction ε̂; constrained-Ridge fair value; conformal uncertainty; logistic P_sell; TOM; EV decision engine.

### 5.4 Deployment / exports
`Aura Product 1 final Version/Aura Version 17 exports and models/`: phase configs (phase6_bias, phase9/10, v14_scenario), `aura_v15_production/artifact_registry.json` + `system_metadata.json`, `aura_v17_elite/` (deployment_config, model_fingerprints, system_health, alerts), catboost_info. Governance docs under `docs/`: ARCHITECTURE, DECISION_LOG, RISK/ASSUMPTION/DEPENDENCY registers, SPRINT_0–6 validations, FREEZE_PACKAGE, MODERNIZATION_REPORT, CANONICAL_IDENTITY. (These `docs/` and JSON configs are **not yet fully read** — see §13.)

### 5.5 UI evolution (SCRUM PI Sprints 0–7)
0 Foundation verification → 1 Intelligence surface expansion → 2 Seller Decision Center → 3 Explainability & Trust (SHAP dashboard) → 4 Scenario & Simulation Studio → 5 Market Intelligence Platform → 6 Enterprise Seller Experience (PDF/report) → 7 Freeze Excellence.

### 5.6 Strengths / weaknesses
**Strengths:** validated temporal-safe models, dual-plane separation, explainability, frozen reproducible runtime, recovery infrastructure. **Weaknesses:** heavy runtime (~1.28 GB checkpoint), notebook-origin fragility mitigated by recovery, contextual intelligence still read-only projections, much intelligence historically hidden behind a legacy prediction UI.

---

## 6. Product 2 Evolution (AI Assistant)

### 6.1 Purpose
Natural-language interface over the 4.69M-row DuckDB analytical dataset; deterministic SQL retrieval, forecasting, grounded comparison, honest-failure, educational "General Background."

### 6.2 Iteration history (13 iterations, `PRODUCT2_ITERATIONS.md`)
- **Iter 0** baseline (keyword router, multi-agent graph, DuckDB, three model modes; hallucinated).
- **Iter 1** frozen-signal guard (deterministic decline).
- **Iter 2** monitoring honest-failure (no false "all clear").
- **Iter 3** forecast grounding rules + comparison schema fix (composite score from `price_per_sqm`, `occupancy_ratio`, `demand_pressure_score`).
- **Iter 4** deterministic ranking narrative + routing precedence overrides + planner intent lock.
- **Iter 5** position-based entity extraction + >2-entity honest decline; placeholder removal.
- **Iter 6** test-infra repair (VectorStore `is_available`; 360/0/91).
- **Iter 7** Portuguese routing (accent-fold + structural early-return fix), meta-explanation (`_aura_meta_answer`), fast→standard SQL fallback.
- **Iter 8** session answer-memory (`_serve_followup`, no persistence to avoid cross-session bleed).
- **Iter 9** latency profiling — proved **>99.5% latency = local 7B inference**; comparison 9.2s→0.7s; graph skipped for chat/comparison.
- **Iter 10** 200-question battery: 198/200 first pass; Q23 planner reroute + Q140 COUNT fabrication fixed.
- **Iter 11–13** UX polish, General Knowledge mode, Option B educational extension → **freeze** (360/0/91, 0 fabrications, <0.35s backend overhead).

### 6.3 Backend phases (source tree)
Phase 6 (temporal): `forecaster.py`, `temporal_agent.py`, `trend_analyzer.py`, `volatility_engine.py`, `cycle_detector.py`, `orchestrator.py`. Phase 7–8 (spatial/investment): `hotspot_ranker.py`, `investment_scorer.py`, `neighbor_influence.py`, `regional_momentum.py`, `spatial_trend_fusion.py`. Phase 9: `orchestrator_v2.py`. Runtime Phase 8/9 snapshots preserve `llm.py` + `tools.py`. Model benchmark study (`Technical_Integration_Analysis…7B13B.pdf`) chose the 7B default.

### 6.4 Cross-cutting principle
**Determinism replaces LLM wherever fabrication is possible** (ranking narrative, comparison, confidence note, follow-up serving, meta-explanation, frozen-signal decline, GK/OOS formatting).

---

## 7. Product 3 Evolution (Intelligence Hub)

### 7.1 Purpose
Deterministic, dataset-first executive decision suite over Datasets A/B/C: portfolio health, opportunity discovery, benchmarking, comparison, strategy simulation, alerts, decision memory. **Honest intelligence** — every displayed number is a real dataset aggregation; no ML/LLM/fabrication in scoring.

### 7.2 Iteration history (9 iterations, `PRODUCT3_ITERATIONS.md`)
1 Foundational platform (FastAPI+Polars, `AuraOrchestrator`, `ScoringRegistry`, `@lru_cache`, JSON repo, 12 pages) → 2 Production readiness (tests, CI, `/health/details`; "Strong Production Candidate" 88/100) → 3 UI polish/defect fixes → 4 Defense audit (`tsc -b` authoritative; ~20 TS errors) → 5 Read-only CTO audit (Eng 7.5, Arch 8.0; classified backlog) → 6 Master improvement (7 fixes, centralized `scoring_config.py`, 404/422 contracts, correlation IDs; BE 62→66) → 7 Command Palette ⌘K + Focus Mode + skeletons → 8 Today's Brief executive synthesis hero → 9 Honest live alert bell → **freeze at diminishing returns**.

### 7.3 Services / repositories / APIs (source tree)
`api/router.py`, `api/schemas.py`, `api/dependencies.py`, `config/{scoring_registry,scoring_config,dataset_registry}.py`; frontend `src/{pages,components/{layout,ui},hooks,services,store,test}`. Endpoints: `/health`, `/health/details`, `/api/domain/*`, `/api/portfolio`, `/watchlist`, `/api/dashboard`, `/brief`, `/opportunities`, `/compare`, `/benchmark`. ~207 design reports under `reports/` (frameworks for daily brief, comparison, alerts, confidence, governance).

### 7.4 Signature experiences
Command Workspace (⌘K), Today's Brief (executive synthesis hero), Focus/Presentation Mode, per-signal DrilldownModal (source/confidence/evidence/recommendation).

### 7.5 Validation at freeze
66 backend (4 documented xfail) + 17 frontend tests; CI; strict `tsc -b`; real-app 404/422/correlation-id verification; persona scoring proven bit-identical after refactor.

---

## 8. Engineering Decisions (Problem → Alternatives → Choice → Trade-off → Impact)

| # | Decision | Problem | Alternatives | Chosen | Trade-off | Impact |
|---|---|---|---|---|---|---|
| D1 | Rebuild XGBoost + meta learner | Valuation collapse €250k→€85k; xgb artifact broken | Patch inference; retrain whole stack | Rebuild `xgb_model.pkl` + `meta_learner.pkl`; enforce `pd.DataFrame([...])[features]` + fixed order [lgbm,xgb,et,rf] | Rework of artifacts | Restored production valuation; motivated governance |
| D2 | Fair-value grounding (not listing price) | Listing ≠ real value | Keep listing target; post-hoc adjust | Bias correction + market anchor + AICF | Less "market-raw" | Economic realism |
| D3 | Strict feature governance | R²≈0.94–0.998 = leakage (OOF `oof_muni_price_mean`, same-slice anchors) | Accept high R²; drop suspicious features only | Ban OOF from primary features; training-only anchors | Lower headline R² | Trustworthy metrics |
| D4 | Temporal validation | Random split unsafe (geo autocorrelation) | Random split; k-fold | Rolling CV (train 19–23/val 24/test 25) | Fewer train rows per fold | Realistic generalization |
| D5 | Deep hybrid model | LGBM-only under-captures interactions | Keep LGBM; pure transformer | 0.5·FT-Transformer + 0.5·LGBM | Complexity, GPU cost | Latent + tree strengths |
| D6 | Conformal uncertainty | V6 coverage 38% (target 75–85%) | Wider fixed intervals; assume Gaussian | Quantile models + conformal calibration | Extra calibration step | Guaranteed empirical coverage |
| D7 | Learned P_sell | V6 sale model constant | Assume linear | Logistic σ(overpricing, demand, stress, liquidity) | Needs labels | Meaningful liquidity |
| D8 | Local Qwen over Gemini | External API dependency, 404/429 quota | Stay on Gemini; other closed APIs | Local qwen2.5:7b (benchmarked) | Local inference latency | Owned, offline assistant |
| D9 | Domain separation (not fusion) | Fused master blurred semantics/time scales | Single master dataset | Dataset A/B/C; Cat6≠Cat7 | Query-time joins needed | Explainability, scalability |
| D10 | Dual-Plane (ADR-009) | Context risks polluting frozen models | Merge context into features | Separate predictive/contextual planes | Compose only at UI | Scientific validity preserved |
| D11 | Determinism over LLM (P2) | LLM fabrication/inconsistency | Prompt-tune | Deterministic code paths + guards | Less "eloquent" | 0 fabrications, testable |
| D12 | No ML/LLM in scoring (P3) | Opaque analytics untrustworthy | ML regression; LLM narratives | Rule-based governed aggregation | No learned nuance | Reproducible, auditable |
| D13 | Honest failure everywhere | Fabricated/missing signals | Estimate; hide feature | Explicit decline + warnings | Feature appears absent | Trust |
| D14 | Freeze at diminishing returns | Endless polish risk | Keep polishing | Stop when no tell reduces demo confidence | Deferred niceties | Release discipline |

---

## 9. Major Architectural Pivots

1. **Ames (US, simulated) → Portugal real data** (Week 7→9).
2. **Buyer/investor → seller-first** (Week 8; reinforced by supervision).
3. **Listing price → fair value grounding** (V4→V5/V6).
4. **Leakage → governance + temporal-safe validation** (V6→V7).
5. **Single model → deep hybrid + latent/retrieval** (V7→V8).
6. **Gemini → local Qwen** (Week 12).
7. **Monolithic fusion → domain separation (A/B/C)** (final data layer).
8. **Notebook → enterprise operating system** (Week 13 / V18).
9. **Prediction ≠ context (Dual-Plane, ADR-009)** (Product 1 program).
10. **Capability → honesty** (Products 2 & 3 tenet).

---

## 10. Version History (consolidated)

- **PIE prototype (Wk 6–8):** Ames → Portugal-intent; buyer→seller pivot; Gemini chatbot; FastAPI+React.
- **V4 (Wk 9–11):** stacked ensemble; broken-XGB crisis; 204 features; log1p target.
- **V5 (Wk 12):** ensemble + governance + fused 1.25M/174-feature panel.
- **V6:** fair-value intelligence + explainability (uncertainty coverage still weak: 38%).
- **V7:** temporal-safe, leakage removed, decision engine, CatBoost added.
- **V8:** FT-Transformer latent ecosystem.
- **V9–V12:** liquidity (P_sell/TOM), strategy EV, SHAP explainability, Monte-Carlo scenarios.
- **V13–V15:** production inference, drift/telemetry, MLOps (registry/shadow/canary/rollback).
- **V17/V18/V19 (Wk 13):** unified enterprise OS / institutional AI OS; checkpoint recovery.
- **Products:** P1 (SCRUM PI, dual-plane, frozen), P2 (13 iterations, frozen), P3 (9 iterations, frozen).

---

## 11. Technical Lessons Learned

- Validation > accuracy; leakage destroys realism (a high R² was the symptom, not the achievement).
- Determinism + governance + honest failure can substitute for opaque ML where explainability is paramount.
- A correct layered architecture pays compounding dividends (P3: 9 iterations, no rewrite).
- Separation of concerns (domain datasets; dual planes) beats convenient fusion.
- Notebook state loss is an existential risk; checkpoint recovery is essential for enterprise credibility.
- Small "tells" (fake notification dot) disproportionately erode trust; making them honest is high-leverage.
- Knowing when to stop (diminishing returns) is itself an engineering result.

---

## 12. Deprecated / Replaced Components

- **Ames Housing dataset** — replaced by Portugal data.
- **Broken `xgb_model.pkl` / `meta_learner.pkl`** — rebuilt/quarantined (memory: xgb quarantined, sklearn pinned 1.7.2, LightGBM-primary validated).
- **OOF target-leaking features** (`oof_muni_price_mean`) — banned from primary features.
- **Random train/test split** — replaced by rolling temporal CV.
- **Listing price as target/value** — replaced by fair-value grounding.
- **Gemini chatbot** — replaced by local Qwen.
- **Monolithic fused master dataset** — replaced by Dataset A/B/C.
- **Cat2 HPI block** — superseded by direct Dataset B price series (100% null in V3). [CONFLICT — verify]
- **Five frozen signals** — permanently unrecoverable; declined, never fabricated.
- **91 skipped P2 tests** bound to deleted `aura_v5_fused_dataset.csv` — obsolete removal candidates.
- **P3 dormant services** (`SpatialBridge`, `WatchlistService`, `PortfolioAuditService`) — present, tested, not wired; documented not deleted.

---

## 13. Remaining Ambiguities & Unread Evidence (honesty section)

- **Version scheme** V17/V18/V19 overlapping — must be canonicalized.
- **Cat1.2, Cat8 (standalone), Cat9** — named in the task prompt but **no clear repository definition**; do not assert. Cat9 especially has no evidence.
- **Cat2 status** — populated in V1/V2, null in V3; "deprecated vs. relocated" needs one-line confirmation.
- **Frozen-signal paradox** — columns exist, formulas lost; frame precisely.
- **Row/feature counts differ by dataset**, not by contradiction: 1.25M (V2 panel), 4.69M (DuckDB market backbone), ~2.07M (spatial). State which is which.
- **R² figures (0.88–0.998)** are pre-governance/leaky — **do not report as results**; extract post-governance temporal-test metrics from notebook code cells before writing Chapter 5.
- **Not yet fully read** (acceptable for now, but note before deep Chapter-5 metric claims): Product 1 `docs/` governance set (DECISION_LOG, ARCHITECTURE, SPRINT_*_VALIDATION, FREEZE_PACKAGE, MODERNIZATION_REPORT), the V17 export JSON configs, the ~207 Product 3 `reports/`, Product 2 backend source bodies, the Week 1–8 PDFs, the V4/V5 dataset PDFs, and `06_Company_Reports` (FairBank, proposal, strategic meeting). None are expected to overturn the reconstruction; they add detail.
- **Iteration dating** — Product 2/3 iterations are logically ordered, not calendar-dated; don't invent dates.
- **Ecosystem integration** is conceptual (presentation-layer), not a single runtime; Product 3 is explicitly standalone.

---

## 14. Recommended Dissertation Structure (Ch4 vs Ch5 mapping)

**Chapter 4 — Iterative Development (the story of *how*):**
- Ecosystem arc (Ames→Portugal, buyer→seller, notebook→OS).
- Product 1 version journey V4→V18 with the two set-pieces: the broken-XGBoost crisis and the V6–V7 leakage autopsy; the Dual-Plane pivot.
- Dataset iterations V1→V2→Final (monolithic→domain separation).
- Product 2 iterations 0–13 (honesty/grounding/determinism).
- Product 3 iterations 1–9 (foundational→premium→diminishing returns).
- Deprecated/replaced ideas.
- **Rationale:** Chapter 4 is decision- and change-driven; it must show reasoning, not final state.

**Chapter 5 — Results & Findings (the *what* and *how well*):**
- Final ecosystem architecture (3 products + dual-plane + A/B/C).
- Final model stack + **post-governance temporal-test metrics**; conformal coverage restored to 75–85% (from 38%).
- Per-product validation: P2 198/200 + 360/0/91 + <0.35s backend; P3 66 BE + 17 FE + CI + audits 7.5/8.0; P1 sprint validations + freeze package.
- Governance/honest-failure/explainability findings.
- Limitations (frozen signals, aggregated spatial data, commercial data not integrated, single-worker cache, stubbed auth).
- **Rationale:** Chapter 5 presents the delivered system and evidence; it must not reuse leaky R².

Maps onto `methodology.tex` DSRM phases: Demonstration/Evaluation → Chapter 5; Design/Development iterations → Chapter 4.

---

## 15. Recommended Iteration Structure (for the empty `ITERATIONS.tex`)

The chapter file already fixes **five iterations** with the DSRM sub-cycle (Problem Investigation / Solution Design / Design Validation / Solution Implementation / Solution Evaluation). Evidence supports these boundaries:

| Iteration (as titled in `ITERATIONS.tex`) | Real engineering content | Products | Data | Architecture | Validation |
|---|---|---|---|---|---|
| **1 — Foundation, Core Concept, Data Layer, Governance Stabilization** | PIE→V4→V5/V6→V7; leakage autopsy; temporal validation; V1→V2→domain-separated data; feature governance | P1 core | V1→V2→A/B/C | ensemble→hybrid; governance | temporal CV; leakage checks |
| **2 — Seller Intelligence Development** | Seller-first pivot; fair value, liquidity, TOM, decision engine, scenario studio; SCRUM Sprints 1–5 | P1 UI/services | Dataset B/A | dual-plane predictive surfaces | sprint validations |
| **3 — AI Assistant Integration & Seller Intelligence Enhancement** | Product 2 build: DuckDB, Qwen, guards, grounding, routing, memory | P2 | DuckDB 4.69M | semantic guards + deterministic engines | 200-question battery, 360/0/91 |
| **4 — Intelligence Hub Development & User Interaction Layer** | Product 3 build: orchestrator, governance registry, dashboards, command workspace, Today's Brief | P3 | A/B/C | layered deterministic hub | 66 BE + 17 FE, CI, audits |
| **5 — Final Ecosystem Consolidation** | Enterprise OS unification (V18), freezes across all three products, dual-plane composition, dissertation/defense packaging | All | Final | enterprise runtime + presentation composition | freeze packages, diminishing-returns |

**[INTERPRETATION]** These five map cleanly onto the real evidence; the dataset/governance work is deliberately folded into Iteration 1 (matching the file's title) rather than given its own iteration.

---

## 16. Evidence References

| Claim area | Primary evidence file(s) |
|---|---|
| Company/problem/objectives/RQs | `…/Section Files/introduction.tex` |
| DSRM, data versions, compute, validation | `…/Section Files/methodology.tex` |
| Empty chapters to fill | `…/Section Files/{ITERATIONS,results-findings,discussion}.tex` |
| PIE origin, Ames, buyer→seller | `Week_6.md`, `WEEK_7_SUMMARIZED_CONTEXT.md`, `WEEK_8_SUMMARIZED_CONTEXT.md` |
| V4 crisis, ensemble, 204 features | `WEEK_9_10_11_CONTEXT.md`, `core_context.md` |
| V5/V6 transformation | `WEEK12_CONTEXT.md` |
| V18 enterprise OS | `WEEK13_CONTEXT.md` |
| Dual-Plane / ADR-009 / sprints | `AURA_PRODUCT1_SCRUM_PROGRAM_INCREMENT.md` |
| Notebook version tables, phases, autopsy | `AURA_V17_Production_final.ipynb` (md cells 0, 3, 5–9, 19) |
| Dataset generations & categories | `AURA_Deep_Feature_Audit.md`, `AURA Dataset Version Evolution Report.md` |
| Product 2 iterations | `PRODUCT2_ITERATIONS.md` |
| Product 3 iterations | `PRODUCT3_ITERATIONS.md` |
| Product source trees | `Aura-AI Assistant-Product 2/…`, `Aura-AI Intellignece Hub -Product 3/…`, `Aura Product 1 final Version/docs/…` |

---

*End of master engineering reconstruction. Update the [CONFLICT]/[WEAK EVIDENCE]/§13 items as the remaining `docs/`, `reports/`, PDFs, and notebook code cells are read; none is expected to overturn this reconstruction.*
