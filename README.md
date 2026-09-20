# Aadhaar Enrolment Disparity Analysis

## Descriptive Analytics of India's National Digital Identity System

This project analyzes Aadhaar enrolment, demographic-update, and biometric-update activity across states, districts, age groups, and time periods using large-scale aggregated government administrative data.

The analysis covers more than 5 million aggregated records and follows a structured data analytics workflow covering data integration, data cleaning, feature engineering, exploratory data analysis, statistical testing, outlier detection, and Power BI dashboard development.

> **Note:** The dataset used in this project contains aggregated district-level daily counts, not individual Aadhaar records.

---

## Project Objectives

- Identify regional disparities in Aadhaar enrolment
- Analyze age-wise enrolment patterns across 0–5, 5–17, and 18+ age groups
- Identify high-load states and districts
- Examine temporal enrolment and update patterns
- Statistically validate regional and demographic patterns
- Build an interactive Power BI dashboard for analytical insights

---

## Dataset

The project uses three major datasets:

1. Aadhaar Enrolment
2. Aadhaar Demographic Updates
3. Aadhaar Biometric Updates

After merging the available CSV partitions, the project analyzed:

| Dataset | Rows | Columns |
|---|---:|---:|
| Enrolment | 1,006,029 | 7 |
| Demographic | 2,071,700 | 6 |
| Biometric | 1,861,108 | 6 |
| **Total** | **5M+** | — |

### Main Features

- `date`
- `state`
- `district`
- `pincode`
- `age_0_5`
- `age_5_17`
- `age_18_greater`

The analysis is exploratory and statistical and does not use a target variable.

---

## Methodology

The project follows the following data analytics pipeline:

### 1. Data Loading & Integration

- Imported multiple CSV partitions
- Verified schema consistency
- Combined datasets using Pandas
- Validated dataset structure and dimensions

### 2. Data Preprocessing

- Converted date fields to appropriate datetime format
- Standardized state names
- Standardized district names
- Corrected spelling and formatting inconsistencies
- Removed invalid and noisy geographic entries
- Identified and removed duplicate records
- Handled missing values where required

### 3. Feature Engineering

Created analytical features including:

- Total Enrolment
- Age-group ratios
- Regional aggregates
- State-level aggregates
- District-level rankings

Total enrolment was calculated from:

`age_0_5 + age_5_17 + age_18_greater`

### 4. Outlier Detection

Used the **Interquartile Range (IQR)** method to identify unusually high or low enrolment values.

The analysis was used to identify high-load districts and investigate regional variation.

### 5. Exploratory Data Analysis

EDA was performed to analyze:

- State-wise distributions
- Regional disparities
- District rankings
- Age-group distributions
- Temporal trends
- Enrolment and update relationships
- Distribution skewness

### 6. Statistical Testing

The project applied:

- Chi-Square Test
- T-Test
- One-Way ANOVA
- Correlation Analysis
- IQR-based Outlier Detection

---

## Data Quality Analysis

Data cleaning was a major component of the project.

Duplicate analysis identified:

| Dataset | Duplicate Rate |
|---|---:|
| Enrolment | 3.05% |
| Demographic | 23.21% |
| Biometric | 5.36% |

The duplicate records were removed before downstream aggregation and statistical analysis.

State and district normalization was also performed to address spelling variations, case inconsistencies, legacy administrative names, invalid entries, and other formatting issues.

---

## Key Findings

### Regional Concentration

A relatively small number of highly populated states account for a large proportion of enrolment activity.

The analysis also identified persistent differences in activity between regions and states.

### Age Patterns

Enrolment activity is concentrated among younger age groups, while demographic update activity is heavily represented among adults.

The analysis identified a clear lifecycle pattern between initial enrolment and subsequent identity updates.

### Temporal Patterns

Aadhaar activity does not follow a simple smooth trend. The analysis identified fluctuations, spikes, and irregular periods of activity.

### Statistical Findings

The statistical analysis identified significant relationships and differences across several regional and demographic dimensions.

For example, the Chi-Square analysis found a statistically significant association between state and the 0–5 age group.

The T-Test comparing mean biometric updates between the 5–17 and 18+ age groups produced a p-value of 0.4616, indicating no statistically significant difference in the analyzed sample.

---

## Power BI Dashboard

The project includes an interactive Power BI dashboard built using a **Star Schema** data model.

The dashboard contains three major analytical sections:

### Overview Analysis

Provides an overall view of enrolment and update activity, including key metrics and trends.

### Regional Disparity

Analyzes:

- Regional distribution
- State-level activity
- Geographic concentration
- Enrolment vs update activity

### Age & Lifecycle

Analyzes:

- Age-wise enrolment
- Demographic updates
- Biometric updates
- Identity lifecycle patterns

---


## Tools & Technologies

### Programming & Analysis

- Python
- Pandas
- NumPy
- SciPy

### Data Visualization

- Matplotlib
- Seaborn
- Plotly

### Business Intelligence

- Microsoft Power BI

### Environment

- Google Colab

---

## Project Structure

```text
Aadhaar-Enrolment-Disparity-Analysis/
│
├── README.md
│
├── notebooks/
│   └── Aadhaar-Enrolment-Disparity-Analysis.ipynb
│
├── report/
│   └── Aadhaar-Enrolment-Disparity-Analysis-Report.docx
│
├── dashboard/
│   └── Aadhaar-Enrolment-Disparity-Analysis.pbix
│
├── presentation/
│   └── Aadhaar-Enrolment-Disparity-Analysis-Presentation.pptx
│
├── images/
│   ├── overview-dashboard.png
│   ├── regional-disparity-dashboard.png
│   └── age-lifecycle-dashboard.png
│
└── data/
    └── README.md