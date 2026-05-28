# Human Supervision of Multi-Agent Reinforcement-Learning Teams:
## Selecting Teams across Environments with Varying Risk of Stag Illness

**Student name:**  
**Date:** 2026-01-11

---

## Overview

This project examines how human supervisors select between three pre-trained multi-agent reinforcement-learning (MARL) teams across environments with different probabilities of stag illness:

- **Extreme Hare (E)** — low stag reward / risk-averse setting  
- **Ambiguous (O)** — mixed/uncertain setting  
- **Extreme Stag (R)** — high stag reward / reward-seeking setting  

The study evaluates:

- **Performance score**
- **Choice accuracy**
- **Response latency**
- **Team-selection clicks**
- **NASA-TLX workload**
- **SART situation awareness**

The analysis tests whether supervisors perform better in clear environments, whether adaptive teams are preferred in ambiguous settings, and how workload and situation awareness relate to performance.

---

## Research Questions / Hypotheses

- **H1:** Accuracy and performance are better in extreme environments than in the ambiguous environment.
- **H2:** The adaptive **DisAdv** team is selected more often in the ambiguous environment.
- **H3:** Selection latency is longer in the ambiguous environment.
- **H4:** Choice accuracy is positively related to situation awareness, while response time is negatively related to situation awareness.
- **H5:** Workload is higher in the ambiguous setting and negatively related to choice accuracy.

---

## Data Sources

The analysis uses data from an Excel workbook:

- `Workload`
- `SA`
- `FullData`
- `FullData2`

The workbook contains participant-level data for:

- NASA-TLX subscales and total workload
- SART scores
- Performance scores
- Choice accuracy
- Response time
- Team selection activity

---

## Software and Packages

The analysis was completed in **R** using the following packages:

- `tidyverse`
- `janitor`
- `skimr`
- `lme4`
- `lmerTest`
- `BayesFactor`
- `psych`
- `polycor`
- `reshape2`
- `readxl`
- `kableExtra`
- `car`
- `effectsize`
- `broom`
- `ggplot2`

---

## Main Analyses

1. **Data import and cleaning**
   - Excel sheets imported with `readxl`
   - Column names cleaned with `janitor::clean_names()`
   - Numeric variables coerced where needed

2. **Descriptive statistics**
   - Means
   - Standard deviations
   - Sample sizes by condition

3. **Inferential statistics**
   - One-way ANOVA
   - Tukey HSD post-hoc tests
   - Levene’s test
   - Shapiro-Wilk test
   - Bayesian ANOVA

4. **Subscale analysis**
   - NASA-TLX subscales:
     - mental demand
     - physical demand
     - temporal demand
     - performance
     - effort
     - frustration

5. **Correlation analysis**
   - Pearson correlations between:
     - performance
     - NASA-TLX total
     - SART total
     - choice accuracy
     - response time

6. **Reliability**
   - Cronbach’s alpha for NASA-TLX subscales

---

## Key Findings

- **Performance** was highest in the **Extreme Stag (R)** condition.
- **Situation awareness** was higher in the **Ambiguous (O)** and **Extreme Stag (R)** conditions than in **Extreme Hare (E)**.
- **NASA-TLX total workload** did not differ significantly across conditions.
- **Effort** differed significantly across conditions.
- **Performance score** was positively correlated with **choice accuracy**.
- **Response time** was negatively correlated with **choice accuracy**.
- NASA-TLX showed acceptable internal consistency.

---

## How to Run the Analysis

### 1. Open the R script
Load the analysis script in R or RStudio.

### 2. Set the file path
Update the Excel file path in the script:

```r
file_path <- "C:/Users/brian/Downloads/Copy of Expt2_final.xlsx"
