# Economic Stress and Digital Behavior: How Economic Changes Shape Social Media Usage in Europe

---

## 1. Motivation
Over the last fifteen years, social media has become an integral part of daily life, it has shaped how people communicate, view news, and spend their free time. However, social media usage does not grow evenly: economic and social factors often impact the way that people connect online. In the event of slower growth, increasing prices, or lower confidence in the economy, people may turn to digital spaces more frequently either to stay informed, seek community, or as a low cost form of entertainment.

This project aims to understand how changes in economic conditions and people's confidence on the economy relate to social media usage across European countries. Rather than only focusing on crises, it studies whether economic uncertainty or optimism captured through inflation, unemployment, and confidence levels is reflected in how people use social media. In addition, it asks whether certain types of platforms (entertainment vs professional) gain more attention when overall usage increases.

---

## 2. Research Questions and Sub-Questions

**Main Question**
- Do worsening economic conditions (higher inflation or unemployment) lead to higher social media participation in European countries?

**Sub-Questions**
1. Does unemployment correlate more with increases in professional-platform usage (e.g., LinkedIn), while rising prices (inflation) correlate more with growth in entertainment-oriented platforms (e.g., Instagram, YouTube)?
2. Does consumer confidence moderate the relationship between economic stress and social-media usage (i.e., when confidence is low, is the effect stronger)?

---

## 3. Hypotheses
- **H1:** Higher inflation and higher unemployment are associated with increased social-media participation.  
- **H2:** When consumer confidence is low, the association between economic stress and social-media usage is stronger.  
- **H3:** During periods of economic stress, countries show shifts in platform preference: rising unemployment is associated with increases in the relative share of professional platforms (e.g., LinkedIn), whereas rising prices (inflation) are associated with increases in the relative share of entertainment platforms (e.g., Facebook, YouTube).

- **H0 (Null):** Economic indicators and consumer confidence have no significant relationship with social-media participation.

---

## 4. Data Description (As Implemented in Notebooks)

| Dataset | Variable(s) | Why used |
|-------|-------------|----------|
| **Eurostat – tin00127** (`tin00127_linear_2_0.csv`) | Individuals using the internet for participating in social networks (%), annual | Main dependent variable: social-media participation rate. |
| **Eurostat – HICP (monthly)** (`prc_hicp_midx__custom_19134087_linear.csv`) | Monthly HICP index → annual inflation (Dec–Dec %) and monthly YoY inflation | Captures price-level stress. |
| **Eurostat – Unemployment (monthly)** (`une_rt_m_linear_2_0.csv`) | Monthly unemployment rate → annual averages | Labor-market stress indicator. |
| **OECD – Consumer Confidence Index** (`export-2025-11-26T13_03_48.204Z.csv`) | Monthly CCI → annual averages | Measures economic optimism/pessimism. |
| **Statcounter (processed)** (`social_media_countries_monthly.csv`) | Monthly platform market shares | Used to study platform-category shifts (H3). |

### Processed Outputs
- `data/processed/panel_annual.csv`
- `data/processed/panel_annual_final.csv`
- `data/processed/panel_monthly_h3.csv`

---

## 5. Data Source and Collection

- **Eurostat social-media participation:** downloaded from table `tin00127`.
- **Inflation (HICP):** monthly data converted into annual inflation using December-to-December percent change.
- **Unemployment:** monthly rates aggregated into yearly averages.
- **Consumer confidence:** OECD CCI monthly series aggregated into yearly averages.
- **Platform shares:** Statcounter monthly data aggregated into annual means and grouped into entertainment vs professional categories.

All data are public, aggregated, and non-personal.

---

## 6. Methodology

### 6.1 Panel Construction
Two panels are created:
- **Annual panel (H1–H2):** country × year, combining participation, inflation, unemployment, CCI, and platform shares.
- **Monthly panel (H3):** platform shares merged with monthly macro indicators.

A standardized **economic stress index** is constructed as:
\[
\text{Stress} = z(\text{inflation}) + z(\text{unemployment}) - z(\text{CCI})
\]

---

### 6.2 Exploratory Data Analysis
Time trends, cross-country variation, and stress–usage relationships are visualized.  
All figures are saved in the `figures/` folder.

---

### 6.3 Hypothesis Testing
- **H1:** Welch two-sample t-tests comparing low-stress vs high-stress periods.
- **H2:** OLS regression with interaction:
  \[
  \text{Social Media Participation} \sim \text{Stress} \times \text{CCI}
  \]
- **H3:** Monthly first-difference correlations between macro stress indicators and platform-category shares.

---

### 6.4 Machine Learning Analysis
To complement inference with prediction:
- **Regression models:** Linear, Ridge, Lasso, ElasticNet, Random Forest, Gradient Boosting, SVR.
- **Classification:** Predicts whether social-media participation increases year-over-year.
- **Evaluation:** Time-aware train–test splits; RMSE, R², and confusion matrices reported.

---

## 7. Expected Results
We expect economic stress to be positively associated with social-media participation, with stronger effects when consumer confidence is low. Platform preferences are expected to shift: unemployment increases professional-platform usage, while inflation increases entertainment-platform usage.

---

## Repository Structure
1. `01_data_collection.ipynb`
2. `02_eda.ipynb`
3. `03_hypothesis_testing.ipynb`
4. `04_ml_models.ipynb`

---

*End of README.md*
