# NHANES Data Documentation

## Data Source

The data used in this project come from the **National Health and Nutrition Examination Survey (NHANES), 2021–2023**.

NHANES is conducted by the U.S. National Center for Health Statistics (NCHS), part of the Centers for Disease Control and Prevention (CDC).

Official dataset documentation and download pages:

https://wwwn.cdc.gov/nchs/nhanes/continuousnhanes/default.aspx?Cycle=2021-2023

## Required Data Files

The analysis uses the following four XPT files:

| File | Purpose | Main variables used |
|---|---|---|
| `DEMO_L.xpt` | Demographic information and survey design | `SEQN`, `RIDAGEYR`, `RIAGENDR`, `RIDRETH3`, `DMDEDUC2`, `INDFMPIR`, `WTMEC2YR`, `SDMVSTRA`, `SDMVPSU` |
| `DPQ_L.xpt` | Depression questionnaire | `SEQN`, `DPQ010`–`DPQ090` |
| `BMX_L.xpt` | Body measurements | `SEQN`, `BMXBMI`, `BMXWAIST` |
| `BPXO_L.xpt` | Blood pressure measurements | `SEQN`, `BPXOSY1`–`BPXOSY3`, `BPXODI1`–`BPXODI3` |

## Official Download Links

- [DEMO_L.xpt](https://wwwn.cdc.gov/Nchs/Data/Nhanes/Public/2021/DataFiles/DEMO_L.xpt)
- [DPQ_L.xpt](https://wwwn.cdc.gov/Nchs/Data/Nhanes/Public/2021/DataFiles/DPQ_L.xpt)
- [BMX_L.xpt](https://wwwn.cdc.gov/Nchs/Data/Nhanes/Public/2021/DataFiles/BMX_L.xpt)
- [BPXO_L.xpt](https://wwwn.cdc.gov/Nchs/Data/Nhanes/Public/2021/DataFiles/BPXO_L.xpt)

The files should be downloaded from the official NHANES website and placed in the `data/raw/` directory.

## Download Date

**Date downloaded:** [October 31, 2026]

## Data Processing and Reconstruction

The analytical dataset is reconstructed in the Jupyter notebook:

`notebooks/feasibility_check.ipynb`

The main processing steps are:

1. Read the four XPT files using pandas.
2. Restrict the demographic dataset to participants aged 20 years and older.
3. Merge the four datasets using `SEQN` as the participant identifier.
4. Check duplicate participant identifiers and missing values.
5. Construct the PHQ-9 total score from the nine questionnaire items (`DPQ010`–`DPQ090`), treating refused and don't-know responses as invalid for the total score.
6. Calculate participant-level mean systolic and diastolic blood pressure from available readings.
7. Conduct descriptive and exploratory analyses.

The four-file merged analytical dataset contains 6,064 adult participants.

A separate dataset created by merging the demographic and body-measurement files is used for the weighted obesity prevalence calculation. It contains 5,970 adults with non-missing BMI and MEC examination weights.

## Survey Design and Weight Selection

NHANES uses a complex survey design and provides different sample weights depending on the survey component.

This project uses the **MEC examination weight (`WTMEC2YR`)** because the main analytical variables include PHQ-9 scores, BMI, waist circumference, and blood pressure.

Although demographic and socioeconomic variables such as age, sex, education, and income-to-poverty ratio are collected during the household interview, the main health measurements and the PHQ-9 questionnaire are collected during the Mobile Examination Center (MEC) component.

The NHANES 2021–2023 analytic guidelines recommend using examination weights when an analysis combines interview and examination variables, because these weights account for nonresponse to the examination among interviewed participants.

The official guidance states:

> "If an analysis included both interview and examination variables, the examination weights should be used because they account for nonresponse to the examination among interviewed people."

Source: [NHANES 2021–2023 Analytic Guidelines – Brief Overview](https://wwwn.cdc.gov/nchs/nhanes/continuousnhanes/OverviewBrief.aspx?Cycle=2021-2023)

The phlebotomy weights are not used because this project does not currently include variables derived from blood analytes.

The following survey design variables are retained for subsequent design-based statistical analysis:

- `WTMEC2YR`: MEC examination sample weight
- `SDMVSTRA`: masked variance unit pseudo-stratum
- `SDMVPSU`: masked variance unit pseudo-PSU

**Important:** Applying sample weights is necessary for appropriate population estimates, but weights alone do not account for the full complex survey design when estimating standard errors and confidence intervals. The strata and PSU variables must also be incorporated in design-based analyses.

## Data Availability and Repository Policy

Raw NHANES data files are not included in this GitHub repository.

The `data/raw/` directory is excluded from version control. Users must download the four files from the official NHANES links above to reproduce the analysis.

The notebook and project documentation provide the processing steps needed to reconstruct the analytical dataset.