# WEEK 9 CONTEXT — AURA / Portugal Real Estate Intelligence

**Date:** 2026-04-13  
**Project:** AURA V4 — Adaptive Unified Real Estate Intelligence Engine  
**Scope:** Week 9 production rebuild using the fused Portugal master dataset

---

## 1. Project Overview

AURA has moved from an Ames-based prototype into a **Portugal-native production intelligence system**. The goal is to turn real estate data into valuation, risk, market, ESG, regulatory, and seller-decision intelligence.

The system now focuses on the Portuguese market and uses the fused master dataset as the source of truth. The prior Ames prototype is preserved only as historical context and comparison material.

Primary problem solved: **real-estate information asymmetry**. The platform helps users understand fair value, market pressure, liquidity, risk, and the best action to take.

Target users: sellers, buyers, investors, agents, and supervisors evaluating product readiness.

Core components in the current architecture:
- **AURA**: decision intelligence layer
- **DTATA**: 7-layer data spine
- **Seller Decision Engine**: SELL_NOW / WAIT / REDUCE_PRICE / HOLD / INVEST
- **Governance layer**: confidence, completeness, human review
- **Market intelligence layer**: district, macro, calibration, ESG, regulatory context

---

## 2. System Architecture

Current structure:

**Raw source datasets**
→ inspection / cleanup  
→ fused Portugal master dataset  
→ feature engineering  
→ model training  
→ validation  
→ seller decision engine  
→ explainability + governance  
→ exports / dashboards / reports

Important architecture notes:
- The system is now **decision-driven**, not prediction-only.
- It uses a **multi-layer data fusion design**:
  - Listings
  - Calibration
  - HPI
  - Macro
  - Socioeconomic
  - ESG / spatial
  - Regulatory / RNAL
- The notebook is treated as a **product-grade intelligence engine**, not a toy model.

Design patterns used:
- pipeline architecture
- modular feature engineering
- data-centric design
- explainable decision system
- confidence-aware governance

---

## 3. Technology Stack

Current week-9 implementation uses:
- **Python**
- **pandas / numpy**
- **scikit-learn**
- **LightGBM**
- **XGBoost**
- **ExtraTrees**
- **RandomForest**
- **Ridge meta-learner**
- **matplotlib / seaborn**
- **joblib**

The work is done locally in notebook form and produces artifact files such as:
- cleaned datasets
- inspection reports
- quality reports
- model artifacts
- comparative documentation

Future architecture direction discussed:
- FastAPI for inference
- React dashboard
- governance / audit layer
- productization around Portugal intelligence

---

## 4. Full Project Structure

At the end of week 9, the working folder contains:

- `AURA_V4_Production.ipynb` — final notebook build
- `aura_master_dataset.csv` — fused Portugal dataset
- `aura_master_dataset_cleaned_archive.csv`
- `aura_master_dataset_cleaned_model_ready.csv`
- `column_quality_report.csv`
- `column_profile.csv`
- `numeric_summary.csv`
- `object_column_profile.csv`
- `missing_summary.csv`
- `dataset_inspection_report.json`
- category source files for lineage:
  - category1
  - category1.2
  - category2
  - category3
  - category4
  - category5
  - category6
- `Readme.md`
- `AURA_V1_vs_V4_Comparative_Report.docx`
- `AURA_DATA_Layer_Final_Report.docx`
- `models/`
- `outputs/`

Role of each:
- **data files**: training and traceability
- **reports**: supervisor review and documentation
- **models**: trained artifacts
- **notebook**: full technical pipeline
- **source category files**: lineage and reproducibility

---

## 5. API Design (Planned / Not Yet Fully Implemented)

The notebook is currently focused on analytics and production-style inference in Python, not a deployed API. Planned endpoints discussed conceptually:

- `POST /predict`
  - purpose: return fair price + decision + confidence
- `POST /evaluate-property`
  - purpose: evaluate risk / market position / opportunity
- `POST /investment-decision`
  - purpose: support investor-side decisions
- `GET /aircs-score`
  - purpose: expose risk/condition scoring

Status:
- **PLANNED / IN PROGRESS**
- not yet a live deployed backend in this week’s deliverable

---

## 6. Database Design

Current state:
- CSV-based dataset
- no live relational database yet

Future logical schema discussed:
- `properties`
- `inspections`
- `transactions`
- `features`

Suggested key strategy:
- `property_id` as main foreign key
- separate feature and transaction tables
- indexes on district, city, price, dates, and registry identifiers

Status:
- **planned architecture**
- not yet implemented as a database

---

## 7. Core Features — Logic & Implementation

### AIRCS / Risk Layer
Purpose:
- measure risk / condition / market exposure

Current Portugal version includes:
- energy proxy
- age proxy
- district tier
- macro affordability
- ESG score
- regulatory pressure
- momentum

### Valuation Layer
Purpose:
- estimate fair price
- produce recommended price and listing range

Uses:
- stacked ensemble
- robust scaling
- final features lock
- Portugal-native feature set

### Decision Engine
Purpose:
- convert valuation and market signals into seller action

Outputs:
- SELL_NOW
- WAIT
- REDUCE_PRICE
- HOLD
- INVEST

### Explainability Layer
Purpose:
- produce human-readable reasoning
- show signal contributions
- support supervisor review

### Governance Layer
Purpose:
- confidence scoring
- layer completeness
- source reliability
- human review flag
- GDPR-aware exclusion

---

## 8. Final Code State (Latest Working Version)

Final working week-9 state includes:

- Portugal feature engineering using the real fused dataset
- area features
- temporal features
- quality / energy features
- location prestige features
- calibration and macro features
- socio features
- ESG and regulatory features
- confidence and governance features
- model training and validation
- stacked ensemble
- seller report generation
- batch and single inference
- artifact export

Important performance summary:
- dataset: **123,454 rows × 152 model-ready columns**
- final features: **204**
- base learners: **4**
- meta-learner: **Ridge**
- log-scale validation R²: **0.9988**
- euro-scale validation R²: **0.9457**
- MAE: **€12,449**
- RMSE: **€131,414**
- MAPE: **1.61%**
- overfit gap: **+0.0006**

---

## 9. Configuration & Environment

Current notebook requires:
- Python environment with pandas, numpy, sklearn, lightgbm, xgboost, matplotlib, seaborn, joblib

Local usage:
- open notebook in VS Code / Jupyter
- run from inspection to model export
- use the cleaned model-ready dataset

Potential future environment files:
- `requirements.txt`
- `.env`
- FastAPI backend config

---

## 10. Problems Encountered & Fixes Applied

Main issues encountered during development:
- old Ames-based code caused missing-column errors when run on Portugal data
- syntax issues in notebook strings
- mismatches between prototype assumptions and the real fused dataset
- feature dominance / possible leakage concerns
- ensemble improvement being small or slightly negative

Fixes applied:
- rebuilt notebook around actual Portugal schema
- replaced Ames column references with Portugal-native features
- standardized temporal and area handling
- added governance and confidence layers
- kept archive + model-ready dataset separately
- preserved lineage from category source files

---

## 11. Data & AI Work

Dataset:
- **aura_master_dataset.csv**
- **123,454 rows**
- **177 total columns before cleanup**
- **152 model-ready columns after cleanup**

Feature engineering emphasis:
- area / sqm signals
- property age
- listing recency
- energy / condition
- district prestige
- market tier
- calibration
- HPI
- macro affordability
- socio-economic strength
- ESG proxy
- AL / regulatory pressure
- confidence and completeness

Performance comparison:
- old prototype was Ames-based
- new version is Portugal-native and product-grade
- current outputs are much more aligned with real market reasoning

---

## 12. Current System State (End of Week 9)

### ✅ Completed
- Portugal master dataset integration
- data inspection and cleanup
- archive/model-ready split
- feature engineering
- stacked model training
- seller decision engine
- explainability reports
- district intelligence summary
- export of models and outputs
- comparative reporting against prior prototype

### 🔄 In Progress
- leakage audit hardening
- simplifying overly dominant features
- API deployment
- dashboard deployment
- supervisor review / positioning

### 📋 Not Started
- live FastAPI backend
- live database
- real-time feeds
- propcheck / transaction platform integration

### ⚠️ Blocked
- none technically blocked, but the current main risk is **overfitting / leakage interpretation** in the report and model review

---

## 13. Next Steps (Prioritized)

Immediate:
1. run leakage and feature-dominance review
2. prepare supervisor meeting
3. finalize report wording
4. clean notebook titles / syntax issues if any remain

Mid-term:
1. simplify or compress the model if needed
2. add API wrapper
3. add dashboard / front-end layer
4. convert outputs into supervisor-ready presentation

Long-term:
1. real-time Portuguese feeds
2. REZERVA platform integration
3. PropCheck consumer-facing verification
4. Codex / deployment pipeline
5. continuous ingestion and retraining

---

## 14. Assumptions & Active Constraints

Current assumptions:
- the fused master dataset is the operational source of truth
- missing layers are handled with graceful fallbacks
- external data coverage is sparse in some layers
- the notebook is production-oriented but still local / offline
- some outputs are exploratory and need supervisor validation

Important constraint:
- the system must remain **Portugal-native** and must not revert to Ames logic

---

## 15. Context Continuity Notes

Critical reminders for the next session:
- This is a **multi-layer intelligence system**
- The notebook is now a **production product build**
- Every output must be **decision-driven**
- Explainability is required, not optional
- The fused master dataset is the key asset
- Governance / confidence / traceability must remain visible
- Watch for leakage and over-dominant features
- Keep the Portugal market context central
- Preserve the current architecture and improve only additively

---

## Week 9 Snapshot

The system has reached a strong production-like state:
- Portugal-native
- dataset-fused
- explainable
- decision-oriented
- artifact-exportable
- supervisor-ready
