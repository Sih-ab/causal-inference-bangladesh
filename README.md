# Causal Inference: Bangladesh Early Childhood Stimulation Program

<p align="center">
  <b>Data Science | Causal Inference | Impact Evaluation</b>
</p>

## Overview

This project analyzes the potential impact of an early childhood stimulation program in Bangladesh using baseline and endline survey data.

The analysis focuses on children's cognitive and language development outcomes and examines differences between treatment and control groups.

The project uses Python, Pandas, Statsmodels, and Jupyter Notebook to perform data exploration, baseline comparisons, and preliminary treatment effect estimation.

## Objectives

- Understand and explore the baseline and endline datasets.
- Investigate treatment and control group characteristics.
- Examine child development outcomes.
- Apply Analysis of Covariance (ANCOVA).
- Estimate treatment effects using cluster-robust standard errors.
- Interpret statistical significance and confidence intervals.
- Document methodological limitations and potential improvements.

## Research Questions

1. How do children's cognitive outcomes differ between treatment and control groups?
2. How do children's language outcomes differ between treatment and control groups?
3. Do estimated treatment effects remain after controlling for baseline outcomes?
4. How should clustering and study design be considered when estimating treatment effects?

## Dataset Sources

The project uses data associated with the Bangladesh Early Childhood Stimulation Program impact evaluation.

### 1. Baseline Dataset

- **Source:** World Bank Microdata Library
- **Link:** https://microdata.worldbank.org/catalog/2736

The baseline data contain children's characteristics and developmental assessment variables collected before the endline assessment.

### 2. Endline Dataset

- **Source:** World Bank Microdata Library
- **Link:** https://microdata.worldbank.org/catalog/3415

The endline data contain follow-up information, treatment assignment, and child development outcome variables.

### 3. Official Impact Evaluation Report

- **Source:** World Bank Microdata Library
- **Link:** https://microdata.worldbank.org/catalog/3415/related-materials

The published report provides information about the study design, estimation strategy, treatment effects, and interpretation of the evaluation results.

### Data Access

Please consult the original dataset pages for downloadable files, codebooks, documentation, licensing terms, and citation requirements.

The original data files are not included in this GitHub repository.

Users should obtain the datasets from their official sources and place the required files in the appropriate project directories.

## Methodology

### 1. Data Understanding

The initial analysis examines:

- Dataset dimensions and column names.
- Data types and missing values.
- Treatment and control group counts.
- Child development score distributions.
- Unique child identifiers and community-clinic identifiers.

### 2. Data Preparation

Baseline and endline records are matched using the child identifier `V001`.

An inner join is used to retain children appearing in both datasets.

The merged dataset contains 2,486 matched observations.

Treatment assignment and community-clinic identifiers are checked for consistency across the matched records.

### 3. Baseline Analysis

Baseline characteristics and developmental scores are compared between treatment and control groups.

Preliminary Welch's t-tests are used to investigate differences in baseline scores.

### 4. ANCOVA

Analysis of Covariance (ANCOVA) is used to estimate treatment effects while controlling for baseline outcome scores.

The preliminary model is:

`Endline Outcome = Treatment + Baseline Outcome`

Treatment effects are estimated using ordinary least squares regression.

### 5. Cluster-Robust Standard Errors

Standard errors are clustered at the community-clinic level to account for the clustered study design.

This adjustment is important because observations within the same cluster may not be statistically independent.

### 6. Statistical Inference

The analysis reports:

- Treatment effect estimates.
- Cluster-robust standard errors.
- P-values.
- 95% confidence intervals.

Statistical significance is evaluated at the 5% significance level.

## Preliminary Results

The following estimates come from the preliminary baseline-adjusted ANCOVA models.

| Outcome | Treatment Effect | Cluster-Robust SE | P-value | Interpretation |
|---|---:|---:|---:|---|
| Cognitive | +0.7668 | 0.7269 | 0.2915 | Not statistically significant |
| Language | +2.1470 | 0.9491 | 0.0237 | Statistically significant |

### Cognitive Outcome

The estimated treatment effect is approximately +0.77 points.

The p-value is 0.2915, and the 95% confidence interval includes zero.

Therefore, the preliminary model does not provide sufficient evidence of a statistically significant cognitive effect at the 5% level.

### Language Outcome

The estimated treatment effect is approximately +2.15 points.

The p-value is 0.0237, and the 95% confidence interval excludes zero.

Therefore, the preliminary model indicates a positive and statistically significant language effect at the 5% level.

### Interpretation

These estimates should be treated as preliminary rather than definitive causal estimates.

Outcome definitions, score comparability, and the complete study specification must be verified before drawing final conclusions.

## Project Structure

```text
causal-inference-bangladesh/
│
├── data/
│   └── Original datasets (not included in GitHub)
│
├── notobooks/
│   ├── 01_data_understanding.ipynb
│   └── 02_baseline_analysis.ipynb
│
└── README.md