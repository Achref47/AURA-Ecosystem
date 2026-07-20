# WEEK_X_SUMMARIZED_CONTEXT.md
# Complete Context Transfer Document
## Project: Portugal Property Intelligence Infrastructure + PIE

> This document is intended to transfer the full working context of the project into a new chat with minimal or zero loss of architectural, product, and implementation history.

---

# 1. PROJECT OVERVIEW

## 1.1 System Name
The broader platform concept is **Portugal Property Intelligence Infrastructure**.  
The implemented core intelligence component is **PIE — Property Intelligence Engine**.

PIE is now aligned with the **Rezerva** ecosystem and positioned as a **seller-first real estate intelligence engine** rather than a buyer-only decision tool.

## 1.2 Purpose
The project exists to reduce information asymmetry in real estate decision-making. It takes property attributes and transforms them into:
- valuation intelligence,
- market intelligence,
- seller decision recommendations,
- scenario simulation outputs,
- AI-based explanations.

The system is not just a prediction model. It is a modular intelligence layer that supports real estate workflows.

## 1.3 Problem Being Solved
The central problem is that property decisions are often made with incomplete visibility into:
- fair market value,
- local demand pressure,
- listing strategy,
- risk exposure,
- liquidity/time-to-sell,
- pricing consequences.

The platform addresses this by giving:
- a seller-oriented valuation,
- a decision recommendation,
- explainability,
- scenario testing,
- context-aware AI support.

## 1.4 Target Users
Current and future user groups:
- **Sellers**: primary focus in the current architecture
- **Buyers**: preserved as a secondary module through PropCheck
- **Agents / intermediaries**: future multi-stakeholder use
- **Platform operators**: Rezerva ecosystem integration

## 1.5 Core System Components
The system is organized around the following components:

### InspectOS
Future/adjacent infrastructure concept for structured property inspection intelligence and external inputs.

### AIRCS
A risk/condition intelligence concept used to describe structural or condition sensitivity and evaluation quality.

### AICF
An additional future intelligence concept used in the broader platform vision.

### PIE
The main intelligence engine implemented in the project. It is the core analytical layer.

### PropCheck
The buyer-side module preserved in the architecture as a secondary flow. It is not the current primary focus.

### Rezerva
The broader platform vision into which PIE is aligned. The project is now framed as a seller-first intelligence layer inside Rezerva.

---

# 2. SYSTEM ARCHITECTURE

## 2.1 High-Level Architecture
The architecture is now multi-layered:

1. **Property input layer**
   - user enters property features

2. **Prediction layer**
   - ML model generates fair price / baseline valuation

3. **Market intelligence layer**
   - demand, liquidity, segment, and macro context are attached

4. **Decision layer**
   - seller strategy is computed from combined signals

5. **Scenario layer**
   - alternative pricing strategies can be simulated

6. **AI explanation layer**
   - context-aware assistant explains outputs in natural language

7. **Rezerva integration layer**
   - seller-first flow, buyer preserved as secondary module

## 2.2 Data → Intelligence → Platform Flow
The system logic is:

**Input features** → **PIE prediction** → **FPI seller valuation** → **market intelligence** → **decision engine** → **scenario simulation** → **AI explanation** → **seller portal / dashboard**

This transforms raw numeric data into actionable intelligence.

## 2.3 Lakehouse / Data Pipeline Vision
The longer-term architecture follows a lakehouse-style progression:

### Bronze
Raw ingest from datasets or future external sources.

### Silver
Cleaned, normalized, and feature-engineered data.

### Gold
Decision-ready analytical outputs:
- fair price,
- risk profile,
- demand pressure,
- pricing strategy,
- scenario results.

## 2.4 AIRCS + AICF Integration
In the broader platform design:
- AIRCS contributes to structural/condition risk logic,
- AICF is a future intelligence extension,
- both are part of the platform vision but not fully productionized yet.

## 2.5 PIE Analytical Pipeline
The implemented analytical chain is:
- property input,
- preprocessing,
- valuation,
- market intelligence,
- seller decision,
- scenario output,
- AI explanation,
- report/dashboard rendering.

## 2.6 Data Flywheel Concept
The product direction is designed as a flywheel:
- more seller interactions generate more valuation/market feedback,
- more feedback improves the intelligence layer,
- better intelligence improves seller trust and adoption,
- more adoption increases the data value of the platform.

## 2.7 Design Patterns
The system uses:
- pipeline architecture,
- modular decomposition,
- data-centric design,
- separation between seller and buyer outputs,
- explainability-first outputs,
- context-aware AI prompts.

---

# 3. TECHNOLOGY STACK

## 3.1 Frontend
Current frontend stack:
- React
- TypeScript
- React Router
- Axios
- Framer Motion
- html2canvas
- jsPDF

UI style:
- executive dashboard layout,
- clean cards,
- soft shadows,
- white panels on light neutral background,
- blue accent color,
- serif title treatment in several screens.

## 3.2 Backend
Current backend stack:
- FastAPI
- Python
- Pydantic
- Modular helper files for valuation, market intelligence, decision logic, scenario logic, chatbot

## 3.3 Data
Current state:
- CSV-based / local dataset workflow for prototype and model development

Future direction:
- PostgreSQL
- PostGIS
- structured relational storage
- platform-level persistence

## 3.4 ML / Data Science
Used or intended:
- scikit-learn
- gradient boosting / tree-based regressors
- feature engineering
- evaluation metrics such as MAE and R²

## 3.5 Infrastructure / Deployment
Current:
- local FastAPI and React development
- no full production deployment yet

Future:
- Docker
- queues/pipelines
- API gateway
- production hosting
- real data ingestion

## 3.6 Security / Compliance
Long-term requirements:
- GDPR-aware architecture
- encryption
- role-based access
- data isolation by stakeholder type

---

# 4. FULL PROJECT STRUCTURE

The project conceptually follows this structure:

```text
PIE/
├── data/
├── notebook/
├── models/
├── app/
├── docs/
├── outputs/
```

## 4.1 data/
Contains:
- raw dataset files,
- cleaned CSVs,
- interim processed datasets.

## 4.2 notebook/
Contains:
- exploratory analysis,
- model training notebooks,
- feature engineering trials,
- evaluation experiments.

## 4.3 models/
Contains:
- saved trained models,
- scalers or encoders if needed,
- reusable model artifacts.

## 4.4 app/
Contains:
- frontend React application,
- pages,
- components,
- services,
- layouts.

## 4.5 docs/
Contains:
- architecture docs,
- reports,
- project explanations,
- Week 8 documentation.

## 4.6 outputs/
Contains:
- report exports,
- generated visual artifacts,
- scenario outputs,
- PDFs.

---

# 5. API DESIGN (CURRENT + FUTURE)

## 5.1 Current Endpoints

### /predict
Purpose:
- direct valuation prediction.

Input:
- property attributes.

Output:
- model prediction.

### /valuate
Purpose:
- main seller-side API endpoint.

Current role:
- runs PIE,
- runs FPI,
- adds market intelligence,
- runs decision engine,
- runs scenario engine,
- returns final seller-ready response.

### /chat
Purpose:
- context-aware AI assistant.

Input:
- message,
- seller context.

Output:
- natural language explanation.

### /market-intelligence
Purpose:
- returns market intelligence output only.

### /decision
Purpose:
- returns decision engine output and related valuation/market details.

### /report
Purpose:
- static report endpoint / prototype report output.

## 5.2 Future Endpoint Intentions
Possible future endpoints:
- /evaluate-property
- /investment-decision
- /aircs-score

These are conceptually part of the broader platform but not the current primary seller-first flow.

---

# 6. DATABASE DESIGN

## 6.1 Current State
The current system relies on:
- dataset files,
- runtime transformations,
- local inference,
- no persistent production database in the implemented core flow.

## 6.2 Future Tables
Planned relational structure:

### properties
Stores property metadata:
- location
- size
- room counts
- quality
- year built
- seller data

### inspections
Stores inspection / condition data:
- risk levels
- structural notes
- AIRCS-like signals

### transactions
Stores sale/listing/decision events:
- pricing history
- recommendation history
- closing outcomes

### features
Stores engineered features and derived signals:
- price gap,
- demand,
- liquidity,
- segment,
- score values.

## 6.3 Relationship Logic
- properties can have many inspections,
- properties can have many transaction events,
- properties can have multiple feature snapshots,
- scenario records can be attached to a property and a decision event.

---

# 7. CORE FEATURES IMPLEMENTED

## 7.1 FPI / Seller Valuation
### Logic
Predict the fair market value of the property and derive seller-oriented pricing guidance.

### Outputs
- fair_price
- recommended_price
- market_range
- listing_range
- price_position
- confidence_score
- risk_level

### Interpretation
The system moved from “predicted price” to “fair price” language to fit seller-side language and Rezerva alignment.

---

## 7.2 Market Intelligence
### Logic
Assign context to the valuation:
- demand pressure,
- liquidity,
- market segment,
- macro signal.

### Outputs
- market_segment
- demand_pressure
- liquidity
- market_context
- macro_signal
- market_strength

---

## 7.3 Decision Engine
### Logic
The seller decision is computed from:
- price position,
- demand pressure,
- risk level,
- market signals.

### Final Working Logic
The decision system evolved to a scoring model where:
- pricing position contributes one component,
- demand contributes one component,
- risk contributes one component,
- final score maps to a seller action.

### Outputs
- decision
- decision_score
- decision_reason
- seller_action

---

## 7.4 Scenario Simulation
### Logic
The scenario engine reruns the valuation/decision path with modified price inputs.

### Outputs
- scenario_price_position
- scenario_decision
- scenario_explanation
- scenario score / comparison logic

### Value
Allows a seller to test how different price choices affect the recommended strategy.

---

## 7.5 AI Assistant
### Logic
Uses structured seller context in the prompt, rather than a generic chat message.

### Outputs
- human readable answer,
- seller-focused explanation,
- context-aware reasoning.

### Important Design Choice
The assistant was updated so that vague questions like “hey” do not get rejected when seller context exists.

---

## 7.6 Explainability
Explainability is implemented through:
- price explanation,
- position explanation,
- risk explanation,
- decision_reason,
- scenario explanation,
- AI natural language output.

---

# 8. FINAL CODE STATE

## 8.1 Decision Function State
Current logic is seller-focused and should use:
- price_position from valuation,
- demand_pressure from market intelligence,
- risk_level from valuation,
- scenario-specific fields if applicable.

## 8.2 Confidence Calculation
Confidence is derived from the combination of:
- AIRCS-like quality/risk signal,
- ROI absolute value in earlier versions,
- later reduced toward a seller-confidence interpretation.

## 8.3 Scenario Logic
Current scenario logic is based on:
- user-adjusted price,
- recalculated valuation,
- updated decision.

## 8.4 Rule About Outdated Code
Outdated buyer-centric or duplicate logic should not be reintroduced.
Use the latest seller-first architecture.

---

# 9. CONFIGURATION & ENVIRONMENT

## 9.1 Frontend Setup
Typical:
- npm install
- npm run dev

## 9.2 Backend Setup
Typical:
- create venv
- install dependencies
- run FastAPI with uvicorn

Example:
```bash
uvicorn main:app --reload
```

## 9.3 Required Dependencies
### Backend
- fastapi
- uvicorn
- pydantic
- scikit-learn
- pandas
- numpy
- google-genai or equivalent SDK

### Frontend
- react
- react-router-dom
- axios
- framer-motion
- html2canvas
- jspdf

---

# 10. PROBLEMS & SOLUTIONS

## 10.1 Graph / UI Bug
A dashboard graph / display issue was encountered earlier.

### Root Cause
Incorrect rendering assumptions or incomplete data coupling.

### Fix
Adjusted display logic and stabilized the output paths.

## 10.2 Decision Rendering Bug
Sometimes decision output was showing raw objects or inconsistent values.

### Root Cause
Wrong variable passed into decision formatting / prompt context.

### Fix
Decision engine now extracts only:
- price_position,
- demand_pressure,
- risk_level,
and generates clean output.

## 10.3 AI Context Bug
The assistant initially rejected vague messages.

### Root Cause
Prompt rules were too strict and context was not treated as dominant.

### Fix
Updated AI prompt:
- if context exists, always answer using it.

## 10.4 Scenario No-Response Bug
The scenario button initially did nothing.

### Root Cause
Scenario state was null / blocked by guard logic.

### Fix
Initialized scenario price and used a safe fallback price variable.

## 10.5 Index / Map Error
A React render error occurred when `index` was referenced incorrectly.

### Root Cause
A variable was used outside its mapping scope.

### Fix
Rewrote the list rendering to avoid relying on a missing `index`.

## 10.6 Overestimation / Decision Stability
When scenario values changed, the result sometimes did not change enough.

### Root Cause
Thresholds for price position were too weak.

### Fix
Scenario and valuation logic were adjusted to make price position more dynamic.

---

# 11. DATA / AI WORK

## 11.1 Dataset
The project uses the Ames Housing dataset as the base ML dataset.

## 11.2 Feature Engineering
Features used or considered:
- living area,
- quality,
- year built,
- total rooms,
- condition,
- basement / garage features,
- engineered combinations for richer model behavior.

## 11.3 Model Performance
Ames model performance should be documented with:
- MAE,
- R²,
- and any model comparison results.

If exact values are not already finalized in the report, they should be inserted from the latest notebook evaluation and not guessed.

## 11.4 Improvements
The model was later adapted from generic “investment” style language to:
- seller fair price,
- seller risk,
- seller action.

---

# 12. CURRENT SYSTEM STATE

## 12.1 Completed
- Seller-first pivot
- FPI valuation module
- Market intelligence layer
- Decision engine
- Scenario simulation
- AI context assistant
- Seller portal
- Reports / PDF export
- Rezerva alignment documentation

## 12.2 In Progress
- Explainability upgrades
- More advanced market signals
- Production-grade database design
- richer feature engineering

## 12.3 Not Started / Future
- live external market data integration
- full deployment architecture
- Codex transition / productionization
- InspectOS and Market Wind full integration
- agent role / multi-stakeholder complete implementation

---

# 13. NEXT STEPS

## 13.1 Immediate
- keep current seller-first architecture stable,
- ensure all outputs stay consistent,
- avoid reintroducing buyer-seller mixing.

## 13.2 Mid-Term
- improve feature engineering,
- add better market signals,
- add richer explainability outputs.

## 13.3 Long-Term
- real data integration,
- API-driven market intelligence,
- production deployment,
- full Rezerva ecosystem integration,
- transition to Codex for deployment.

---

# 14. ASSUMPTIONS & CONSTRAINTS

- The system is still based on a simulated / prototype dataset.
- Cost modeling is simplified.
- Real-time external market data is not yet integrated.
- Some future Rezerva concepts are design-aligned but not fully productionized.
- The current focus remains seller-first.

---

# 15. CONTEXT CONTINUITY NOTES

This must be remembered in the next conversation:

- The system is **multi-model**, not a single ML model.
- Outputs are **decision-driven**, not just predictive.
- **Explainability is required**.
- The project is an **infrastructure component**, not just a model demo.
- PIE is aligned with **Rezerva** and the **seller-first workflow**.
- PropCheck remains the secondary buyer module.
- Avoid mixing buyer and seller outputs.
- Keep the final output structured, seller-facing, and product-level.

---

# 16. FINAL SYSTEM STATEMENT

PIE has evolved from a buyer-oriented prototype into a seller-first, Rezerva-aligned real estate intelligence engine that combines valuation, market intelligence, decision logic, scenario testing, and AI-based explanation into a single modular platform.

This is the current technical and product state that the next chat should continue from without re-explaining the architecture from scratch.
