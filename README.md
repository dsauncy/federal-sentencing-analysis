# Apples to Apples: An Analysis of Geographic Influence in Federal Sentencing

## Overview
Federal sentencing guidelines are intended to create a consistent sentencing structure
nationwide, such that defendants under identical legal factors would receive relatively
similar outcomes regardless of geographic location. For example, a defendant with no
prior criminal history who pleads guilty to a federal offense in Washington should, in
theory, receive a sentence comparable to that of a similarly situated defendant in
Florida pleading guilty to the same federal offense. However, concerns about the United
States’s judicial consistency remain persistent, suggesting that certain geographic
areas are much harsher than others, with documented research supporting this narrative.
This project investigates whether geographic inconsistencies exist that undermine the
uniformity of the federal guidelines, what areas are most prone to deviation, and
whether the results can serve as a meaningful predictor of sentencing outcomes.

## Data Source
United States Sentencing Commission Individual Datafile, FY2024 (October 
2023 – September 2024). Publicly available at 
[ussc.gov](https://www.ussc.gov/research/datafiles/commission-datafiles#individual).  
The raw dataset contains 61,678 cases and 27,265 columns. After isolating 
relevant variables and removing incomplete rows, the working dataframe 
contained 55,759 cases.

## Methodology
- **Framework:** CRISP-DM
- **Model:** OLS Multiple Linear Regression (statsmodels)
- **Dependent variable:** Sentence length in months (log-transformed)
- **Independent variables:** District, offense type, offense level, 
  criminal history category
- **Hypothesis testing:** Overall F-test, restricted F-test, 
  individual district t-tests

## Key Findings
- The model achieved an R² of 0.48, explaining 48% of variance in 
  sentence length
- A restricted F-test confirmed geography explains significant variance 
  beyond legal factors alone (F = 40.30, p < 0.001)
- 70 of 94 districts deviated significantly from the national average
- Most extreme outliers: **Nebraska** (~85% below national average) and 
  **Western Louisiana** (~80% above)
- For otherwise identical cases, district of sentencing can mean the 
  difference between months and years

## Tools & Libraries
Python · pandas · statsmodels · matplotlib · seaborn · plotly · 
Jupyter Notebook · Microsoft Excel · Microsoft Word

## Repository Contents
- `apples_to_apples.ipynb` — Full analysis notebook
- `Apples to Apples.docx` — Analysis report 
