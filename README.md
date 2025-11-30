# Economic Stress and Digital Behavior: How Economic Changes Shape Social Media Usage in Europe

---

##  1. Motivation
  Over the last fifteen years, social media has become an integral part of daily life, it has shaped how people communicate, view news, and spend their free time. However, social media usage does not grow evenly: economic and social factors often impact the way that people connect online. In the event of slower growth, increasing prices, or lower confidence in the economy, people may turn to digital spaces more frequently either to stay informed, seek community, or as a low cost form of entertainment.

This project aims to understand how changes in economic conditions and people's confidence on the economy relate to social media usage across European countries. Rather than only focusing on crises, it studies whether economic uncertainty or optimism captured through inflation, unemployment,and confidence levels is reflected in how people use social media. In addition, it asks whether certain types of platforms (entertainment vs professional) gain more attention when overall usage increases.

##  2. Research Questions and Sub-Questions  
**Main Question**  
- Do worsening economic conditions (higher inflation or unemployment) lead to higher social media participation in European countries?  

**Sub-Questions**  
1. Does unemployment correlate more with increases in professional-platform usage (e.g., LinkedIn), while rising prices (inflation) correlate more with growth in entertainment-oriented platforms (e.g., Instagram, TikTok, YouTube)?
2. Does consumer confidence moderate the relationship between economic stress and social-media usage (i.e., when confidence is low, is the effect stronger)?  

---

##  3. Hypotheses  
- **H1:** Higher inflation, higher unemployment  are associated with increased social-media participation.  
- **H2:** When consumer confidence is low, the association between economic stress and social-media usage is stronger.  
- **H3:** Under economic stress, different conditions lead to different shifts in platform usage: rising unemployment is expected to increase participation more on professional platforms such as LinkedIn, while rising prices (inflation) are expected to increase participation more on entertainment-oriented platforms such as Facebook and YouTube.

- **H0 (Null):** Economic indicators and consumer confidence have no significant relationship with social-media participation.

---

##  4. Data Description  
| Dataset | Variable(s) | Why used |
|----------|--------------|----------|
| **Eurostat – tin00127** | “Individuals using the internet for participating in social networks (% of individuals)” | Main dependent variable: social-media participation rate for each European country (2011–2024). |
| **World Bank (WDI)** | Inflation (`FP.CPI.TOTL.ZG`), Unemployment (`SL.UEM.TOTL.ZS`), GDP growth (`NY.GDP.MKTP.KD.ZG`) | Key macro-economic stress variables. |
| **OECD – Consumer Confidence Index (CCI; STES/CLI)** | Monthly CCI; aggregated to yearly averages | Behavioural measure capturing how optimistic/pessimistic consumers are. |
| **Statcounter** | Platform market shares (Facebook, Instagram, TikTok, YouTube, LinkedIn) | Used to answer which platform categories gain usage during stressed periods. |
| **DataReportal** | Country-level social media penetration & time-spent indicators | Alternative view on adoption and intensity of use; helpful for robustness checks. |

---

##  5. Data Source and Collection  
- **Eurostat social-media participation data:** Download from Eurostat Data Browser (table `tin00127`) as CSV/TSV.  
- **World Bank macro data:** Retrieve via WDI API using codes `FP.CPI.TOTL.ZG`, `SL.UEM.TOTL.ZS`, `NY.GDP.MKTP.KD.ZG`.  
- **OECD Consumer Confidence Index (CCI):** Use OECD STES/CLI dataset; download monthly CCI and aggregate to yearly averages.  
- **Statcounter platform share data (optional):** Export for selected countries from Statcounter Global Stats – Social Media Market Share.  
- **DataReportal (optional):** Use annual country reports/datasets for social media penetration and time-spent metrics to complement Eurostat/Statcounter.  

All data used are **public, aggregated, and non-personal**, making the analysis reproducible and ethically sound.

---

##  6. Methodology – How We Will Test It  

To test the research questions, we will combine data from Eurostat, the World Bank, and the OECD to create a panel dataset covering European countries from 2011 to 2024. Social media participation rates will be compared with key economic indicators inflation, unemployment, GDP growth and consumer confidence levels.  

First we will explore the general trends over time to see whether social media usage tends to increase during periods of economic stress or declining confidence. Then, we will apply a **panel regression analysis** that tracks how changes in these economic indicators are related to changes in social media participation within each country.  

To address the **sub-questions**, we will test whether consumer confidence strengthens or weakens the relationship between economic stress and social media use (interaction effects).  
Additionally, optional platform level data from Statcounter or DataReportal will help us see whether higher usage is driven more by entertainment focused or professional platforms.  

Beyond the main model, two complementary approaches may be used for robustness:  
- **Regional Fixed Effects Models:** Countries will also be grouped by region (e.g., Northern, Southern, and Eastern Europe) to test whether regional similarities in digital adoption or culture influence the results.  
- **Difference-in-Differences (DiD):** Specific economic shock periods (such as 2020–2022) will be analysed to see whether social media engagement increased more strongly in countries that experienced larger economic disruptions compared to more stable ones.  
---

##  7. Expected Results  
The project expects to find a **positive relationship** between economic stress indicators (inflation, unemployment, low GDP growth) and social media participation.  
It further expects that **lower consumer confidence** amplifies this effect (H2), and that when usage rises, **entertainment-oriented platforms** benefit more than professional ones (H3).

---

*End of README.md*
