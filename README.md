# Medicare Physician Billing Patterns in RI and NH (2022–2023)

**Author**: Shan Aziz  

## Overview

This project analyzes Medicare billing patterns among physicians in **Rhode Island (RI)** and **New Hampshire (NH)** using CMS public datasets for the years 2022 and 2023. The analysis focuses on consistent billing behavior, state-level differences, and specialty-based payment patterns.

## Objectives

- Compare total **submitted** and **allowed** charges by state and year.
- Identify the **top 3 most common physician specialties** in each state.
- Run a **regression model** to test state-level differences in allowed charges.
- Measure **correlation** between 2022 submitted and 2023 allowed charges.

## Data Source

- CMS Medicare Physician & Other Practitioners by Provider (2022–2023)  
  (https://data.cms.gov/provider-summary-by-type-of-service/medicare-physician-other-practitioners/medicare-physician-other-practitioners-by-provider)

## Key Findings

### 🔹 Summary Statistics

| State | Year | Avg Submitted Charges | SD | Avg Allowed Charges | SD |
|-------|------|------------------------|----|----------------------|----|
| NH    | 2022 | $461,375              | $693,319 | $110,174            | $210,611 |
| NH    | 2023 | $472,662              | $712,272 | $107,527            | $225,651 |
| RI    | 2022 | $276,442              | $416,372 | $86,406             | $138,214 |
| RI    | 2023 | $299,083              | $477,989 | $86,784             | $144,684 |

- NH physicians submit ~50–70% more in charges than RI.
- Allowed charges remain relatively stable across both states.

### 🔹 Top 3 Specialties (Proportion of Total)

**New Hampshire**  
- Internal Medicine (43.3%)  
- Family Practice (38.3%)  
- Emergency Medicine (18.5%)

**Rhode Island**  
- Internal Medicine (61.8%)  
- Emergency Medicine (22.0%)  
- Family Practice (16.1%)

### 🔹 Regression Results

A linear regression of total allowed charges shows:

- RI physicians receive **$19,083 less** on average compared to NH (p < 0.001)
- Highest earning specialties (controlled for state and year):
  - **Micrographic Dermatologic Surgery**: +$542,259
  - **Medical Oncology**: +$326,825
  - **Dermatology**: +$267,077

Adjusted R² = **0.1865** (19% variance explained)

### 🔹 Correlation Analysis

- **r = 0.696** between 2022 submitted and 2023 allowed charges  
  → Indicates moderately strong year-to-year billing consistency.

## Technologies Used

- **R** (Data Wrangling, Visualization, Statistical Modeling)
- Libraries: `dplyr`, `ggplot2`, `tidyr`, `broom`, `patchwork`, `readr`, `kable`

## Visualization Highlights
📊 Bar charts showing mean and standard deviation of charges by state and year

🥧 Pie charts comparing specialty distributions between RI and NH

📈 Regression tables and coefficient breakdowns

## How to Use
- Clone the repository.
- Download the CMS data files for 2022 and 2023.
- Run the R script provided in the RMarkdown or source code.
- Ensure dependencies are installed using install.packages().
