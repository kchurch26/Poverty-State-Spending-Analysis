# Poverty Rate Analysis: Public Assistance Spending, Education, and Cost of Living
State-level OLS regression analysis examining public assistance spending, education rates, and cost of living as predictors of poverty rates using 2022 Census and C2ER data in R.

## Overview
This project examines whether state-level public assistance spending, 
educational attainment rates, and cost of living are associated with 
poverty rates across the 50 U.S. states. Analysis is conducted using 
2022 data and an OLS multiple regression model in R.

## Research Question
Do states that spend more on public assistance, have higher educational 
attainment, or face higher costs of living tend to have lower poverty rates?

## Data Sources
- **Poverty rates**: U.S. Census Bureau, American Community Survey (ACS) 
5-Year Estimates, 2022 — accessed via `tidycensus` API
- **Public welfare spending**: U.S. Census Bureau, State & Local Government 
Finance Historical Datasets, 2022
- **Educational attainment**: U.S. Census Bureau, ACS 5-Year Estimates, 
2022 — accessed via `tidycensus` API
- **Cost of Living Index**: Council for Community and Economic Research 
(C2ER), 2022

## Methods
- Data cleaning and merging across four sources using `tidyverse` and 
`dplyr`
- OLS multiple linear regression: `poverty_rate ~ Spending + 
education_rate + Cost of Living Index`
- State-level unit of analysis (n = 50)

## Key Findings
- **Public assistance spending** shows a positive association with poverty 
rates — likely reflecting that higher-poverty states allocate more spending 
in response to need, not causality
- **Cost of living** is negatively associated with poverty rates (p = 0.037), 
though this counterintuitive result warrants further examination of wage 
levels and purchasing power
- **Education rate** was not statistically significant (p = 0.667), raising 
questions about lag effects and labor market mediators

## Limitations
Model does not establish causality. Future work could address 
multicollinearity, confounding variables, and longitudinal data to better 
isolate education's long-term impact on poverty reduction.

## Tools
R | tidyverse | tidycensus | dplyr | knitr

## Files
| File | Description |
|------|-------------|
| `povertyspendinganalysis.Rmd` | Full R Markdown source with code and 
narrative |
| `povertyspendinganalysis.pdf` | Knitted PDF output (if available) |
```

---

**One flag:** your .Rmd has two hardcoded local file paths for the spending and COLI data:
```
/Users/k.churchill22/Library/CloudStorage/...
