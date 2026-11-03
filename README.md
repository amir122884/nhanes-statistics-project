# PROJECT CARD

## Project Title

Depressive Symptoms and Obesity-Related Measures Among Adults in NHANES 2021–2023

## Dataset and Subset

- **Dataset:** NHANES 2021–2023
- **Path:** Dataset A — NHANES
- **Files:** DEMO_L, DPQ_L, BMX_L, BPXO_L
- **Analytical subset:** Adults aged 20 years and older
- **Main analytical sample:** 6,064 participants with records in all four files

## Main Research Question

Among adults aged 20 years and older in NHANES 2021–2023, what is the association between depressive symptoms, measured by the PHQ-9 score, and obesity-related measures, particularly BMI and waist circumference?

Blood pressure is considered a secondary health outcome.

## Population and Unit of Observation

- **Target population:** Adults aged 20 years and older in the U.S. civilian noninstitutionalized population.
- **Unit of observation:** Individual NHANES participant.
- **Identifier:** SEQN.
- **Study design:** Cross-sectional observational survey.

Each row in the analytical dataset represents one participant.

## Variable Roles and Measurement Scales

| Variable | Measurement scale | Role |
|---|---|---|
| PHQ-9 total score | Discrete quantitative | Main explanatory variable |
| BMI | Continuous quantitative | Primary outcome |
| Waist circumference | Continuous quantitative | Secondary outcome |
| Systolic blood pressure | Continuous quantitative | Secondary outcome |
| Diastolic blood pressure | Continuous quantitative | Secondary outcome |
| Age | Discrete quantitative | Demographic variable |
| Sex | Nominal categorical | Demographic variable |
| Race/ethnicity | Nominal categorical | Demographic variable |
| Education | Ordinal categorical | Demographic variable |
| Income-to-poverty ratio | Continuous quantitative | Potential adjustment variable |

## Type of Statistical Question

Primarily an associational and descriptive question.

## Initial Hypothesis

No formal statistical hypothesis was specified before the exploratory analysis. The initial investigation is descriptive and exploratory. Formal null and alternative hypotheses are reserved for Phase 3.

## Sampling and Weighting

NHANES uses a complex multistage probability sampling design. The project uses the MEC examination weight (`WTMEC2YR`) for analyses combining interview and MEC measurements. The design variables `SDMVSTRA` and `SDMVPSU` are retained for subsequent design-based variance estimation.

## Initial Limitations

1. The cross-sectional design does not establish temporal order or causality.
2. Missing values reduce the number of participants available for analyses involving multiple variables.
3. Some PHQ-9 severity groups contain relatively few participants.
4. PHQ-9 measures depressive symptoms and is not a clinical diagnosis.
5. Population estimates require appropriate survey weights and design information.

## Phase 1 Scope

Data source identification, sample construction, data quality assessment, missingness analysis, frequency tables, descriptive statistics, exploratory visualizations, descriptive group comparisons, and weighted versus unweighted obesity prevalence.