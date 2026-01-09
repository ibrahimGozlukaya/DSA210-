# Economic Stress and Digital Behavior: How Economic Changes Shape Social Media Usage in Europe

---

## 1. Motivation
Over the last fifteen years, social media has become an integral part of daily life, shaping how people communicate, consume news, and spend their free time. However, social media usage does not grow evenly: economic and social factors influence how people connect online. During periods of slower growth, rising prices, or declining confidence in the economy, individuals may turn to digital spaces more frequently to stay informed, seek community, or access low-cost entertainment.

This project examines how changes in economic conditions and consumer confidence relate to social media usage across European countries. Rather than focusing only on crisis periods, it studies whether economic uncertainty or optimism—captured through inflation, unemployment, and confidence indicators—is reflected in digital behavior. It also explores whether different types of platforms (entertainment vs professional) benefit differently during periods of economic stress.

---

## 2. Research Questions and Sub-Questions

**Main Question**
- Do worsening economic conditions (higher inflation or unemployment) lead to higher social media participation in European countries?

**Sub-Questions**
1. Does unemployment correlate more strongly with increased usage of professional platforms (e.g., LinkedIn), while inflation correlates more with entertainment-oriented platforms (e.g., Instagram, YouTube)?
2. Does consumer confidence moderate the relationship between economic stress and social media usage (i.e., is the effect stronger when confidence is low)?

---

## 3. Hypotheses
- **H1:** Higher inflation and higher unemployment are associated with increased social media participation.  
- **H2:** When consumer confidence is low, the relationship between economic stress and social media usage is stronger.  
- **H3:** During periods of economic stress, countries experience shifts in platform preferences: rising unemployment is associated with increases in the relative share of professional platforms, while rising inflation is associated with increases in the relative share of entertainment platforms.

- **H0 (Null):** Economic indicators and consumer confidence have no significant relationship with social media participation.

---

## 4. Data Description (As Implemented in the Notebooks)

| Dataset | Variables | Purpose |
|-------|----------|---------|
| **Eurostat – tin00127** (`tin00127_linear_2_0.csv`) | Percentage of individuals participating in social networks (annual) | Main dependent variable: social media participation rate. |
| **Eurostat – HICP** (`prc_hicp_midx__custom_19134087_linear.csv`) | Monthly HICP index, converted to annual inflation (Dec–Dec %) | Measures inflationary pressure. |
| **Eurostat – Unemployment** (`une_rt_m_linear_2_0.csv`) | Monthly unemployment rate, aggregated to yearly averages | Labor-market stress indicator. |
| **OECD – Consumer Confidence Index** (`export-2025-11-26T13_03_48.204Z.csv`) | Monthly CCI values, aggregated to yearly averages | Captures consumer optimism or pessimism. |
| **Statcounter (processed)** (`social_media_countries_monthly.csv`) | Monthly platform market shares | Used to analyze platform-category shifts. |

### Processed Data Outputs
- `data/processed/panel_annual.csv`
- `data/processed/panel_annual_final.csv`
- `data/processed/panel_monthly_h3.csv`

---

## 5. Data Source and Collection

- **Social media participation:** Eurostat table `tin00127`, cleaned and reshaped into a country–year panel.
- **Inflation:** Monthly HICP data converted into annual inflation using December-to-December percentage change.
- **Unemployment:** Monthly unemployment rates aggregated into yearly averages.
- **Consumer confidence:** OECD monthly CCI series aggregated into yearly averages.
- **Platform market shares:** Statcounter monthly data processed into annual means and grouped into entertainment and professional categories.

All datasets are public, aggregated, and non-personal.

---

## 6. Methodology

### 6.1 Panel Construction
Two panel datasets are constructed:
- **Annual panel (H1 and H2):** Country–year data combining social media participation, inflation, unemployment, consumer confidence, and platform shares.
- **Monthly panel (H3):** Platform market shares merged with monthly inflation, unemployment, and consumer confidence.

A standardized economic stress index is constructed as:

Stress = z(inflation) + z(unemployment) − z(consumer confidence)

---

### 6.2 Exploratory Data Analysis
Exploratory analysis visualizes time trends, cross-country differences, and the relationship between economic stress and social media participation. All figures are saved in the `figures/` directory.

---

### 6.3 Hypothesis Testing
- **H1:** Welch two-sample t-tests comparing social media participation in low-stress versus high-stress periods.
- **H2:** Linear regression with an interaction term:  
  Social media participation ~ Stress × Consumer Confidence
- **H3:** Monthly first-difference correlations between economic indicators and platform-category market shares.

---

### 6.4 Machine Learning Analysis
Machine learning methods are used to complement statistical inference with prediction:
- **Regression models:** Linear Regression, Ridge, Lasso, ElasticNet, Random Forest, Gradient Boosting, and Support Vector Regression.
- **Classification task:** Predicts whether social media participation increases year-over-year.
- **Evaluation:** Time-aware train–test splits; performance evaluated using RMSE, R², and confusion matrices.

---

## 7. Expected Results
The project expects to find a positive association between economic stress and social media participation, with stronger effects during periods of low consumer confidence. Platform preferences are expected to shift under stress, with unemployment favoring professional platforms and inflation favoring entertainment platforms.

---

## Repository Structure
1. `01_data_collection.ipynb`
2. `02_eda.ipynb`
3. `03_hypothesis_testing.ipynb`
4. `04_ml_models.ipynb`

---

*End of README.md*
