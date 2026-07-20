# 🧠 CORE CONTEXT — AURA / PROPERTY INTELLIGENCE INFRASTRUCTURE (FINAL MASTER CONTEXT V3)

---

# 1. SYSTEM OVERVIEW

## System Name

AURA — Adaptive Unified Real Estate Intelligence Engine

Built inside the larger:

Portugal Property Intelligence Infrastructure (Powered by PIE)

---

## Vision

Build the central intelligence infrastructure for property transactions in Portugal first, then expand to Europe.

Move the market from:

❌ Listing-price-based real estate

➡️ toward

✅ Intelligence-driven real estate decision systems

The goal is not “property listing software.”

The goal is:

A defensible AI-powered real estate intelligence infrastructure.

This is a seller-first + intelligence-first ecosystem.

---

## Core Philosophy

This project is NOT:

* just an ML model
* just a valuation tool
* just a dashboard
* just a chatbot
* just a pricing estimator

It is a:

✅ Property Intelligence Infrastructure
✅ Multi-layer AI Decision Engine
✅ Predictive Real Estate Intelligence Platform
✅ Governance-aware Explainable Valuation System
✅ Defensible Data Platform

This distinction is extremely important.

---

## Strategic Direction

The system prioritizes:

# SELLER-FIRST INTELLIGENCE

before buyer expansion.

Why:

Seller-side control creates:

* stronger data ownership
* earlier supply capture
* off-market opportunity creation
* stronger defensibility
* predictive sourcing advantages

This was strongly reinforced during supervision meetings.

Buyer-side expansion comes later.

---

# 2. FULL SYSTEM ECOSYSTEM (MACRO ARCHITECTURE)

The platform is composed of multiple connected systems.

It is NOT a single application.

It is an ecosystem.

---

# 2.1 InspectOS — Data Generation Layer

## Purpose

Inspection-driven proprietary data generation system.

This is one of the strongest moats.

---

## Role

Collect real inspection intelligence from the physical property.

Unlike portals, this is proprietary first-party data.

---

## Captures

* structural defects
* hidden damage
* compliance issues
* renovation requirements
* energy efficiency
* EPC quality
* safety risks
* environmental signals
* habitability concerns
* legal irregularities
* technical inspection reports
* renovation cost estimates

---

## Strategic Importance

This creates:

PROPRIETARY DATA ADVANTGE

instead of relying only on scraped listing portals.

This is critical.

Without proprietary data:

there is no true defensible moat.

---

# 2.2 AIRCS — Core Risk Intelligence Layer

## Meaning

Adaptive Intelligent Risk Classification System

---

## Purpose

Standardized property risk scoring engine.

Transforms inspection + market + regulatory data into interpretable risk.

This becomes the “credit score of the property.”

---

## Formula

AIRCS =

0.30 × Physical Integrity

* 0.25 × Regulatory Compliance
* 0.20 × Market Alignment
* 0.15 × Energy Performance
* 0.10 × Environmental Risk

---

## Output

* score (0–100)
* risk class
* confidence layer
* governance flags
* human review requirement

---

## Strategic Role

AIRCS becomes:

THE STANDARDIZED TRUST LAYER

for:

* buyers
* sellers
* banks
* investors
* insurers
* legal professionals

This is central.

---

# 2.3 AICF — Valuation Correction Layer

## Meaning

Adjusted Intelligence Correction Framework

---

## Formula

Adjusted Value = Market Value − Renovation Cost

---

## Purpose

Convert technical inspection findings into financial corrections.

This solves:

“Why is this property actually worth less?”

instead of blind market pricing.

---

## Example

Listing says:

€350,000

Inspection reveals:

€45,000 hidden renovation risk

Real adjusted value becomes:

€305,000

This is critical for seller trust.

---

# 2.4 PIE — Property Intelligence Engine (CORE AI SYSTEM)

## This is the analytical brain

PIE is the execution engine of intelligence.

Everything flows through PIE.

---

## PIE Modules

* AIRCS (risk scoring)
* AICF (valuation correction)
* ML Fair Price Valuation
* Deal Finder
* ROI Simulator
* Investment Score
* Seller Advantage Score
* Investor Risk Score
* Governance Score
* Decision Engine
* Explainability Layer
* Scenario Engine
* Market Intelligence Engine
* Future Digital Twin Layer

---

## Strategic Role

PIE = execution layer of intelligence

AURA = unified intelligence orchestration

InspectOS = data moat

Together they form the real company.

---

# 2.5 REZERVA — Seller Platform

## Priority Platform

Seller-first platform.

This is the primary strategic direction.

---

## Purpose

Capture supply BEFORE listing.

This is far more valuable than competing for listed properties.

---

## Features

* seller onboarding
* seller scoring
* pricing lab
* pre-listing valuation
* seller advantage analysis
* off-market opportunity capture
* private inventory creation
* professional network integration
* broker connection
* seller intelligence
* predictive sourcing integration

---

## Strategic Value

This creates:

OFF-MARKET SUPPLY OWNERSHIP

which is far stronger than buyer portals.

---

# 2.6 PropCheck — Buyer Platform

## Purpose

Buyer intelligence platform.

Comes after seller-side maturity.

---

## Features

* risk analysis
* fair valuation
* AIRCS reports
* predictive deal discovery
* investor analysis
* governance confidence
* renovation forecasting
* negotiation intelligence

---

## Buyer Flow

Find → Price → Protect → Own

---

# 2.7 Predictive Sourcing Engine

## Purpose

Predict supply before listing happens.

This is one of the strongest strategic moats.

---

## Signals

* inheritance patterns
* ownership duration
* tax irregularities
* permit activity
* EPC expiration
* renovation signals
* mortgage stress indicators
* vacancy indicators
* family transfer patterns
* legal change indicators

---

## Output

Predictive Property Watchlist

This allows seller capture before the market sees it.

Massive strategic advantage.

---

# 3. AURA V4 — CURRENT ML PRODUCTION ENGINE

This is the current deployed valuation core.

Extremely important.

---

# 3.1 Current Model Architecture

Stacked Ensemble:

LGBM + XGBoost + ExtraTrees + RandomForest
→ Ridge Meta Learner

This is NOT a single-model system.

It is a professional ensemble architecture.

---

# 3.2 Confirmed Model Parameters

## LightGBM

* 1500 estimators
* learning_rate = 0.025
* max_depth = 7
* num_leaves = 50

---

## XGBoost

* 1500 estimators
* learning_rate = 0.025
* max_depth = 6

---

## Random Forest

* 600 estimators
* max_depth = 18

---

## Extra Trees

* 600 estimators
* max_depth = 18

---

## Meta Learner

Ridge(alpha = 0.5)

---

## Scaler

RobustScaler

quantile_range = (25,75)

---

# 3.3 Training Target (CRITICAL)

Notebook confirms:

df["LogPrice"] = np.log1p(df["price"])

y = data["LogPrice"]

This means:

MODEL TARGET = TOTAL PROPERTY PRICE

NOT price-per-sqm

This is extremely important.

Therefore:

fair_price = np.expm1(prediction)

is mathematically correct.

DO NOT change this.

DO NOT multiply by area.

This was a critical debugging point.

---

# 3.4 Engineered Features

204 engineered features

Examples:

* price_per_sqm
* price_per_room
* area_x_prestige
* seller_advantage
* district_prestige
* energy_x_location
* esg_composite
* macro_score
* demand_signal
* confidence_score
* investor_risk_score
* price_per_sqm_x_tier
* demand_persistence
* neighborhood_strength

This proves the system is feature-engineering heavy.

Not simple input prediction.

---

# 4. CRITICAL PRODUCTION ISSUE DISCOVERED

Extremely important recent finding.

---

# 4.1 Original Failure

System started producing:

Asking Price = €250,000

Fair Price = €85,718

Clearly wrong.

This triggered full architecture debugging.

---

# 4.2 First Suspected Issue

pie_engine.py was using:

np.array([...])

instead of:

pd.DataFrame([...])[features]

while scaler was trained with feature names.

This produced:

"X does not have valid feature names"

This was dangerous.

---

# 4.3 Second Issue

Base learner predictions used:

_store.base_models.values()

This is unsafe because Ridge requires exact order:

[lgbm, xgb, et, rf]

Wrong order breaks meta learner.

This was fixed.

---

# 4.4 REAL ROOT CAUSE FOUND

After fixing feature alignment, logs showed:

lgbm = 12.500489
xgb = 0.837145
et = 12.444184
rf = 12.499370

This is catastrophic.

All models should predict around:

12.xx

because they all should use:

y = log1p(price)

But XGBoost predicts:

0.83

which proves:

XGBoost artifact is broken.

This is the real issue.

---

# 4.5 Final Diagnosis

The main production issue is:

BROKEN XGBOOST ARTIFACT

Most likely:

* trained on wrong target
* old artifact mismatch
* serialization mismatch
* wrong xgb_model.pkl copied
* meta learner trained on broken XGB predictions

Therefore:

must rebuild:

1. xgb_model.pkl
2. meta_learner.pkl

This is the current highest priority.

---

# 5. FULL SYSTEM DATA FLOW

DATA SOURCES
→ INGESTION
→ LAKEHOUSE
→ PIE / AIRCS / AICF
→ REZERVA / PropCheck
→ TRANSACTIONS
→ FEEDBACK LOOP
→ DATA FLYWHEEL

This loop is the moat.

---

# 6. DATA PIPELINE (LAKEHOUSE)

## Bronze Layer

Raw data

* listings
* inspections
* regulatory
* socio-economic
* market indices
* transaction records

---

## Silver Layer

Cleaned + normalized

* deduplicated
* standardized
* validated
* feature-ready

---

## Gold Layer

Analytical features

* structural score
* compliance score
* valuation delta
* environmental risk
* macro indicators
* seller signals
* predictive sourcing signals

This powers PIE.

---

# 7. DECISION ENGINE

BUY

if:

ROI > 8%
AIRCS > 0.5
InvestmentScore > threshold

---

HOLD

if:

ROI > 3%
AIRCS > 0.35

---

REJECT

otherwise

---

This must remain explainable.

No black-box-only decisions.

---

# 8. SUPERVISOR GUIDANCE (VERY IMPORTANT)

Multiple supervision meetings established strategic priorities.

These must guide all future work.

---

# Key Guidance

## Use all useful relevant data

Not just model-friendly data.

Especially:

* external market conditions
* interest rates
* inflation
* banking indicators
* geopolitical effects
* market stability

---

## Explainability First

The system must justify:

WHY this price?

WHY this decision?

WHY this score?

Especially because R² ≈ 0.94 looked suspiciously high.

Need explainability + validation.

---

## Seller-first priority

Focus seller-side first.

Buyer-side later.

Strongly reinforced.

---

## Prototype now, production later

Current work = prototype

Must show path to deployment.

---

## Public deployment quickly

Real-world testing matters more than internal perfection.

Get feedback fast.

---

## Governance-aware architecture

System must be trusted by:

banks
investors
sellers
buyers
institutions

Explainability is mandatory.

---

# 9. TECHNOLOGY STACK

## Frontend

* React
* Next.js
* Redux
* Axios
* Chart.js

---

## Backend

* FastAPI
* Node.js
* Express.js
* REST APIs

---

## Database

* MySQL
* PostgreSQL
* PostGIS

---

## Infrastructure

* Docker
* RabbitMQ
* Containerized services

---

## ML Stack

* Python
* Pandas
* NumPy
* Scikit-Learn
* LightGBM
* XGBoost
* SHAP
* Explainability layers

---

# 10. BUSINESS MODEL

Revenue Streams:

* Property Reports (€99–€499)
* Inspection commissions
* AIRCS API for banks
* SaaS subscriptions
* Seller-side premium tools
* Investor intelligence products
* Data analytics
* Institutional API access

This is infrastructure economics.

Not simple SaaS.

---

# 11. STRATEGIC MOATS

True defensibility comes from:

1. InspectOS proprietary inspection dataset

2. AIRCS standardized trust score

3. Predictive sourcing engine

4. REZERVA off-market seller capture

5. Data Flywheel

6. Explainable decision engine

7. Governance + trust layer

This is the moat.

Not the model alone.

---

# 12. CURRENT SYSTEM PHASE

CURRENT:

Advanced prototype + architecture validation

---

NEXT:

* rebuild xgb_model.pkl
* rebuild meta_learner.pkl
* validate production valuation
* public deployment
* real expert testing

---

FUTURE:

* payment systems
* mobile app
* multi-language
* institutional integrations
* Europe expansion
* full platform productionization

---

# FINAL NOTE FOR FUTURE AI

This system is:

NOT just ML
NOT just a dashboard
NOT just a valuation tool

It is:

PROPERTY INTELLIGENCE INFRASTRUCTURE

AI DECISION ENGINE

DEFENSIBLE DATA PLATFORM

REAL ESTATE INTELLIGENCE ECOSYSTEM

CORE CONTEXT = SYSTEM MEMORY

WEEKLY UPDATES = EXECUTION STATE

Use this as the foundation for all future work.
