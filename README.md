
# Human Supervision of Multi-Agent Reinforcement-Learning Teams:
## Selecting Teams across Environments with Varying Risk of Stag Illness


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

### 1. Data Import and Cleaning

- Excel sheets imported using `readxl`
- Column names cleaned using `janitor::clean_names()`
- Numeric variables coerced where needed
- Missing values handled as `NA`

### 2. Descriptive Statistics

- Means
- Standard deviations
- Sample sizes by condition

### 3. Inferential Statistics

- One-way ANOVA
- Tukey HSD post-hoc tests
- Levene’s test
- Shapiro-Wilk test
- Bayesian ANOVA

### 4. NASA-TLX Subscale Analysis

The following workload dimensions were analysed:

- Mental demand
- Physical demand
- Temporal demand
- Performance
- Effort
- Frustration

### 5. Correlation Analysis

Pearson correlations were calculated between:

- Performance score
- NASA-TLX total
- SART total
- Choice accuracy
- Response time

### 6. Reliability Analysis

- Cronbach’s alpha for NASA-TLX subscales

---

## Key Findings

- **Performance** was highest in the **Extreme Stag (R)** condition.
- **Situation awareness** was higher in the **Ambiguous (O)** and **Extreme Stag (R)** conditions than in **Extreme Hare (E)**.
- **NASA-TLX total workload** did not differ significantly across conditions.
- **Effort** differed significantly across conditions.
- **Performance score** was positively correlated with **choice accuracy**.
- **Response time** was negatively correlated with **choice accuracy**.
- NASA-TLX demonstrated acceptable internal consistency reliability.

---

## How to Run the Analysis

### 1. Open the R Script

Load the analysis script in R or RStudio.

### 2. Set the File Path

Update the Excel file path in the script:

```r
file_path <- "C:/Users/brian/Downloads/Copy of Expt2_final.xlsx"
````

### 3. Run the Script

Execute the script section by section, or run the entire script at once.

---

## Expected Outputs

The script produces:

* Summary tables
* ANOVA tables
* Tukey post-hoc results
* Bayesian ANOVA output
* Correlation matrices
* Boxplots
* Violin plots
* Bar plots
* Reliability statistics

---

## File Structure

```text
project/
│
├── data/
│   └── Copy of Expt2_final.xlsx
│
├── scripts/
│   └── analysis.R
│
├── output/
│   ├── tables/
│   └── figures/
│
└── README.md
```

---

## Notes

* Some imported values were converted from character to numeric.
* Missing values introduced during coercion were handled as `NA`.
* The study used a within-subjects design with repeated environment conditions.
* Statistical significance was assessed at **α = 0.05**.

---

## Project Description (300 Characters)

This project investigates how human supervisors select between specialist and adaptive multi-agent reinforcement-learning teams across environments with varying stag illness risk, examining performance, workload, situation awareness, choice accuracy, and decision-making behaviour using R.

---

## Citation Reminder

If this README is used in a report or repository, include the full reference list in the project documentation or appendix.

```
```
