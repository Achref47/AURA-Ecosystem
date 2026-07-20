# WEEK_9_11_CONTEXT.md

# 🔁 PROPERTY INTELLIGENCE ENGINE — CONTEXT TRANSFER SYSTEM

## Week 9 → Week 11 (Critical Production Debugging + Model Architecture Validation + Strategic Expansion)

Version Tag: Week 9–11 — Final Transfer Context

---

# 1. 🧠 PROJECT OVERVIEW

---

## System Name

AURA — Adaptive Unified Real Estate Intelligence Engine

Inside the larger:

Portugal Property Intelligence Infrastructure (Powered by PIE)

---

## Purpose

Build the central intelligence infrastructure for real estate transactions in Portugal first, then Europe.

This system is not a listing platform.

It is an intelligence platform.

The goal is to solve:

## INFORMATION ASYMMETRY IN REAL ESTATE

where buyers, sellers, investors, and institutions make decisions based on incomplete, inaccurate, or manipulated information.

The system transforms:

❌ Price-based decisions

into

✅ Intelligence-driven decisions

through explainable AI infrastructure.

---

## Core Objectives

* Fair Price Valuation
* Seller-side intelligence
* Buyer-side risk protection
* Governance-aware explainability
* Predictive sourcing before listing
* Off-market seller capture
* Institutional-grade trust infrastructure
* Standardized property intelligence scoring
* Defensible real estate data platform

---

## Target Users

### Primary

* Sellers
* Property owners
* Real estate professionals
* Brokers
* Investor networks

### Secondary

* Buyers
* Investors
* Banks
* Insurance companies
* Legal professionals
* Institutions
* Funds
* Mortgage providers

---

## Strategic Direction

Seller-first strategy is mandatory.

Why:

Seller-side ownership creates:

* supply control
* off-market access
* stronger defensibility
* earlier decision influence
* proprietary market advantage

This was strongly reinforced by academic supervision.

Buyer-side expansion comes later.

---

## Core Systems

---

### InspectOS

Inspection intelligence platform.

Purpose:

Generate proprietary inspection data.

Captures:

* structural defects
* energy efficiency
* compliance issues
* hidden renovation costs
* environmental risks
* EPC quality
* legal irregularities

Strategic role:

Primary proprietary data moat.

---

### AIRCS

Adaptive Intelligent Risk Classification System

Purpose:

Standardized property risk scoring.

Formula:

AIRCS =
0.30 × Physical Integrity

* 0.25 × Regulatory Compliance
* 0.20 × Market Alignment
* 0.15 × Energy Performance
* 0.10 × Environmental Risk

Output:

* risk score
* risk class
* trust layer

Strategic role:

Property credit score equivalent.

---

### AICF

Adjusted Intelligence Correction Framework

Purpose:

Convert inspection findings into financial correction.

Formula:

Adjusted Value = Market Value − Renovation Cost

Strategic role:

True explainable valuation.

---

### PIE

Property Intelligence Engine

Core AI execution engine.

Contains:

* AIRCS
* AICF
* Fair Price Model
* Deal Finder
* ROI Simulator
* Seller Advantage
* Investment Score
* Investor Risk
* Decision Engine
* Explainability Layer
* Scenario Engine
* Market Engine

Strategic role:

Analytical brain.

---

### PropCheck

Buyer-side intelligence platform.

Flow:

Find → Price → Protect → Own

Features:

* valuation
* risk analysis
* AIRCS report
* renovation forecasting
* negotiation intelligence

---

### REZERVA

Seller-first platform.

Purpose:

Capture supply before listing.

Features:

* seller onboarding
* pricing lab
* off-market deals
* seller intelligence
* broker integration

Strategic role:

Supply ownership.

---

# 2. 🏗️ SYSTEM ARCHITECTURE

---

# Full Architecture

DATA SOURCES
→ INGESTION
→ LAKEHOUSE
→ AIRCS / PIE / AICF
→ REZERVA / PropCheck
→ Transactions
→ Feedback Loop
→ Data Flywheel

---

# Data Sources

* Idealista
* CASAFARI
* Imovirtual
* SIR transactions
* Municipal records
* EPC data
* Inspection reports
* Regulatory systems
* Predictive seller signals

---

# Lakehouse Pipeline

---

## Bronze Layer

Raw ingestion

Contains:

* listings
* transactions
* inspections
* public records
* socio-economic indicators

---

## Silver Layer

Cleaned + normalized

Contains:

* standardized records
* deduplicated data
* validation-ready datasets

---

## Gold Layer

Analytical intelligence features

Contains:

* price deviation
* compliance score
* structural score
* district prestige
* seller advantage
* market alignment
* environmental score

Used directly by PIE.

---

# AIRCS + AICF Integration

Inspection findings from InspectOS

→ AIRCS risk scoring

→ AICF financial correction

→ PIE valuation adjustment

→ final decision layer

This creates explainable intelligence.

---

# Data Flywheel

More inspections
→ Better AIRCS
→ More trust
→ More transactions
→ More data
→ Better models
→ Stronger moat

This is the true competitive advantage.

Not the model alone.

---

# 3. 🛠️ TECHNOLOGY STACK

---

# Frontend

* React
* Next.js
* Redux
* Axios
* Chart.js

Dashboard:

AURA Admin Dashboard

Features:

* valuation interface
* simulation page
* district intelligence
* analytics
* chatbot integration

---

# Backend

* FastAPI
* Node.js
* Express.js
* REST APIs

Current production focus:

FastAPI backend for valuation system.

---

# Database

Current:

MySQL + CSV prototype flow

Future:

* PostgreSQL
* PostGIS

for production-grade geospatial architecture.

---

# ML / AI

* Python
* Pandas
* NumPy
* Scikit-Learn
* LightGBM
* XGBoost
* RandomForest
* ExtraTrees
* Ridge
* SHAP
* Explainability layer

---

# Infrastructure

* Docker
* RabbitMQ
* Containerized services
* Render deployment
* Vercel deployment

---

# Security

* JWT authentication
* GDPR compliance
* explainability-first
* auditability
* governance-aware outputs

---

# New Week 9–11 Tools

Major strategic addition:

Future transition toward:

## Open Source LLM Replacement

Current chatbot:

Gemini API

Planned replacement:

Fine-tuned Open Source LLM
(example: Qwen 17B / equivalent)

Purpose:

Replace Gemini dependency with proprietary AI assistant.

This becomes Week 12 priority.

---

# 4. 📁 FULL PROJECT STRUCTURE

---

AURA/

├── backend/
│   ├── main.py
│   ├── pie_engine.py
│   ├── decision_engine.py
│   ├── market_engine.py
│   ├── scenario_engine.py
│   ├── outputs/
│   │   └── models/
│   │       ├── lgbm_model.pkl
│   │       ├── xgb_model.pkl
│   │       ├── rf_model.pkl
│   │       ├── et_model.pkl
│   │       ├── meta_learner.pkl
│   │       ├── scaler.pkl
│   │       ├── features.pkl
│   │       └── feature_defaults.pkl
│   └── requirements.txt

├── frontend/
│   ├── dashboard
│   ├── simulation page
│   ├── admin analytics
│   ├── district intelligence
│   └── chatbot interface

├── notebooks/
│   ├── valuation training
│   ├── feature engineering
│   ├── model training
│   ├── meta learner training
│   └── export pipeline

├── docs/
│   ├── architecture
│   ├── deployment
│   ├── report
│   └── supervisor guidance

---

# 5. 🔌 API DESIGN

---

# POST /predict

Status:

IMPLEMENTED

Purpose:

Main valuation endpoint.

Input:

property features

Output:

fair price + explanation metrics

---

# GET /health

Status:

IMPLEMENTED

Purpose:

Backend health validation

---

# GET /districts

Status:

IMPLEMENTED

Purpose:

District intelligence list

---

# Future

* investment-decision
* AIRCS endpoint
* scenario simulation
* governance scoring

---

# 6. 🗄️ DATABASE DESIGN

---

Current:

CSV + model artifacts

Prototype mode.

---

Future tables:

properties
inspections
transactions
district_signals
predictive_sources
seller_profiles
broker_networks

Indexes:

district
property_id
seller_id
transaction_date

Production target:

PostgreSQL + PostGIS

---

# 7. 🧩 CORE FEATURES

---

# Fair Price Engine

Current architecture:

LGBM + XGB + ET + RF
→ Ridge Meta Learner

Target:

TOTAL PROPERTY PRICE

not price/m²

This was critically verified.

Formula:

fair_price = np.expm1(prediction)

DO NOT change.

---

# AIRCS

Risk engine

Scoring:

0–100 standardized trust score

Explainability mandatory.

---

# AICF

Adjusted Value:

Market Value − Renovation Cost

---

# Seller Advantage

Measures seller-side strategic strength.

Used in REZERVA prioritization.

---

# Decision Engine

BUY / HOLD / REJECT

Based on:

* ROI
* AIRCS
* Investment Score

---

# Explainability Layer

Critical requirement.

Supervisor strongly emphasized:

Need explanation for:

WHY this valuation?

WHY this decision?

WHY such high R²?

Must be defensible.

---

# 8. 💻 FINAL CODE STATE

---

Most important production correction:

pie_engine.py

Critical functions:

* _prepare_input()
* predict()

were rewritten.

Reason:

old version used:

np.array([...])

breaking RobustScaler compatibility.

New version uses:

pd.DataFrame([...])[features]

and exact model order:

[lgbm, xgb, et, rf]

This fixed inference architecture.

BUT final issue remained.

---

# 9. ⚙️ CONFIGURATION & ENVIRONMENT

---

Critical production requirement:

Support BOTH:

LOCAL

Full Ensemble:

LGBM + XGB + ET + RF + Ridge

and

RENDER

Lightweight deployment:

LightGBM-only

without breaking either environment.

This architecture must remain.

---

# 10. 🐞 PROBLEMS ENCOUNTERED

---

# Problem 1

Valuation collapse

€250k → €85k

---

# Root Cause Investigation

First suspected:

scaler mismatch

Then:

feature alignment

Then:

meta learner order

Final discovery:

XGBoost artifact broken

---

# Smoking Gun

Logs showed:

lgbm = 12.500489
xgb = 0.837145
et = 12.444184
rf = 12.499370

This is catastrophic.

All should be around 12.xx

because target = log1p(price)

This proved:

xgb_model.pkl is broken.

This is the real issue.

---

# Final Root Cause

Broken:

xgb_model.pkl

and therefore also:

meta_learner.pkl

because Ridge was trained using broken XGB predictions.

---

# 11. 📊 DATA & AI WORK

---

Features:

204 engineered features

Examples:

* price_per_sqm
* area_x_prestige
* seller_advantage
* district_prestige
* macro_score
* demand_signal
* confidence_score

This is heavy feature engineering.

---

Performance:

R² ≈ 0.94

Supervisor flagged this as suspiciously high.

Must justify it.

Need:

feature importance
scenario validation
real-world explainability

not blind trust.

---

# 12. 🚧 CURRENT SYSTEM STATE

---

✅ COMPLETED

* architecture definition
* seller-first strategy
* valuation pipeline
* ensemble deployment
* dashboard
* simulations
* explainability direction
* inference correction
* root cause discovery

---

🔄 IN PROGRESS

* rebuild xgb_model.pkl
* rebuild meta_learner.pkl
* production validation
* public deployment
* institutional explainability

---

📋 NOT STARTED

* payment systems
* mobile app
* Europe scaling
* institutional AIRCS API
* bank integrations

---

⚠️ BLOCKED

Final production valuation depends on:

correct XGBoost rebuild

This is highest priority.

---

# 13. 🎯 NEXT STEPS

---

# Immediate (Week 12)

1. Rebuild xgb_model.pkl correctly

2. Rebuild meta_learner.pkl correctly

3. Validate healthy base learner outputs

Expected:

all models ≈ 12.xx

not xgb = 0.83

4. Production valuation verification

---

# Week 12 Strategic Task

## Open Source LLM Replacement

Current AI assistant:

Gemini API

Planned:

Replace Gemini with proprietary Open Source LLM

Likely candidate:

Qwen 17B (or equivalent)

Goal:

Own the intelligence layer.

Remove dependency on external closed APIs.

Create:

AURA proprietary real estate AI assistant

trained on:

* valuation logic
* AIRCS
* AICF
* market intelligence
* seller-side workflows
* legal explainability
* governance logic

This is a major strategic move.

Supervisor strongly supports this direction.

This becomes major Week 12 work.

---

# Mid-Term

* public deployment
* real-world expert validation
* seller onboarding tests

---

# Long-Term

* PropCheck
* REZERVA production
* institutional integrations
* Europe expansion

---

# 14. ⚠️ ASSUMPTIONS

---

Current prototype assumptions:

* simulated market assumptions
* partial real data integration
* simplified renovation cost logic
* no payment gateway yet
* deployment-first before full scale

New assumption:

Open source LLM must be practical for deployment and explainability, not just “big model hype.”

Must support business value.

---

# 15. 🔄 CONTEXT CONTINUITY NOTES

---

Critical reminders for next AI:

This is a MULTI-MODEL system

NOT a single ML model

---

This is INFRASTRUCTURE

NOT just a notebook

---

Explainability is mandatory

NOT optional

---

Seller-first strategy is core

NOT buyer-first

---

AIRCS and AICF are independent engines

NOT one module

---

The real moat is:

data flywheel + proprietary inspection data

NOT model accuracy alone

---

Current highest priority:

BROKEN XGBOOST ARTIFACT

Fix:

xgb_model.pkl + meta_learner.pkl

before anything else

---

Week 12 major strategic priority:

OPEN SOURCE LLM

Replace Gemini

Build proprietary assistant

This is now core roadmap.

---

END OF TRANSFER
