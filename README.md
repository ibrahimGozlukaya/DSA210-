# Economic Stress and Digital Behavior: How Economic Changes Shape Social Media Usage in Europe

---

##  1. Motivation
Over the last decade, Europe has gone through major economic challenges such as the COVID-19 pandemic, the energy crisis, and record-high inflation in 2022–2023.  
During these periods, people tend to change their online behavior — turning to social media to stay connected, informed, or simply distracted.

This project explores **how economic changes, specifically inflation and unemployment, affect social media usage across European countries** between **2011 and 2024**.  
The main goal is to find out **whether social media participation increases when economic conditions worsen**.  
If an increase is observed, the project will also examine **which types of platforms account for that growth** — for example, whether people move toward entertainment-based platforms like TikTok and YouTube or professional networks such as LinkedIn.

By combining economic and digital data, the project aims to understand how people’s online habits respond to economic stress.

---

##  2. Research Questions and Sub-Questions

**Main Question**
- Do worsening economic conditions (higher inflation or unemployment) lead to higher social-media participation in Europe?

**Sub-Questions**
1. If participation increases, which categories of platforms (entertainment vs. professional/informational) account for that growth?  
2. Is the relationship immediate, or does it appear with a delay (one-year lag between economic change and digital response)?  
3. Is the trend consistent across different years of economic turbulence (e.g., 2020–2023 inflation surge)?

---

##  3. Hypotheses

- **H1:** Higher inflation or unemployment rates are associated with increased social-media participation.  
- **H2:** If participation increases, the growth will be stronger on entertainment-based platforms (e.g., TikTok, YouTube) compared to professional ones (LinkedIn).  
- **H0 (Null):** Economic indicators have no significant relationship with social-media participation.

---

##  4. Data Description

| **Dataset** | **Variable(s)** | **Why it is used** |
|--------------|-----------------|--------------------|
| **Eurostat – tin00127** | “Individuals using the internet for participating in social networks (% of individuals)” | Measures yearly social-media participation for each European country (2011–2024). |
| **World Bank (WDI)** | Inflation (`FP.CPI.TOTL.ZG`), Unemployment (`SL.UEM.TOTL.ZS`), Internet usage (`IT.NET.USER.ZS`) | Represents key economic conditions and general internet access rates. |
| **Statcounter ** | Platform market share (Facebook, Instagram, YouTube, TikTok, LinkedIn, X) | Identifies which platforms gain or lose users when total participation changes. |

---

##  5. Data Source and Collection

- **Eurostat data:** Downloaded from the [Eurostat Data Browser](https://ec.europa.eu/eurostat/databrowser/product/page/tin00127) in `.csv` or `.tsv` format  
  *(filters: `sex=T`, `age=Y16-74`, `unit=PC_IND`)*  
- **World Bank data:** Retrieved through the [World Bank Open Data API](https://data.worldbank.org/indicator) using the codes `FP.CPI.TOTL.ZG`, `SL.UEM.TOTL.ZS`, and `IT.NET.USER.ZS`.  
- **Statcounter :** Exported manually from [Statcounter Global Stats](https://gs.statcounter.com/social-media-stats/all/europe) for selected countries and years.  

All datasets are **public, aggregated, and non-personal**, ensuring ethical and reproducible use.

---

##  6. Methodology (How the Questions Will Be Tested)

1. **Data Preparation**
   - Merge Eurostat and World Bank datasets by country and year (2011–2024).  
   - Create lag variables for inflation and unemployment (`t-1`) to capture delayed behavioral effects.  
   - Normalize or scale variables where needed.

2. **Exploratory Analysis (EDA)**
   - Plot trends of social-media usage vs. inflation/unemployment.  
   - Visualize country-year heatmaps and correlation matrices.  

3. **Statistical Testing**
   - Apply a **panel fixed-effects regression** model:  
    
4. **Platform Composition Analysis **
   - Use Statcounter platform shares to examine which platforms drive the changes in total participation (tests H2).  

---

##  7. Expected Results
The project expects to find a **positive association** between economic stress (inflation/unemployment) and social-media participation.  
If confirmed, secondary analysis will reveal **which platform types** absorb that growth — showing whether people turn to entertainment, community, or professional platforms during tough economic periods.

---

---

##  8. Author
**İbrahim Gözlükaya**  
Sabancı University – DSA210 (Fall 2025–2026)

---
