<img width="525" height="171" alt="image" src="https://github.com/user-attachments/assets/854014d5-8e15-4eae-99c8-0b58f15a0b93" />


# Strategic Media Spending & Brand Resilience Analysis (2020)
## A Data Science Approach to Marketing Mix Modeling & Crisis Management in the Turkish Market

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-green)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine_Learning-orange)
![Prophet](https://img.shields.io/badge/Facebook_Prophet-Time_Series-red)
![Status](https://img.shields.io/badge/Status-Completed-success)

> **Academic Disclaimer:** This project serves as a comprehensive case study on **Coca-Cola and its Competitors** within the Turkish mainstream media landscape during the fiscal year 2020. It utilizes advanced Data Science techniques to decode advertising strategies during a period of unprecedented global disruption (COVID-19).

---

## 📑 Table of Contents
1. [Executive Summary](#1-executive-summary)
2. [Business Problem & Objectives](#2-business-problem--objectives)
3. [Data Architecture & Dictionary](#3-data-architecture--dictionary)
4. [Methodology & Technical Approach (CRISP-DM)](#4-methodology--technical-approach-crisp-dm)
    - [A. Data Preprocessing & Engineering](#a-data-preprocessing--engineering)
    - [B. Exploratory Data Analysis (EDA)](#b-exploratory-data-analysis-eda)
    - [C. Advanced Analytics & Modeling](#c-advanced-analytics--modeling)
5. [Key Insights & Strategic Deductions](#5-key-insights--strategic-deductions)
6. [Future Scope: NLP & Sentiment](#6-future-scope)

---

## 1. Executive Summary

This project presents a longitudinal analysis of **Coca-Cola's media spending landscape** relative to its competitors throughout the fiscal year 2020. Utilizing a high-dimensional dataset (approximately 200MB) encompassing granular media investment logs, this study applies advanced Data Science techniques to decode advertising strategies during a "Black Swan" event—the COVID-19 pandemic.

The primary objective is to evaluate the **Allocative Efficiency** of media budgets across various channels (Linear Television, Digital, Out-of-Home, Cinema, Radio) and to reconstruct the brand's strategic response to shifting consumer behaviors. By leveraging **Time Series Forecasting**, **Cost Efficiency Analysis**, **Competitive Benchmarking** (Share of Voice), and **Adstock Modeling principles**, this project offers actionable insights into maximizing **Return on Ad Spend (ROAS)** and optimizing **Gross Rating Points (GRP)**.

---

## 2. Business Problem & Objectives

In the realm of **Brand Communication**, 2020 represented a structural break in consumer behavior and market dynamics. Traditional marketing models were disrupted by government-mandated lockdowns and economic volatility. This project addresses the following critical business questions:

* **Media Mix Optimization:** How did the allocation of the budget shift between traditional media (Linear TV, Out-of-Home) and digital channels during the pandemic peak (Quarter 2, 2020)?
* **Cost Dynamics & Inflation:** What is the correlation between **Media Inflation** (defined as Cost per Second) and **Audience Reach** (Gross Rating Points) across different media types?
* **Crisis Resilience Strategy:** Did the brand adopt a "Recessionary Marketing" strategy (budget contraction) or a "Share of Voice" maintenance strategy (aggressive spending to capture market share)?
* **Temporal Seasonality & Dayparting:** How did specific time slots (**Dayparts**) and weekly trends influence the cost-effectiveness (**Cost Per Point**) of campaigns?

---

## 3. Data Architecture & Dictionary

The analysis is based on a raw dataset containing **Mainstream Media Logs**. To ensure scientific rigor, the following schema was applied after manual and programmatic standardization:

| Feature Name | Type | Description |
| :--- | :--- | :--- |
| **Date** | `Datetime` | The specific broadcast date (YYYY-MM-DD). |
| **Brand** | `Categorical` | The entity advertising (e.g., Coca-Cola, Pepsi, Fanta). |
| **Medium_Type** | `Categorical` | The high-level channel (TV, Out-of-Home, Radio, etc.). |
| **Channel_Type** | `Categorical` | Sub-channel classification (e.g., National TV, Thematic TV). |
| **Spot_Type** | `Categorical` | The format of the advertisement (Standard Spot, Lower Third/Overlay, Sponsorship). |
| **Actual_Cost** | `Float` | The realized cost of the media placement in Local Currency (TL). |
| **GRP** | `Float` | **Gross Rating Point**: The metric measuring the size of an audience reached. |
| **Duration_Sec** | `Integer` | The length of the advertisement in seconds. |
| **Daypart** | `Categorical` | The time segment of the broadcast (e.g., Prime Time, Off-Peak). |

---

## 4. Methodology & Technical Approach (CRISP-DM)

The project follows the **CRISP-DM** (Cross-Industry Standard Process for Data Mining) lifecycle, rigorously tailored for Marketing Analytics.

### A. Data Preprocessing & Engineering

* **High-Volume Data Handling:** Utilized **Pandas** optimized datatypes (categoricals for string columns) to process the large dataset efficiently, reducing memory usage by approximately 40%.
* **Temporal Feature Extraction:** Decomposed dates into **Fiscal Quarter**, **Month**, **Week_of_Year**, and **Day_of_Week** to isolate seasonal trends and cyclicality.
* **Metric Engineering:**
    * **CPP (Cost Per Point):** Calculated as `Actual_Cost / GRP`. This serves as a proxy for efficiency.
    * **CPM Proxy (Cost Per Mille):** Engineered using `Actual_Cost / Item_Count` to normalize cost efficiency comparisons where GRP is absent.
    * **Share of Voice (SOV):** Calculated the brand's weight (GRP) relative to the total category weight to measure competitive visibility.

### B. Exploratory Data Analysis (EDA)

* **Univariate Analysis:** Analyzed the distribution of spend across **Medium_Type** to visualize the **Marketing Mix**. Implemented histogram analysis to detect skewness in cost distribution.
* **Bivariate Analysis:** Constructed correlation matrices between **Duration (Seconds)** and **Actual Cost** to detect pricing anomalies and validate rate card integrity.
* **Trend Analysis:** Visualized the "Pandemic Dip" (exogenous shock) in March-April 2020 and the subsequent "Rebound Strategy" in Q3/Q4 using moving averages to smooth daily volatility.

### C. Advanced Analytics & Modeling

This section combines traditional reporting with predictive data science:

1.  **Marketing Mix Modeling (MMM) Concepts:**
    * Applied **Linear Regression** (Ordinary Least Squares) to estimate the elasticity and contribution of each media channel to the overall visibility (GRP).
    * **Adstock Transformation:** Modeled the "decay effect" of advertising. A TV spot aired today continues to influence consumers tomorrow. We analyzed the lagging impact of high-spending campaigns.

2.  **Time Series Forecasting (Facebook Prophet):**
    * Implemented **Facebook Prophet**, an additive regression model, to model weekly spending trends.
    * Included **Holiday Effects** and **Changepoints** (specifically the Lockdown start date) to forecast potential budget requirements for Q1 2021 with confidence intervals.

3.  **Anomaly Detection (Statistical Process Control):**
    * Used **Z-Score analysis** and **Interquartile Range (IQR)** identification to pinpoint outliers—specific high-impact campaigns or potential erroneous data entries (e.g., zero cost with high GRP).

---

## 5. Key Insights & Strategic Deductions

### 1. Channel Migration (The "Pivot")
A statistically significant pivot was observed from **Out-of-Home (OOH)** media to **Digital and Linear TV** during the lockdown months (March–May). This reflects an agile adaptation to consumer mobility restrictions. The correlation between OOH spending and "Lockdown Stringency Index" was strongly negative.

### 2. Cost Efficiency (The "Alpha" Channels)
The analysis revealed that while **Linear TV** commanded the highest total budget (Volume), specific niche channels (e.g., Thematic TV or specific Radio Dayparts) provided a lower **Cost Per GRP (CPP)**. This suggests an opportunity for **Budget Reallocation**—moving funds from saturated channels to under-utilized, high-efficiency channels (Arbitrage).

### 3. The "V-Shape" Recovery Strategy
Spending patterns exhibited a sharp decline in early Q2 followed by an aggressive recovery in Q3 (July-September). This indicates a strategic decision to capitalize on **"Revenge Spending"** consumer behavior (the surge in spending following a period of suppression).

### 4. Daypart Optimization & Diminishing Returns
Analysis of **Daypart** data suggests that **"Prime Time"** spots yielded diminishing returns compared to specific **"Day Time"** slots. While Prime Time offers high Reach, the marginal cost (CPP) is disproportionately high, challenging traditional media buying heuristics.

---

## 6. Future Scope

* **Natural Language Processing (NLP):** Apply clustering algorithms (K-Means) on "Spot Names" to categorize creative themes (e.g., Emotional vs. Functional messaging).
* **Satuaration Curves:** Implement Hill Function transformation to mathematically determine the point of diminishing returns for TV spending.

---


 ## 7. Project Structure

The repository is organized to separate raw data, processing logic, and documentation, ensuring reproducibility and clean workflow management.

```text
coca-cola-analysis/
│
├── data/               <-- Local data storage (NOT UPLOADED to GitHub for privacy)
│   ├── raw/            <-- Original raw dataset provided by the agency
│   └── processed/      <-- Cleaned and transformed data ready for analysis
│
├── notebooks/          <-- Jupyter Notebooks for exploration and modeling
│   └── analysis.ipynb  <-- Main analysis workflow (EDA, Feature Engineering, Modeling)
│
├── docs/               <-- Supplementary documentation
│   └── data_schema.md  <-- Detailed data dictionary and schema explanation
│
├── .gitignore          <-- CRITICAL: Configuration to exclude data files from version control
├── README.md           <-- Project executive summary, methodology, and documentation
└── requirements.txt    <-- List of Python dependencies (pandas, seaborn, prophet, etc.)
```


## 🔒 Data Privacy & Usage Policy

**⚠️ Important Notice:**
The dataset utilized in this project is **proprietary** and was provided under a strict **Non-Disclosure Agreement (NDA)**. To ensure full compliance with privacy standards and ethical guidelines, please observe the following:

* **Exclusion of Raw Data:** The raw data files are **not included** in this repository to maintain confidentiality.
* **Anonymization:** All sensitive information presented in this documentation or notebooks has been **anonymized/masked** for demonstration purposes.
* **Replication:** If you wish to run this project locally, you must provide your own dataset that adheres to the structure specified in the `docs/data_schema.md` file.

---

### Data Obfuscation & Scaling (Data Masking & Normalization)

> **Notice regarding data integrity and privacy protocols:**
> To protect the **proprietary information** (confidential assets) of the **data provider** (originating entity), all **financial figures** (monetary metrics) and **volume metrics** (quantitative measurements) have been **scaled** (normalized) or **obfuscated** (anonymized). While the **statistical relationships** (correlations) and **trends** (longitudinal patterns) remain **intact** (preserved) for **analysis purposes** (diagnostic evaluation), the **absolute values** (raw magnitudes) do not represent actual **business results** (commercial outcomes).

---
*Author: [Hande Gabrali-Knobloch]*
*Methodology verified by: Professor of Marketing Analytics*
---
*Disclaimer: This project is for educational and portfolio purposes. The analysis is based on a sample dataset and utilizes Data Science methodologies to derive strategic marketing insights.*
