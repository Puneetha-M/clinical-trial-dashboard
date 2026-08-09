# Oncology Clinical Research: Global Operations & Predictive Analytics

A Predictive Intelligence Framework built on 38,900+ public oncology clinical trial records from ClinicalTrials.gov — combining Tableau Prep data engineering, Python machine learning, and live TabPy integration to address the "Recruitment Chasm": the systemic problem where nearly 80% of clinical trials fail to meet enrolment timelines.

Built as part of MSc Data Analytics coursework (Visualisation & Storytelling using Tableau) at BSBI Berlin, 2026.

---

## The Problem

Clinical trial recruitment failure is a billion-dollar bottleneck in oncology drug development. Sponsors commit capital to trials that chronically underperform on enrolment — not because the science fails, but because operational risk goes undetected until delays have already compounded. This framework was designed to change that: moving from reactive reporting to proactive, predictive decision support.

---

## Framework Architecture — Three Pillars

### Pillar I — Data Engineering (Tableau Prep)
- Complex ETL pipeline cleaning and harmonising 38,900+ ClinicalTrials.gov records
- Anomaly mitigation: excluded placeholder dates (e.g. 1900-01-01) that would have invalidated duration calculations
- Feature engineering: derived `Trial Duration (Days)` as a core operational KPI
- Data harmonisation: standardised phase naming conventions into a single `Phases (Clean)` dimension for cross-regional comparison

### Pillar II — Data Science (Python + TabPy)
- Trained a **Logistic Regression model** in Python (Jupyter) on cleaned trial data to identify the primary drivers of trial completion
- Key finding: Phase maturation coefficient of **3.85** — Phase 3 trials have a 31% predicted success probability vs. 15% in Early Phase 1
- Embedded Python-derived Sigmoid function coefficients directly into Tableau calculated fields, enabling dynamic real-time success probability scoring as dashboard filters change
- **TabPy integration**: custom Python script normalises patient enrolment volume against trial duration in real-time, classifying each trial site into: **At Risk / High Efficiency / Standard**
- **825 trials identified as At Risk** — providing immediate, actionable recruitment intervention targets

### Pillar III — Business Intelligence (Tableau Visualisation)
Eight specialist visualisations, two dashboards, and two story points designed for both executive and operational stakeholders.

---

## Dashboard Screenshots

### Dashboard 1 — Global Oncology Research & Success Intelligence Suite
![Global Dashboard Overview](images/dashboard_overview.png)
*Executive command centre: Global Footprint Map (master geographic filter), Predictive Success Probability Heatmap, Portfolio Status Audit across 38,900 trials, Oncology Research Growth Trend, and Top Sponsors by Trial Volume. Clicking a country on the map triggers a global filter that instantly recalibrates all other views for that region.*

---

### Dashboard 2 — Operational Performance & Site Clustering
![Operational Risk Dashboard](images/site_clustering.png)
*Operational deep-dive for project managers: Strategic Phase Maturation box plot (log scale), Predictive Site Performance scatter (enrollment vs. duration with linear trend benchmark), and the TabPy-powered Efficiency Density Heat Map showing the 825 At Risk trials in real-time RAG classification.*

---

### Portfolio Status Audit
![Portfolio Status Audit](images/portfolio_audit.png)
*38,900 trials structured by study status: 17,064 Completed, 6,779 Recruiting, 4,320 Terminated. The donut anchor acts as the mathematical zero point against which all model-driven probabilities are benchmarked.*

---

## The Eight Visualisations

| # | Chart | Purpose |
|---|---|---|
| 1 | Global Footprint Map | Choropleth geographic filter — US and China lead volume; European corridors growing |
| 2 | Predictive Success Probability Heatmap | Logistic Regression output by Phase × Sex — Phase 3 anchors at 31% success |
| 3 | Oncology Research Growth Trend | 20-year dual-line temporal view — validates why predictive intelligence is needed |
| 4 | Strategic Phase Maturation Box Plot | Log-scale enrollment variance across phases — reveals "Enrollment Dispersion" |
| 5 | Predictive Site Performance Scatter | Enrollment vs. duration with linear trend benchmark — sites above line flagged |
| 6 | Efficiency Density Heat Map | TabPy RAG classification — At Risk / High Efficiency / Standard in real-time |
| 7 | Portfolio Status Audit Donut | 38,900-trial health check anchoring all probability metrics |
| 8 | Top Sponsors by Trial Volume | Institutional Concentration analysis — M.D. Anderson (1,002), NCI (998) lead |

---

## Key Findings

- **825 trials currently At Risk** of recruitment failure — identified via real-time TabPy classification
- **Phase 3 maturation is the primary success driver** — Logistic Regression coefficient of 3.85, 31% predicted success probability
- **Capacity Gap confirmed**: Phase 3 has the highest average enrollment per trial but significantly fewer trials than Phase 2 — high failure rate at the Phase 2→3 transition
- US and China dominate trial volume, but European research corridors are growing substantially
- Institutional concentration: the top 2 sponsors (M.D. Anderson + NCI) alone account for 2,000 trials

---

## Tech Stack

- **Tableau Desktop** — 8 worksheets, 2 dashboards, 2 story points
- **Tableau Prep Builder** — ETL pipeline, data cleaning, feature engineering
- **TabPy** — live Python-Tableau integration for real-time recruitment risk classification
- **Python (Jupyter Notebook)** — Logistic Regression, Sigmoid function, data preprocessing
- **Advanced Excel** — Pivot table + combo chart for longitudinal supply-demand variance audit
- **Data source**: ClinicalTrials.gov public registry (38,900+ oncology trial records)

---

## Data Source

All data sourced from [ClinicalTrials.gov](https://clinicaltrials.gov) public registry. No patient-level data used. All records are de-identified public trial metadata.

---

## Author

**Puneetha** — Medidata Rave Certified Study Builder | MSc Data Analytics @ BSBI Berlin
[LinkedIn](https://www.linkedin.com/in/puneetham/) | [GitHub](https://github.com/Puneetha-M)
