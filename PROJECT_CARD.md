# Project Card

## Provisional Title

Depressive Symptoms and Obesity-Related Measures Among Adults in NHANES 2021–2023

## Research Question

Among adults aged 20 years and older in NHANES 2021–2023, what is the association between depressive symptoms, measured by the PHQ-9 score, and obesity-related measures, particularly BMI and waist circumference?

Blood pressure is also examined as a secondary health outcome.

## Dataset

- **Source:** National Health and Nutrition Examination Survey (NHANES), 2021–2023 cycle
- **Population of interest:** Adults aged 20 years and older
- **Main analytical dataset:** 6,064 participants with records in the demographic, depression questionnaire, body measurements, and blood pressure files
- **BMI-only dataset for the weighted obesity estimate:** 5,970 participants with non-missing BMI and MEC examination weights

## Variables

| Variable | NHANES variable | Role |
|---|---|---|
| Depressive symptoms | PHQ-9 total score | Main explanatory variable |
| Body mass index | BMXBMI | Primary outcome |
| Waist circumference | BMXWAIST | Secondary outcome |
| Systolic blood pressure | Mean of available BPXOSY readings | Secondary outcome |
| Diastolic blood pressure | Mean of available BPXODI readings | Secondary outcome |
| Age | RIDAGEYR | Demographic variable |
| Sex | RIAGENDR | Demographic variable |
| Race/ethnicity | RIDRETH3 | Demographic variable |
| Education | DMDEDUC2 | Demographic variable |
| Income-to-poverty ratio | INDFMPIR | Potential adjustment variable |

## Initial Analytical Approach

Phase 1 focuses on data understanding, cleaning, missing-value assessment, descriptive statistics, frequency tables, and exploratory visualizations.

The analysis also compares weighted and unweighted estimates of obesity prevalence, using BMI ≥ 30 as the obesity threshold and the MEC examination weight (WTMEC2YR).

## Important Limitations

- NHANES has a complex survey design; population-level estimates and variance calculations must account for the appropriate weights and survey design.
- The current descriptive and exploratory analyses do not establish causality.
- PHQ-9 measures depressive symptoms and is not, by itself, a clinical diagnosis of depression.
- Missing observations may reduce the sample size for analyses involving multiple variables.
- Findings from this cross-sectional dataset should be interpreted as associations rather than causal effects.

## Project Scope

The primary focus is the relationship between PHQ-9 score and BMI. Waist circumference and blood pressure are examined as additional health measures. Further statistical inference and regression analysis are reserved for later project phases.