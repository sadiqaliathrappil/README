# Cybersecurity Awareness and Consumer Trust: A Data-Driven Study of Digital Service Adoption

## Overview

This repository contains the dataset, Python analysis script, and supporting outputs for the dissertation:

**"Cybersecurity Awareness and Consumer Trust: A Data-Driven Study of Digital Service Adoption"**

The study investigates how:

- Cybersecurity Awareness
- Perceived Data Privacy
- System Reliability

influence:

- Consumer Trust in Digital Services

The analysis was conducted using Python and follows a quantitative research design based on survey data collected from digital service users.

---

# Research Objectives

The study addressed the following objectives:

1. Analyse respondents' demographic characteristics and levels of cybersecurity awareness, perceived data privacy, system reliability, and consumer trust.

2. Examine whether consumer trust differs across demographic groups.

3. Investigate the relationship between cybersecurity awareness, perceived data privacy, system reliability, and consumer trust.

4. Assess the impact of cybersecurity awareness, perceived data privacy, and system reliability on consumer trust.

---

# Dataset

The dataset consists of responses collected through a structured online questionnaire.

### Sample Size

- Total valid respondents: **124**

### Target Population

Individuals who regularly use digital services such as:

- Online banking
- Digital payment platforms
- E-commerce services
- Mobile applications
- Cloud-based services

### Sampling Technique

- Convenience Sampling

### Research Design

- Quantitative Research
- Cross-Sectional Survey

---

# Python Libraries Used

The analysis was conducted using the following Python packages:

```python
pandas
numpy
matplotlib
seaborn
scipy
statsmodels
pingouin
scikit-posthocs
openpyxl
```

---

# Data Processing Workflow

## Step 1: Importing the Dataset

The survey dataset was imported into Python using Pandas.

```python
pd.read_csv()
```

The code first examined:

- Dataset dimensions
- Number of respondents
- Variable names
- Missing values

---

## Step 2: Data Cleaning

To ensure consistency:

- Column names were cleaned and standardized.
- Missing values were checked.
- Screening questions were verified.

The script specifically filtered respondents who confirmed that they use digital services.

Only valid digital service users were retained for analysis.

---

## Step 3: Variable Classification

Variables were grouped into five categories:

### Demographic Variables

- Gender
- Age
- Education
- Occupation
- Income
- Residence
- Usage Frequency
- Years Using Digital Services

### Cybersecurity Awareness

10 objective knowledge questions:

```text
C1 – C10
```

### Perceived Data Privacy

7 Likert-scale items:

```text
D1 – D7
```

### System Reliability

7 Likert-scale items:

```text
E1 – E7
```

### Consumer Trust

10 Likert-scale items:

```text
F1 – F10
```

---

# Construction of Study Variables

## Cybersecurity Awareness Score

Cybersecurity awareness was measured using objective knowledge questions.

### Procedure

1. Each question was matched against its correct answer.
2. Correct answer = 1
3. Incorrect answer = 0
4. Scores were summed across all 10 questions.

```python
Cybersecurity Awareness
=
Sum of Correct Responses
```

Possible score range:

```text
0 – 10
```

Higher scores indicate greater cybersecurity awareness.

---

## Likert Scale Coding

Responses for:

- Data Privacy
- System Reliability
- Consumer Trust

were converted into numerical values.

Example:

```text
Strongly Disagree = 1
Disagree = 2
Neutral = 3
Agree = 4
Strongly Agree = 5
```

---

## Reverse Coding

Two trust-related items required reverse coding:

```python
F4
F6
```

Transformation:

```python
New Score = 6 - Original Score
```

This ensured all items pointed in the same conceptual direction.

---

## Construct Score Creation

Composite scores were calculated using mean values.

### Perceived Data Privacy

```python
Mean(D1-D7)
```

### System Reliability

```python
Mean(E1-E7)
```

### Consumer Trust

```python
Mean(F1-F10)
```

These construct scores were used for all subsequent statistical analyses.

---

# Statistical Analysis

## Objective 1: Descriptive Statistics

Descriptive statistics were generated for:

- Cybersecurity Awareness
- Perceived Data Privacy
- System Reliability
- Consumer Trust

Statistics reported:

- Mean
- Standard Deviation
- Minimum
- Maximum
- Skewness
- Kurtosis

Purpose:

To understand respondent characteristics and overall perceptions.

---

## Reliability Analysis

Internal consistency was assessed using Cronbach's Alpha.

```python
pingouin.cronbach_alpha()
```

Constructs tested:

- Perceived Data Privacy
- System Reliability
- Consumer Trust

Purpose:

To verify that questionnaire items consistently measured the intended concepts.

---

## Objective 2: Demographic Differences in Consumer Trust

### Independent Samples t-Test

Applied when a demographic variable had two groups.

Example:

```text
Gender
```

Purpose:

To determine whether consumer trust differs significantly between two groups.

---

### One-Way ANOVA

Applied when demographic variables had more than two categories.

Variables included:

- Age
- Education
- Occupation
- Income
- Residence
- Usage Frequency
- Years Using

Purpose:

To examine whether mean consumer trust varies across demographic categories.

---

### Post-Hoc Testing

When ANOVA results were significant, Tukey HSD tests were prepared for pairwise comparisons.

```python
Tukey HSD
```

Purpose:

To identify which groups differ from each other.

---

# Objective 3: Correlation Analysis

Pearson correlation analysis was conducted to evaluate relationships among:

- Cybersecurity Awareness
- Perceived Data Privacy
- System Reliability
- Consumer Trust

```python
pearsonr()
```

Outputs included:

- Correlation coefficients (r)
- Significance values (p-values)

A correlation heatmap was also created using:

```python
Seaborn Heatmap
```

Purpose:

To understand the strength and direction of relationships among study variables.

---

# Objective 4: Multiple Regression Analysis

Multiple Linear Regression was used to examine the influence of:

### Independent Variables

- Cybersecurity Awareness
- Perceived Data Privacy
- System Reliability

### Dependent Variable

- Consumer Trust

Model specification:

```text
Consumer Trust =
β0
+ β1(Cybersecurity Awareness)
+ β2(Perceived Data Privacy)
+ β3(System Reliability)
+ ε
```

The regression model estimated:

- Regression coefficients
- Standard errors
- t-values
- p-values
- R²
- Adjusted R²
- F-statistic

Purpose:

To identify the most influential predictors of consumer trust.

---

# Additional Diagnostic Tests

To ensure robustness of findings, diagnostic checks were performed.

## Standardised Beta Coefficients

Variables were standardised using:

```python
StandardScaler()
```

Purpose:

To compare the relative importance of predictors.

---

## Multicollinearity Test

Variance Inflation Factor (VIF) was calculated.

```python
variance_inflation_factor()
```

Purpose:

To determine whether predictors were highly correlated with each other.

---

## Heteroscedasticity Test

Breusch-Pagan Test was applied.

```python
het_breuschpagan()
```

Purpose:

To verify constant variance of regression residuals.

---

## Robust Regression

HC3 robust standard errors were estimated.

```python
cov_type = "HC3"
```

Purpose:

To confirm whether statistical significance remained stable under robust estimation.

---

# Hypothesis Testing

The following hypotheses were evaluated:

### H1

Consumer trust differs across demographic groups.

### H2

Cybersecurity awareness significantly influences consumer trust.

### H3

Perceived data privacy significantly influences consumer trust.

### H4

System reliability significantly influences consumer trust.

Decision rule:

```text
p < 0.05 → Supported

p ≥ 0.05 → Not Supported
```

---

# Output Generation

All generated results were exported automatically into Excel format.

Outputs included:

- Descriptive Statistics
- Reliability Analysis
- ANOVA Results
- Correlation Results
- Regression Results
- Robust Regression Results
- Hypothesis Testing Summary

Export format:

```python
openpyxl
```

---

# Main Findings

The analysis showed that:

- Cybersecurity awareness was moderate among respondents.
- Perceived data privacy positively influenced consumer trust.
- System reliability positively influenced consumer trust.
- System reliability emerged as the strongest predictor of trust.
- Cybersecurity awareness did not significantly predict consumer trust.
- No significant demographic differences in trust were observed.

---

# Reproducibility

To reproduce the analysis:

1. Download the dataset.
2. Open the Python script.
3. Install required packages.
4. Run the script sequentially.
5. Review the generated Excel outputs and visualisations.

---

# Repository Structure

```text
├── sadiq dataset.csv
├── Sadiq Python Code.py
├── README.md
└── Abstract of the study
```

---

# Author
