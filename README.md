# NHANES Statistics Project

## Overview

This project investigates the association between depressive symptoms and selected health measurements among adults aged 20 years and older, using data from the NHANES 2021–2023 survey cycle.

The primary research question is:

> Among adults aged 20 years and older in NHANES 2021–2023, what is the association between depressive symptoms, measured by the PHQ-9 score, and obesity-related measures, particularly BMI and waist circumference?

Blood pressure is also examined as a secondary health outcome.

## Data Source

The project uses four publicly available NHANES datasets:

- Demographics (`DEMO_L.xpt`)
- Depression Questionnaire (`DPQ_L.xpt`)
- Body Measures (`BMX_L.xpt`)
- Blood Pressure (`BPXO_L.xpt`)

All data are obtained from the official [NHANES website](https://wwwn.cdc.gov/nchs/nhanes/continuousnhanes/default.aspx?Cycle=2021-2023).

Raw data files are not stored in this repository. See [`data/README.md`](data/README.md) for download links and reconstruction instructions.

## Repository Structure

```text
nhanes-statistics-project/
│
├── data/
│   ├── raw/                  # Downloaded NHANES files (not tracked by Git)
│   └── README.md             # Data source and reconstruction instructions
│
├── notebooks/
│   └── feasibility_check.ipynb
│
├── reports/
│   └── figures/              # Figures generated during the analysis
│
├── PROJECT_CARD.md
├── README.md
└── .gitignore
```

## Analytical Sample

The four-file merged dataset contains 6,064 adults aged 20 years and older.

A separate BMI dataset containing 5,970 participants with valid BMI and MEC examination weights is used for the weighted obesity prevalence comparison.

## Main Variables

- PHQ-9 total score: measure of depressive symptoms.
- BMI: primary health outcome.
- Waist circumference: secondary health outcome.
- Mean systolic and diastolic blood pressure: secondary health outcomes.
- Age, sex, race/ethnicity, education, and income-to-poverty ratio: demographic and socioeconomic variables.

## Reproducibility

1. Clone or download this repository.
2. Download the four required NHANES XPT files using the instructions in [`data/README.md`](data/README.md).
3. Place the downloaded files in `data/raw/`.
4. Install the required Python packages.
5. Open and run `notebooks/feasibility_check.ipynb`.

## Current Project Stage

**Phase 1 – Data Understanding and Exploratory Analysis**

This phase covers data inspection, cleaning, missing-value assessment, descriptive statistics, frequency tables, exploratory visualizations, and an initial comparison of weighted and unweighted obesity prevalence.

Further statistical inference and regression analysis are reserved for subsequent phases.