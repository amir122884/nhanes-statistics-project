
# Depressive Symptoms and Obesity-Related Measures Among Adults in NHANES 2021–2023

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


## Phase 2 Scope — Probability and Probability Distributions

Phase 2 translates the project data into empirical probability statements and examines selected probability distributions. The analysis focuses on obesity-related measures and depressive symptoms among adults aged 20 years and older.

### Events and Random Variables

The main categorical events are defined as follows:

- **Event A — Obesity:** A participant has a BMI greater than or equal to 30 kg/m².
- **Event B — Moderate-or-higher depressive symptom severity:** A participant has a PHQ-9 total score greater than or equal to 10. This is a screening threshold for depressive symptom severity, not a clinical diagnosis.

The quantitative variables include:

- **BMI (`BMXBMI`):** A continuous quantitative variable.
- **PHQ-9 total score (`PHQ9`):** A discrete quantitative score ranging from 0 to 27.
- **Mean systolic blood pressure (`Mean_Systolic`):** The mean of the available systolic blood pressure readings for each participant.

Each event or variable is defined at the participant level. The participant identifier remains `SEQN`.

### Probability Analysis

The probability analysis includes:

1. Empirical marginal probabilities of Events A and B.
2. Their joint probability, P(A ∩ B).
3. Conditional probabilities, including P(B | A) and P(A | B).
4. An assessment of independence by comparing the joint probability with the product of the marginal probabilities.
5. Conditional obesity probabilities across sex subgroups, using the NHANES sex variable (`RIAGENDR`).
6. An application of Bayes' theorem using the empirical probabilities.

The joint analysis of obesity and depressive symptoms uses participants with non-missing values for both BMI and PHQ-9. Subgroup comparisons and other probability estimates use the corresponding eligible observations for each analysis.

### Discrete Random Variable and the Binomial Model

Obesity is also treated as a binary event. A count variable is defined as the number of participants with obesity in a subsample of 100 participants.

The observed counts from 50 non-overlapping subsamples are compared with the theoretical binomial distribution. The analysis examines the binomial assumptions, including fixed sample size, binary outcomes, constant success probability, and independence.

Because the data come from a finite sample and NHANES uses a complex sampling design, the binomial model is interpreted as an approximation rather than an exact description of the sampling process.

### Continuous Variables and Probability Distributions

The distribution of mean systolic blood pressure is examined using a histogram and a boxplot. The analysis considers:

- Distribution shape and skewness.
- Measures of center and spread.
- Potential outliers.
- The suitability and limitations of a normal approximation.

The empirical mean and variance of systolic blood pressure are calculated and interpreted in the context of the project.

### Relationship Between Quantitative Variables

The relationship between BMI and PHQ-9 score is examined using a scatterplot and covariance. The direction and pattern of the observed relationship are discussed descriptively. Formal correlation inference and causal conclusions are outside the scope of this phase.

### Sampling Weights and Empirical Probabilities

The unweighted and weighted estimates of obesity prevalence are compared using the MEC examination weight (`WTMEC2YR`). The analysis explains why the observed sample proportion and the weighted population estimate may differ.

The weighted and unweighted comparison is descriptive. Appropriate population-level variance estimation requires accounting for the NHANES complex survey design, including `SDMVSTRA` and `SDMVPSU`.

### Phase 2 Analytical Limitations

1. Analyses involving both BMI and PHQ-9 are restricted to participants with valid observations for both variables. Their sample size is therefore smaller than the main analytical sample.
2. Subgroup probability comparisons are descriptive and do not constitute formal hypothesis tests.
3. The binomial model relies on simplifying assumptions that may not fully hold under the NHANES sampling design.
4. The normal approximation is evaluated from the observed distribution and is not assumed in advance.
5. Covariance describes the direction of a linear relationship but does not establish causality or, by itself, measure the strength of association independently of the variables' scales.
6. Weighted prevalence estimates do not, by themselves, provide design-adjusted standard errors or confidence intervals.

### Phase 2 Deliverables

- `notebook/phase2_probability.ipynb`
- `reports/phase2.pdf`
- Reproducible probability-analysis code.
- Final tables and visualizations.
- Git tag: `phase-2`
