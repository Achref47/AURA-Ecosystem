# WEEK_7_SUMMARIZED_CONTEXT.md

# ⚠️ CONTEXT TRANSFER MODE — WEEK 7
This document is a **complete context transfer** for the current PIE prototype state so a new chat can continue development without losing the architecture, current logic, or implementation history.

## Verified scope of this week
The **verified implementation** in this conversation centers on the **Property Intelligence Engine (PIE)** prototype: the analytical notebook, the FastAPI backend, the React frontend, the simulation page, the AI assistant, PDF export, and the context-aware chatbot flow.

> Note: The broader umbrella terms such as **Portugal Property Intelligence Infrastructure**, **InspectOS**, **PropCheck**, and **REZERVA** were mentioned in the requested structure, but they were **not fully defined or implemented in the verified codebase during this conversation**. The current working implementation is PIE. They can be treated as future/program-level architecture labels unless the team later maps them explicitly.

---

# 1. 🧠 PROJECT OVERVIEW

## System name
**Property Intelligence Engine (PIE)**  
Prototype for an AI-powered real-estate investment decision platform.

## Purpose and objectives
PIE was built to transform raw housing data into actionable investment intelligence. Instead of only predicting prices, the system evaluates:
- profitability (ROI)
- risk (AIRCS)
- market inefficiency (deal detection)
- investment quality (decision engine)
- user explainability (XAI)
- interactive scenario testing (simulation)
- conversational guidance (AI chatbot)

## Problem being solved
The project addresses **information asymmetry** in real estate:
- buyers/investors often do not know whether a property is overpriced
- profitability is hard to estimate manually
- structural risk is not obvious from sale price alone
- raw price prediction is not enough for decision-making

PIE turns property data into a decision-support workflow that helps users decide whether to **BUY**, **HOLD**, or **REJECT** a property.

## Target users
- real-estate investors
- analysts
- agencies
- supervisors/reviewers during prototype validation
- end users who need investment guidance

## Core system components
### Verified in the current implementation
- **Notebook analytical pipeline**
- **AIRCS** risk score
- **AICF** cost-adjustment / renovation estimation logic
- **ML valuation model**
- **Deal Finder**
- **ROI simulator**
- **Investment Score**
- **Decision Engine**
- **Explainability layer**
- **FastAPI backend**
- **React frontend**
- **Simulation page**
- **AI assistant**
- **PDF export**

### Mentioned in broader architecture but not fully verified in this conversation
- InspectOS
- PropCheck
- REZERVA

---

# 2. 🏗️ SYSTEM ARCHITECTURE

## Full architecture
The project follows a **data → intelligence → platform** structure:

**Raw housing data**  
→ exploratory analysis  
→ feature engineering  
→ risk scoring  
→ value correction  
→ predictive modeling  
→ investment scoring  
→ explainability  
→ web platform  
→ AI assistant  
→ PDF report / user interaction

## Lakehouse-style pipeline idea
The broader architecture can be interpreted like a lakehouse pattern:
- **Bronze**: raw CSV housing dataset
- **Silver**: cleaned and engineered features
- **Gold**: final intelligence outputs such as ROI, AIRCS, DealScore, Decision, ConfidenceScore

This is a conceptual mapping; the verified implementation currently uses a notebook and CSV-driven workflow rather than a full production lakehouse stack.

## AIRCS + AICF integration
- **AIRCS** evaluates structural quality / risk
- **AICF** estimates renovation or adjustment cost
- Together they help avoid relying only on price prediction
- They make the system investment-oriented rather than purely predictive

## PIE analytical pipeline
1. Load dataset
2. EDA
3. Remove outliers
4. Engineer features
5. Compute AIRCS
6. Compute AICF / adjusted value
7. Train regression model
8. Predict price
9. Detect market inefficiency
10. Score deals
11. Simulate ROI
12. Generate decision + explanation
13. Validate with plots and summary statistics

## Data flywheel explanation
Every property evaluation produces:
- structured outputs
- decision feedback
- explanation signals
- user interaction data in the web app

This can later be used to improve:
- feature engineering
- scoring thresholds
- model accuracy
- chatbot responses

## Design patterns used
- pipeline architecture
- modular feature engineering
- decision-driven outputs
- explainability-first design
- data-centric modeling
- notebook-to-API conversion
- frontend/backend separation

---

# 3. 🛠️ TECHNOLOGY STACK

## Frontend
- React
- React Router
- Framer Motion
- Chart.js
- Axios

## Backend
- FastAPI
- Pydantic
- Uvicorn
- Python-based AI integration

## Data / ML
- pandas
- numpy
- scikit-learn
- XGBoost
- LightGBM
- joblib
- matplotlib
- seaborn

## Reporting / export
- html2canvas
- jsPDF

## Infrastructure / environment
- Python virtual environment (`venv`)
- local development server
- localhost frontend + backend integration

## Security / governance
Not production-ready yet, but the long-term direction should include:
- GDPR awareness
- access control
- encryption
- user/session management
- safe API key handling

---

# 4. 📁 FULL PROJECT STRUCTURE

## Current / practical structure used in this prototype
PIE/
- `data/` → CSV dataset and intermediate files
- `notebook/` → analytical notebook and research logic
- `models/` → saved model, scaler, features
- `backend/` → FastAPI app and chatbot logic
- `frontend/` → React application
- `docs/` → reports, documentation, context notes
- `outputs/` → charts, exported tables, PDFs
- `reports/` → weekly progress / notebook report drafts

## Role of each module
### `data/`
Contains the Ames Housing dataset (`train.csv`) and any working copies of the data.

### `notebook/`
Contains the analytical core:
- EDA
- feature engineering
- AIRCS
- AICF
- model training
- market inefficiency detection
- clustering
- validation
- decision logic

### `models/`
Contains exported artifacts such as:
- `model.pkl`
- `scaler.pkl`
- `features.pkl`
- `aicf_model.pkl`

### `backend/`
Contains:
- `main.py`
- `pie_engine.py`
- `chatbot.py`

This is the API layer that exposes:
- `/predict`
- `/chat`

### `frontend/`
Contains the React application:
- dashboard
- analysis page
- simulation page
- AI assistant
- routing
- report / PDF export UI

### `docs/`
Contains:
- weekly progress
- technical report
- final explanation
- context transfer notes

### `outputs/`
Contains:
- charts
- visualizations
- CSV exports
- generated PDF reports

---

# 5. 🔌 API DESIGN (CURRENT + FUTURE)

## Current verified endpoints

### `/predict`
**Purpose:** return property valuation and investment outputs.

**Typical request**
```json
{
  "SalePrice": 200000,
  "GrLivArea": 1500,
  "OverallQual": 7,
  "TotRmsAbvGrd": 6,
  "YearBuilt": 2005
}
```

**Typical response**
```json
{
  "pred_price": 116614,
  "roi": -0.4169,
  "aircs": 0.42,
  "decision": "REJECT",
  "explanation": "...",
  "score": 0.0
}
```

### `/chat`
**Purpose:** answer investment questions using Gemini and optional context.

**Current request structure**
```json
{
  "message": "Why is this property rejected?",
  "context": {
    "roi": -0.4169,
    "aircs": 0.42,
    "decision": "REJECT"
  }
}
```

**Purpose of context**
The chatbot receives the property analysis so it can generate answers based on the current property instead of only answering generic questions.

## Future API endpoints (planned)
### `/evaluate-property`
- purpose: unified property evaluation
- may combine price prediction, risk, and recommendation

### `/investment-decision`
- purpose: return decision-only output

### `/aircs-score`
- purpose: risk score only

### `/deal-finder`
- purpose: ranked opportunities / undervalued property detection

---

# 6. 🗄️ DATABASE DESIGN

## Current state
The prototype currently relies on:
- CSV dataset
- notebook transformations
- in-memory processing
- exported model artifacts

## Future database design
A production version should use a relational database such as PostgreSQL (+ PostGIS if spatial features are added).

### Proposed tables
#### `properties`
- property_id
- price
- area
- year_built
- rooms
- quality
- condition
- neighborhood
- etc.

#### `inspections`
- inspection_id
- property_id
- AIRCS inputs
- inspection notes
- structural observations

#### `transactions`
- transaction_id
- property_id
- purchase price
- renovation cost
- sale price
- ROI outcome

#### `features`
- feature_id
- property_id
- engineered feature values
- encoded neighborhood value
- model inputs

## Relationships
- one property can have multiple inspections
- one property can have multiple transaction records over time
- one property has one current feature snapshot for model inference

---

# 7. 🧩 CORE FEATURES IMPLEMENTED

## AIRCS
### Logic
AIRCS is a custom risk score that summarizes structural quality and risk.

### In the notebook
AIRCS was originally computed from:
- OverallCond
- OverallQual
- HouseAge
- YearRemodAdd

### In the web prototype
AIRCS was later stabilized so it would not stay constant on single-row inputs.  
The final working concept uses normalized property characteristics to produce a variable risk score that changes with:
- quality
- condition
- age
- rooms
- garage
- bathrooms

### Purpose
- indicate low / medium / high risk
- support decision-making
- improve explainability

---

## AICF
### Logic
AICF is the project’s **cost-adjustment / renovation-factor logic**.

### Purpose
- estimate the cost pressure on a property
- correct value from an investment perspective
- make evaluation more realistic

### Role in the system
AICF helps the system understand that a property may be cheap but expensive to renovate.

---

## ML Model
### Role
Predict the market value of a property.

### Notebook
- multiple models tested
- GradientBoostingRegressor selected as the final working model in the notebook

### Outputs
- PredictedPrice
- error vs actual price
- market inefficiency insight

---

## Deal Finder
### Logic
Compares:
- predicted value
- adjusted value
- actual sale price

### Output classes
- Strong Deal
- Opportunity
- Fair
- Overpriced

### Purpose
To identify undervalued properties that may represent good investment opportunities.

---

## ROI Simulator
### Notebook logic
The notebook ROI module uses:
- purchase price
- renovation cost
- holding cost
- transaction cost
- predicted resale value

### Formula
Total Investment =
purchase price + renovation cost + holding cost + transaction cost

Expected Profit =
post-renovation value - total investment

ROI =
expected profit / total investment

### Web prototype logic
The simulation page also uses a simpler live demo ROI:
- ROI = (predicted price - purchase price) / purchase price

This simpler formula is used for the interactive prototype and web demo.

---

## Investment Score
### Logic
A combined ranking metric based on:
- ROI
- DealScore
- AIRCS
- stability

### Purpose
To avoid relying on a single score and instead rank properties by overall investment attractiveness.

---

## Decision Engine
### Output categories
- BUY
- HOLD
- REJECT

### Purpose
Converts numeric outputs into clear action recommendations.

---

## Explainability
### Logic
The system produces human-readable reasons based on:
- ROI
- AIRCS
- DealScore
- price gap

### Purpose
Explain why the property was recommended or rejected.

---

# 8. 💻 FINAL CODE STATE

## Latest verified backend logic
### Property input
Required:
- SalePrice
- GrLivArea
- OverallQual
- TotRmsAbvGrd
- YearBuilt

Optional:
- OverallCond
- GarageCars
- GarageArea
- TotalBsmtSF
- FirstFlrSF
- SecondFlrSF
- FullBath
- HalfBath
- BsmtFullBath
- BsmtHalfBath
- YearRemodAdd
- YrSold

### Important transformation
Missing fields are auto-generated in `enrich_missing_features()`.

### Final working decision logic in the prototype
```text
BUY  -> strong ROI + acceptable AIRCS + strong combined score
HOLD -> moderate return / moderate risk
REJECT -> otherwise
```

### Confidence calculation used in the web app
A simple prototype confidence metric is computed from ROI and AIRCS:
```text
confidence = ((AIRCS + |ROI|) / 2) * 100
```

### Current chatbot flow
- user clicks “Ask AI”
- simulation result is passed to the AI page
- a full property report is generated as prompt text
- the question is auto-sent to the chatbot backend

---

# 9. ⚙️ CONFIGURATION & ENVIRONMENT

## Python environment
- Python 3.x
- virtual environment (`venv`)

## Key dependencies
### Notebook / ML
- pandas
- numpy
- scikit-learn
- xgboost
- lightgbm
- matplotlib
- seaborn
- joblib

### Backend
- fastapi
- uvicorn
- pydantic
- google-genai

### Frontend
- react
- react-router-dom
- axios
- framer-motion
- chart.js
- html2canvas
- jspdf

## Run commands

### Backend
```bash
python -m uvicorn main:app --reload
```

### Frontend
```bash
npm install
npm run dev
```

### Model save example
```python
joblib.dump(model, "models/aicf_model.pkl")
joblib.dump(features, "models/features.pkl")
```

### Scaler / model persistence note
The prototype encountered version mismatches between scikit-learn model artifacts and the runtime environment during development. The current working state relies on the exported artifacts and the final tested backend logic.

---

# 10. 🐞 PROBLEMS & SOLUTIONS

## 1) AIRCS stayed fixed at 0.25
### Root cause
The score was being normalized using `MinMaxScaler` on a single-row input, which collapses the range and produces almost constant values.

### Fix
Reworked AIRCS to use normalized manual property attributes so it changes per input and remains meaningful in the prototype.

---

## 2) CORS error between frontend and backend
### Root cause
Frontend ran on `localhost:5173` while backend was on `127.0.0.1:8000`, causing browser cross-origin blocking.

### Fix
Added CORS middleware with the correct allowed origin and ensured the frontend calls the backend consistently.

---

## 3) 422 Unprocessable Content on `/predict`
### Root cause
Field names and request schema did not match the backend model requirements.

### Fix
Aligned frontend request payload with the FastAPI `PropertyInput` model and mapped field names correctly.

---

## 4) 404 on Gemini model
### Root cause
A model name used in the chatbot was not available in the API version/account.

### Fix
Switched to the available model that worked reliably in the prototype environment.

---

## 5) 429 RESOURCE_EXHAUSTED from Gemini
### Root cause
Free-tier quota limitations.

### Fix
Added fallback error handling and used simpler requests. The prototype remains functional with quota-aware behavior.

---

## 6) Indentation errors in `pie_engine.py`
### Root cause
Temporary code edits introduced indentation issues.

### Fix
Removed the broken lines and stabilized the file structure.

---

## 7) `pred_price` NameError at import time
### Root cause
Debug code was left at module level instead of inside functions.

### Fix
Removed module-level debug statements and kept logging inside function scope only.

---

## 8) NaN on “Overpriced by $NaN”
### Root cause
The frontend tried to compute price difference using a field that was not actually sent back.

### Fix
Returned the original sale price in the backend response and computed the price difference safely.

---

## 9) PDF export looked messy
### Root cause
Exporting the entire UI caused sliders and layout elements to appear in the PDF.

### Fix
Wrapped a clean report section for export and kept the controls outside the exported area.

---

## 10) Chatbot was generic
### Root cause
The chatbot only received raw text, not the property analysis context.

### Fix
Passed the simulation/report result into the chat flow and auto-generated a detailed prompt from the property analysis.

---

# 11. 📊 DATA / AI WORK

## Dataset
- **Ames Housing Dataset**
- used for property price prediction and investment analysis

## Feature engineering
The notebook engineered features that capture:
- age
- renovation-related effects
- size
- quality
- bathrooms
- garage
- basement
- neighborhood effects

## Model performance
### Verified approximate performance
- R² ≈ 0.88–0.89
- MAE ≈ 10k

## Why this performance is acceptable
Real estate data is inherently noisy and incomplete:
- prices depend on negotiation
- location quality varies
- economic conditions are external
- the dataset does not include all real market signals

## Improvements
- real-time market data
- geo features
- economic indicators
- more training data
- better model calibration
- custom AI real-estate assistant instead of generic API only

---

# 12. 🚧 CURRENT SYSTEM STATE

## Completed
- notebook analytical pipeline
- AIRCS logic
- AICF logic
- ML training and evaluation
- market inefficiency detection
- deal finder
- ROI simulation
- decision engine
- explainability layer
- React frontend
- FastAPI backend
- simulation page
- PDF export
- chatbot integration
- context-aware AI prompt generation

## In progress
- report/presentation polishing
- final documentation
- possible minor UI refinement

## Not started
- production deployment
- real-time market integration
- full database integration
- domain-specialized custom real-estate LLM
- Codex-based production automation

---

# 13. 🎯 NEXT STEPS

## Immediate
- finalize presentation
- prepare demo flow
- ensure smooth navigation between simulation and AI pages
- keep UI stable and avoid new major changes

## Mid-term
- integrate real-time property market data
- move from CSV prototype to database-backed system
- add more realistic renovation and market cost modeling

## Long-term
- deploy as a real platform
- replace generic chatbot API with a specialized real-estate AI model
- add authentication, analytics, and scalable infrastructure
- transition parts of the prototype to Codex/production workflow

---

# 14. ⚠️ ASSUMPTIONS & CONSTRAINTS

- prototype only, not final production
- simplified cost model in some places
- AIRCS is a custom project score, not a standard industry metric
- AICF is a custom project concept
- no live market data yet
- external economic factors are not yet integrated
- the chatbot currently uses Gemini API rather than a fully custom-trained real-estate model

---

# 15. 🔄 CONTEXT CONTINUITY NOTES

## Critical continuity points for the next chat
- The system is **multi-component**, not a single ML model.
- The notebook is the analytical core.
- The web app is the interaction layer.
- The backend exposes `/predict` and `/chat`.
- The simulation page runs against the real backend.
- The chatbot must remain **context-aware**.
- Explainability is required in every output path.
- The prototype is intentionally simplified and should not be mistaken for final production.

## Current mental model of the project
**Data → Feature Engineering → AIRCS / AICF → ML Prediction → ROI / DealScore / InvestmentScore → Decision → Explanation → Web App → Context-Aware Chat**

---

# END OF CONTEXT TRANSFER
