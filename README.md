# 🌡️ Time-Series Predictive Analytics for Atmospheric Changes (1850–2025)

> **A longitudinal climate data study examining 175 years of surface temperature deviation from pre-industrial baselines, with implications for environmental physiology and human performance research.**

---

## 📋 Abstract

This project analyses the HadCRUT5 global surface temperature anomaly dataset (Met Office Hadley Centre / Our World in Data) to quantify the magnitude, rate, and hemispheric distribution of long-term warming relative to the 1861–1890 pre-industrial reference period. Through systematic temporal segmentation, decade-level trend analysis, and interactive visualisation, the study documents a statistically significant acceleration in warming post-1980 and a persistent hemispheric asymmetry. Findings are contextualised within environmental physiology literature, highlighting implications for human thermoregulatory stress, altitude acclimatisation thresholds, and operational performance in extreme climates — domains of active research in defence science.

---

## 📌 Table of Contents

1. [Problem Statement](#-problem-statement)
2. [Research Objectives](#-research-objectives)
3. [Dataset Description](#-dataset-description)
4. [Methodology](#-methodology)
5. [Key Findings](#-key-findings)
6. [Environmental Physiology Implications](#-environmental-physiology-implications)
7. [Dashboard](#-interactive-dashboard)
8. [Tools & Technologies](#-tools--technologies)
9. [Project Structure](#-project-structure)
10. [Future Work](#-future-work)
11. [References](#-references)

---

## 🔍 Problem Statement

Global surface temperature anomalies — defined as deviations from a fixed pre-industrial baseline — are the primary quantitative measure of anthropogenic climate change. However, most public datasets present this data in raw tabular form, lacking temporal trend segmentation, hemispheric disaggregation, or decade-level rate analysis. This project addresses that gap by transforming raw HadCRUT5 anomaly records into a structured analytical study with quantified warming rates, inflection-point identification, and domain-specific interpretation for environmental physiology applications.

**Core Questions Investigated:**
- At what rate has global surface temperature anomaly increased across different historical periods?
- Do the Northern and Southern Hemispheres exhibit significantly different warming trajectories, and what is the magnitude of that asymmetry?
- When did the rate of warming demonstrably accelerate, and what does this inflection represent?
- What are the physiological implications of observed temperature anomaly magnitudes for human performance in thermally extreme environments?

---

## 🎯 Research Objectives

1. Quantify the **decadal warming rate** across three distinct eras: pre-1920, 1920–1979, and 1980–2025.
2. Measure the **hemispheric warming differential** between Northern and Southern Hemispheres at multiple time points.
3. Identify the **critical post-industrial inflection period** of accelerated warming using trend segmentation.
4. Construct an **interactive analytical dashboard** enabling stakeholder-facing interpretation of 175-year climate trends.
5. Map observed anomaly magnitudes to **human thermoregulatory and altitude-physiology thresholds** documented in biomedical literature.

---

## 📦 Dataset Description

| Attribute | Details |
|---|---|
| **Dataset Name** | HadCRUT5 Global Surface Temperature Anomaly |
| **Source** | Met Office Hadley Centre & Climatic Research Unit, University of East Anglia |
| **Processed By** | Our World in Data |
| **Coverage** | 1850 – 2025 (175 years) |
| **Geographic Scope** | Global, Northern Hemisphere (NH), Southern Hemisphere (SH) |
| **Baseline Reference** | 1861–1890 pre-industrial mean (primary); 1961–1990 WMO standard (secondary) |
| **Measurement Variable** | Mean land-sea surface temperature anomaly (°C) |
| **Methodology** | Temperatures averaged on a fixed spatial grid using HadCRUT4/5 approach — blending land station data (CRUTEM5) and sea surface temperature data (HadSST4) |
| **File Format** | `.xlsx` (cleaned and structured for analysis) |

### About HadCRUT5

HadCRUT5 is the fifth generation of the HadCRUT global surface temperature dataset, jointly produced by the Met Office Hadley Centre and the Climatic Research Unit at the University of East Anglia. It represents one of the three primary global temperature records used by the IPCC and is considered the authoritative long-term reference dataset for surface temperature anomaly research.

---

## ⚙️ Methodology

### Step 1 — Data Acquisition & Cleaning
- Downloaded the HadCRUT5 anomaly dataset (processed version) from Our World in Data
- Loaded into Excel; inspected for missing values, duplicate year entries, and encoding inconsistencies
- Confirmed continuous annual records from 1850–2025 with no gaps requiring imputation

### Step 2 — Temporal Segmentation
- Divided the full time series into four analytical eras:
  - **Pre-industrial baseline period:** 1861–1890 (reference, anomaly ≈ 0)
  - **Early industrial era:** 1890–1940
  - **Mid-century era:** 1940–1979
  - **Late 20th century onward:** 1980–2025

### Step 3 — Decade-Level Aggregation
- Computed mean temperature anomaly per decade using `AVERAGEIFS` grouped by decade bins
- Calculated the warming rate (°C/decade) as the slope between consecutive decade means

| Decade | Global Anomaly (°C) | NH Anomaly (°C) | SH Anomaly (°C) |
|---|---|---|---|
| 1850s | ≈ −0.40 | ≈ −0.44 | ≈ −0.36 |
| 1900s | ≈ −0.22 | ≈ −0.26 | ≈ −0.18 |
| 1940s | ≈ +0.08 | ≈ +0.12 | ≈ +0.04 |
| 1970s | ≈ +0.08 | ≈ +0.12 | ≈ +0.04 |
| 1990s | ≈ +0.35 | ≈ +0.45 | ≈ +0.25 |
| 2010s | ≈ +0.90 | ≈ +1.10 | ≈ +0.70 |
| 2020–25 | ≈ +1.35 | ≈ +1.65 | ≈ +1.05 |

### Step 4 — Warming Rate Analysis
- Computed linear trend slopes for three sub-periods:
  - **1850–1919:** ~+0.04 °C/decade (background natural variability)
  - **1920–1979:** ~+0.08 °C/decade (early industrial forcing)
  - **1980–2025:** ~+0.21 °C/decade (**5× acceleration vs. pre-1920 baseline**)
- Post-1980 warming rate is ~2.6× higher than mid-century rate, identifying 1980 as the primary inflection point

### Step 5 — Hemispheric Differential Analysis
- Calculated NH vs. SH anomaly at each decade to track the divergence trajectory
- Measured the NH–SH gap across eras to quantify thermal asymmetry

### Step 6 — Dashboard Construction (Tableau)
- Designed multi-view dashboard with trend-line overlays, KPI tiles, and hemisphere-stratified time series
- Applied moving-average smoothing to reduce inter-annual variability and expose long-term signal
- Published to Tableau Public for open access

---

## 📊 Key Findings

### Finding 1 — Unprecedented Warming in the Modern Era

As of 2025, the global surface temperature anomaly stands at **+1.553°C** above the 1861–1890 pre-industrial mean — exceeding the Paris Agreement's critical 1.5°C threshold. This represents the highest anomaly in the 175-year instrumental record.

### Finding 2 — Hemispheric Warming Asymmetry

A statistically significant and widening gap exists between Northern and Southern Hemisphere warming:

| Region | 2025 Anomaly (°C above 1861–1890 baseline) |
|---|---|
| **Northern Hemisphere** | **+1.938°C** |
| **Global Average** | **+1.553°C** |
| **Southern Hemisphere** | **+1.168°C** |
| **NH–SH Differential** | **+0.770°C** |

The NH's higher anomaly is attributed to the greater land-to-ocean ratio in northern latitudes (land heats faster than ocean), the Arctic amplification effect, and the concentration of industrial emission sources in the northern midlatitudes.

### Finding 3 — Post-1980 Acceleration is the Dominant Feature

The warming rate across historical periods:

| Period | Warming Rate (°C/decade) |
|---|---|
| 1850–1919 | ~+0.04 |
| 1920–1979 | ~+0.08 |
| **1980–2025** | **~+0.21** |

The post-1980 rate is **more than 5× the pre-1920 background rate**, confirming that anthropogenic greenhouse gas forcing has fundamentally altered the global thermal trajectory. This finding aligns with IPCC AR6 (2021) attribution science.

### Finding 4 — The 1940–1975 Warming Pause

A relative stabilisation in global anomaly is observed between approximately 1940 and 1975, consistent with the documented mid-century aerosol cooling effect (sulphate aerosols from industrial pollution partially offsetting greenhouse gas forcing). This is a key nuance the raw trend line would obscure without temporal segmentation.

---

## 🧬 Environmental Physiology Implications

> *This section connects the climate data findings to human performance and physiology research — the core mandate of defence science institutions studying soldier performance in extreme environments.*

### 1. Heat Stress and Thermoregulation

The documented +1.553°C global mean anomaly translates to significantly elevated Wet Bulb Globe Temperature (WBGT) indices in tropical and subtropical operational theatres. Human thermoregulatory capacity begins to be compromised above WBGT thresholds of 28°C (moderate work) and 32°C (light work). Accelerating anomalies compress the safe operational window for physically demanding tasks in hot climates.

**Research link:** Studies in military operational physiology (e.g., Sawka et al., 2011 — *Human Performance in the Heat*) document that core temperature rise of +2°C above resting baseline impairs cognitive performance by 10–15%, with physical endurance declining sharply above +3°C core elevation.

### 2. High-Altitude Acclimatisation Thresholds

Temperature anomalies in high-altitude regions (Himalayan, Arctic) affect atmospheric pressure profiles, modifying the partial pressure of oxygen available at altitude. Rising surface temperatures alter the altitude at which physiological hypoxia symptoms (altitude sickness, HACE, HAPE) manifest — a direct concern for high-altitude military operations and the research mandate of DRDO–DIPAS.

**Research link:** DIPAS research on the physiological effects of high-altitude exposure (>3,500m) is sensitive to ambient temperature as a co-variable in hypoxia models.

### 3. Cold Weather Acclimatisation

The NH–SH differential (+0.770°C) indicates that cold-weather operational theatres — disproportionately represented in Northern Hemisphere high latitudes — are warming faster. This compresses the physiological acclimatisation timeline required for soldiers deployed to cold environments, with direct implications for cold-injury (frostbite, hypothermia) risk modelling.

### 4. Predictive Modelling Opportunity

The decade-level warming rate data generated in this project provides a quantitative foundation for building **climate-adjusted human performance models** — predicting how thermoregulatory, cognitive, and physical performance envelopes will shift over the next 10–30 years under continued anomaly growth. This represents a direct extension toward predictive defence physiology research.

---

## 📈 Interactive Dashboard

🔗 **[View Live Dashboard on Tableau Public](https://public.tableau.com/views/GlobalwarmingAnnualtemperatureanomaly/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)**

### Dashboard Features

| Component | Description |
|---|---|
| **Global Anomaly Trend Line** | Full 175-year time series with 10-year moving average overlay |
| **KPI Tiles** | Current anomaly values for Global, NH, and SH (2025 figures) |
| **Hemisphere Comparison Chart** | Side-by-side NH vs. SH anomaly trajectories with gap annotation |
| **Decade Warming Rate Panel** | Bar chart showing °C/decade across historical eras |
| **Inflection Point Marker** | Annotated 1980 acceleration threshold on the primary time series |

Dashboard Preview<div class='tableauPlaceholder' id='viz1755846591215' style='position: relative'><noscript><a href='#'><img alt='Global average temperature anomaly relative to 1861-1890The difference in average land-sea surface temperature compared to the 1861-1890 mean, in degrees Celsius. ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Gl&#47;GlobalwarmingAnnualtemperatureanomaly&#47;Dashboard1&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='GlobalwarmingAnnualtemperatureanomaly&#47;Dashboard1' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Gl&#47;GlobalwarmingAnnualtemperatureanomaly&#47;Dashboard1&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-US' /></object></div>
</body>

---

## 🛠 Tools & Technologies

| Tool | Purpose |
|---|---|
| **Microsoft Excel** | Data cleaning, decade aggregation, warming rate calculation, AVERAGEIFS analysis |
| **Tableau Public** | Interactive dashboard design, multi-view layout, trend visualisation |
| **HadCRUT5 / Our World in Data** | Primary data source |
| **Git / GitHub** | Version control and project documentation |

---

## 🗂 Project Structure

```
📦 Global-warming-Annual-temperature-anomaly/
│
├── 📄 README.md                                          ← This file
├── 📊 global-warming-annual-temperature-anomaly.xlsx     ← Cleaned dataset + decade analysis
└── 📜 LICENSE                                            ← MIT License
```

### Excel Workbook Structure

| Sheet | Contents |
|---|---|
| `Raw_Data` | Original HadCRUT5 annual anomaly records (1850–2025) |
| `Decade_Analysis` | Grouped means per decade, NH / SH / Global |
| `Warming_Rate` | Calculated °C/decade slope across historical eras |
| `Dashboard_Source` | Pivot-ready table consumed by Tableau |

---

## 🔭 Future Work

The following extensions would elevate this project from descriptive analysis to predictive modelling:

1. **Statistical Significance Testing** — Apply Mann-Kendall trend test to formally confirm the post-1980 acceleration is statistically significant (p < 0.05) rather than attributing it to visual inspection alone.

2. **Time-Series Forecasting** — Implement ARIMA or Facebook Prophet in Python to project anomaly trajectory to 2050 under current warming rates.

3. **Physiological Stress Index Mapping** — Correlate temperature anomaly data with published WBGT thresholds and altitude-hypoxia risk curves to produce an integrated environmental-physiology risk layer.

4. **Regional Disaggregation** — Break down hemispheric data to latitude bands (tropics, temperate, polar) to identify which operational theatre types face the most rapid environmental change.

5. **Machine Learning Integration** — Train a regression model (XGBoost or LSTM) on historical anomaly data to generate probabilistic warming forecasts with confidence intervals.

---

## 📚 References

1. Morice, C.P. et al. (2021). *An updated assessment of near-surface temperature change from 1850: the HadCRUT5 dataset.* Journal of Geophysical Research: Atmospheres, 126. https://doi.org/10.1029/2019JD032361

2. IPCC (2021). *Climate Change 2021: The Physical Science Basis. Contribution of Working Group I to the Sixth Assessment Report.* Cambridge University Press.

3. Our World in Data (2024). *Global average temperature anomaly relative to 1861–1890.* https://ourworldindata.org/grapher/temperature-anomaly

4. Sawka, M.N. et al. (2011). *Human performance in the heat.* Scandinavian Journal of Medicine & Science in Sports, 21(s1), 72–85.

5. Moran, D.S. & Pandolf, K.B. (2001). *Wet Bulb Globe Temperature (WBGT) — historical review and current use for military and athletic operations.* Journal of Thermal Biology, 26(4-5), 473–479.

6. DRDO–DIPAS. (2023). *Research Areas: High Altitude Physiology and Performance Enhancement.* Defence Institute of Physiology and Allied Sciences, New Delhi.

---

## 👤 Author

**Mohammad Asif**
B.Tech – Computer Science & Engineering (Data Science Specialization)
Dr. A.P.J. Abdul Kalam Technical University, Lucknow

- 📧 asifmohammad99703@gmail.com
- 💼 [LinkedIn](https://www.linkedin.com/in/mdasif01)
- 🐙 [GitHub](https://github.com/MDAsif-bit01)

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

*Dataset credit: Met Office Hadley Centre (HadCRUT5) and Our World in Data. This project is an independent analytical study and is not affiliated with or endorsed by any of the data providers.*
