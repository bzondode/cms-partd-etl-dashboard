# CMS Part D ETL + Streamlit Dashboard (Power BI–Ready Export)

This project builds a reproducible ETL + quality assurance workflow and an interactive Streamlit dashboard using public CMS Medicare Part D Prescribers data. It also produces a cleaned, Power BI–ready CSV for downstream reporting.

## Why this repo
Healthcare analytics work is often less about “one-off analysis” and more about:
- reliable data intake and cleaning,
- defensible QA checks,
- repeatable reporting outputs,
- clear communication through dashboards.

This repo is designed as a lightweight portfolio example of that end-to-end workflow.

## Data source
- CMS: Medicare Part D Prescribers (public use file)

> Note: This dataset is public and aggregated (no PHI). See CMS documentation for definitions and limitations.

## What’s included
- ETL pipeline (raw → cleaned)
- QA checks (schema, nulls, duplicates, basic numeric sanity checks)
- Streamlit dashboard (filters + insight views)
- Export: Power BI–ready CSV

## Outputs
- `exports/partd_powerbi_fact.csv` — cleaned fact table for Power BI
- `exports/partd_summary.csv` — small aggregates for quick reporting

## How to run
1. Create a virtual environment
2. Install dependencies:
   - `pip install -r requirements.txt`
3. Run ETL:
   - `python -m src.etl.run_etl`
4. Run QA:
   - `python -m src.qa.run_qa`
5. Launch the dashboard:
   - `streamlit run app/Home.py`

## Dashboard views (MVP)
- Top drugs by total cost
- Cost per claim by specialty
- Specialty mix and concentration
- State-level comparisons (where available)

## Roadmap
- Add caching and incremental updates
- Add more robust QA (expectations tests)
- Add “briefing deck” export images for leadership-ready summaries

