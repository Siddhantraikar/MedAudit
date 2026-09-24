# MedAudit

An AI system for processing health insurance claims — parses medical documents, detects fraud, and generates pre-authorization decisions automatically.

I built this after noticing how broken the insurance claim process is in India. Most hospitals wait 10–30 days for TPA approvals that involve a lot of manual paperwork. MedAudit tries to automate the repetitive parts of that.

## What it does

- Reads PDF discharge summaries and hospital bills, extracts structured data (ICD codes, amounts, hospital details)
- Runs a fraud detection model on the extracted data — flags suspicious claims with an explanation for each flag
- Validates the claim against policy terms (waiting periods, exclusions, sum insured)
- Generates a pre-authorization decision and audit report

## Tech stack

- **Backend** — Python, FastAPI, pdfplumber, LayoutLM
- **ML** — XGBoost, SHAP for explainability
- **Frontend** — React.js, Recharts
- **Database** — PostgreSQL
- **Deployment** — AWS EC2

## How it works
Hospital PDF
    → Parser (pdfplumber + LayoutLM)
    → Structured JSON
    → Policy validation + Fraud model (XGBoost)
    → Pre-auth decision
    → React dashboard


## Project structure
MedAudit/
├── backend/       FastAPI server, parser, ML pipeline
├── frontend/      React dashboard
├── ml_model/      XGBoost training, SHAP analysis
├── data/sample/   Anonymised sample claim documents
└── docs/          Architecture notes


## Running locally
git clone https://github.com/Siddhantraikar/MedAudit
cd backend
pip install -r requirements.txt
uvicorn main:app --reload


For frontend: `cd frontend && npm install && npm start`

## Current status

Still building this. Here's where things are:

- [ ] PDF parser — extracts structured data from discharge summaries
- [ ] Fraud detection model — XGBoost trained on synthetic claim data
- [ ] Policy validation engine
- [ ] React dashboard
- [ ] AWS deployment

Will update this as I go.

---

Made by [Siddhant Raikar](https://linkedin.com/in/siddhant-raikar) · [GitHub](https://github.com/Siddhantraikar)
