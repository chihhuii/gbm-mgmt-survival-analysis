# GBM MGMT Expression & Survival Analysis

Analysis of **MGMT mRNA expression** in glioblastoma (GBM) patients using publicly available TCGA data, including demographic associations and Cox proportional hazards survival modeling.

---

## Overview

Glioblastoma multiforme (GBM) is an aggressive primary brain tumor with poor prognosis. MGMT (O6-methylguanine-DNA methyltransferase) is a DNA repair enzyme and a widely studied prognostic biomarker in GBM. This project investigates how MGMT expression relates to patient demographics and overall survival using real-world cancer genomics data.

---

## Data

- **Source:** [TCGA PanCancer Atlas GBM cohort](https://www.cbioportal.org/) via cBioPortal (publicly available)
- **Dataset:** 100 primary GBM patients after filtering
- **Key variables:** MGMT mRNA expression (z-score), age at diagnosis, sex, overall survival time and status

---

## Analyses

### Part I – MGMT Expression & Demographics
- Pearson correlation + simple linear regression (MGMT vs. age)
- Welch's t-test + Wilcoxon rank-sum test (MGMT vs. sex)

### Part II – Survival Analysis
- Kaplan–Meier survival curves + log-rank test
- Multivariable **Cox proportional hazards model** (MGMT expression, age, sex)
- Post hoc power / sample size calculation

---

## Key Findings

- MGMT expression was **not significantly associated** with age or sex
- MGMT-high group showed a trend toward **worse survival** (HR ≈ 1.56), though borderline significant (p ≈ 0.074)
- **Age** was a robust independent predictor of mortality (HR ≈ 1.03/year, p < 0.01)
- Study was underpowered (n = 100); ~224 patients needed for 80% power at the observed effect size

---

## Tools & Packages

| Tool | Purpose |
|------|---------|
| R | Primary analysis environment |
| `survival` | Cox model, Kaplan–Meier (`coxph`, `survfit`) |
| `survminer` | Survival curve visualization (`ggsurvplot`) |
| `dplyr` | Data manipulation |

---

## Files

| File | Description |
|------|-------------|
| `GBM_MGMT_analysis.Rmd` | Full R Markdown analysis (source) |
| `GBM_MGMT_analysis.html` | Rendered report (open in browser) |
| `GBM_MGMT_final_dataset.csv` | Cleaned dataset used for analysis |

> 💡 To view the rendered report, download `GBM_MGMT_analysis.html` and open it in your browser.

---

## Academic Context

This project was completed as a final project for BIOL5312 (Biostatistics), December 2025.
