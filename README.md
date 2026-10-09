# Causal Inference: Bangladesh Early Childhood Stimulation Program

## Overview
This project analyzes the potential impact of an early childhood stimulation program in Bangladesh using baseline and endline survey data.

## Objectives
- Understand the dataset and its structure.
- Analyze baseline characteristics of treatment and control groups.
- Estimate treatment effects using ANCOVA.
- Evaluate cognitive and language development outcomes.

## Dataset
The analysis uses baseline and endline survey data from the Bangladesh Early Childhood Stimulation Program.

## Methodology
- Data cleaning and preprocessing
- Exploratory Data Analysis (EDA)
- Baseline group comparison
- Analysis of Covariance (ANCOVA)
- Cluster-robust standard errors

## Preliminary Results
- **Cognitive outcome:** Treatment effect = +0.7668; p-value = 0.2915.
- **Language outcome:** Treatment effect = +2.1470; p-value = 0.0237.

These estimates are preliminary. Outcome-scale comparability and model specifications require further verification.

## Project Structure
- `data/` — Dataset files
- `notobooks/` — Jupyter notebooks
- `README.md` — Project documentation

## Tools
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Statsmodels
- Jupyter Notebook

## Limitations
- Baseline and endline outcome definitions require further verification.
- Union categories differ from those described in the published report.
- Results should not be interpreted as definitive causal estimates until these issues are resolved.

## Author
Sih-ab (MD. Sihab Hossen)

GitHub: https://github.com/Sih-ab