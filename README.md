Oncology Clinical Research: Global Operations & Predictive Analytics

A Predictive Intelligence Framework built on 38,900+ public oncology clinical trial records from ClinicalTrials.gov — combining Tableau Prep data engineering, Python machine learning, and live TabPy integration to address the "Recruitment Chasm": the systemic problem where nearly 80% of clinical trials fail to meet enrolment timelines.

Built as part of MSc Data Analytics coursework (Visualisation & Storytelling using Tableau) at BSBI Berlin, 2026.

The Problem

Clinical trial recruitment failure is a billion-dollar bottleneck in oncology drug development. Sponsors commit capital to trials that chronically underperform on enrolment — not because the science fails, but because operational risk goes undetected until delays have already compounded. This framework was designed to change that: moving from reactive reporting to proactive, predictive decision support.

Framework Architecture — Three Pillars
Pillar I — Data Engineering (Tableau Prep)
Complex ETL pipeline cleaning and harmonising 38,900+ ClinicalTrials.gov records
Anomaly mitigation: excluded placeholder dates (e.g. 1900-01-01) that would have invalidated duration calculations
Feature engineering: derived Trial Duration (Days) as a core operational KPI
Data harmonisation: standardised phase naming conventions into a single Phases (Clean) dimension for cross-regional comparison
Pillar II — Data Science (Python + TabPy)
Trained a Logistic Regression model in Python (Jupyter) on cleaned trial data to identify the primary drivers of trial completion
Key finding: Phase maturation coefficient of 3.85 — Phase 3 trials have a 31% predicted success probability vs. 15% in Early Phase 1
Embedded Python-derived Sigmoid function coefficients directly into Tableau calculated fields, enabling dynamic real-time success probability scoring as dashboard filters change
TabPy integration: custom Python script normalises patient enrolment volume against trial duration in real-time, classifying each trial site into: At Risk / High Efficiency / Standard
825 trials identified as At Risk — providing immediate, actionable recruitment intervention targets
Pillar III — Business Intelligence (Tableau Visualisation)

Eight specialist visualisations, two dashboards, and two story points designed for both executive and operational stakeholders.
