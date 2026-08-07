# Clinical Trial Recruitment & Risk Dashboard

An interactive **Streamlit dashboard** for visualising clinical trial recruitment performance and data quality risk indicators, built on public ClinicalTrials.gov data.

This project grew out of the Tableau/TabPy dashboard I built during my MSc, rebuilt in Python/Streamlit so it's fully open-source and reproducible without a Tableau license.

---

## What It Shows

### Tab 1 — Recruitment Overview
- Enrolment progress vs. target by study and site
- Countries with fastest/slowest enrolment velocity
- Studies at risk of missing recruitment targets (flagged automatically)

### Tab 2 — Site Risk Heatmap
- Site-level risk scoring: enrolment pace, country, site experience
- Red/amber/green RAG status per site
- Drill-down to individual site metrics

### Tab 3 — Query Rate Trends
- Simulated query rate trends over study lifecycle
- Peak query periods (typically post-database lock prep)
- Correlation between visit complexity and query volume

### Tab 4 — Data Quality Flags
- Missing data rates by domain (DM, VS, AE, LB)
- Protocol deviation frequency by site
- Outstanding query age distribution

---

## Tech Stack

- Python 3.10
- Streamlit
- Plotly Express
- Pandas, NumPy
- Requests (ClinicalTrials.gov API)

---

## Quick Start

```bash
git clone https://github.com/Puneetha-M/clinical-trial-dashboard
cd clinical-trial-dashboard
pip install -r requirements.txt
streamlit run app.py
```

Dashboard opens at `http://localhost:8501`

---

## Data Source

Public data from [ClinicalTrials.gov](https://clinicaltrials.gov) via their REST API (`/api/query/full_studies`). No patient-level data is used. Synthetic site-level performance data is generated for the query rate and data quality tabs.

---

## Project Structure

```
clinical-trial-dashboard/
│
├── app.py                   # Main Streamlit app
├── pages/
│   ├── 01_recruitment.py
│   ├── 02_site_risk.py
│   ├── 03_query_trends.py
│   └── 04_data_quality.py
│
├── data/
│   ├── fetch_ctgov.py       # ClinicalTrials.gov API fetch
│   └── synthetic_sites.py   # Synthetic site data generator
│
├── utils/
│   ├── risk_scoring.py      # RAG status logic
│   └── charts.py            # Reusable Plotly chart functions
│
├── requirements.txt
└── README.md
```

---

## Author

**Puneetha** — Medidata Rave Certified Study Builder | MSc Data Analytics @ BSBI Berlin  
[LinkedIn](https://www.linkedin.com/in/puneetham/) | [GitHub](https://github.com/Puneetha-M)
