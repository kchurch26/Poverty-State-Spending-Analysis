# Poverty Rate Analysis: Public Assistance Spending, Education, and Cost of Living

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

## Data Access
The following datasets are required to reproduce this analysis and must be 
downloaded separately:

- **Public welfare spending**: Download from the U.S. Census Bureau, 
[State & Local Government Finance Historical Datasets and Tables](https://www.census.gov/data/datasets/2022/econ/local/public-use-datasets.html) 
(2022). Filter for "Public Welfare" expenditures by state.

- **Cost of Living Index**: Download from the Council for Community and 
Economic Research (C2ER) at [coli.org](https://www.coli.org). 
2022 state-level index data required.

- **Poverty and education data**: Pulled directly via the `tidycensus` 
R package using the U.S. Census Bureau API. A free API key is required — 
register at [api.census.gov](https://api.census.gov/data/key_signup.html).

Once downloaded, update the file paths in the `.Rmd` file to match your 
local directory before running.

## Tools
R | tidyverse | tidycensus | dplyr | knitr

## Files
| File | Description |
|------|-------------|
| `povertyspendinganalysis.Rmd` | Full R Markdown source with code and 
narrative |
| `povertyspendinganalysis.pdf` | Knitted PDF output (if available) |
