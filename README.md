<img width="525" height="171" alt="image" src="https://github.com/user-attachments/assets/854014d5-8e15-4eae-99c8-0b58f15a0b93" />



# Strategic Media Spending & Brand Resilience Analysis (2020)
### A Data Science Approach to Marketing Mix Modeling & Crisis Management

![Project Status](https://img.shields.io/badge/Status-Completed-success)
![Domain](https://img.shields.io/badge/Domain-Marketing%20Analytics-blue)
![Focus](https://img.shields.io/badge/Focus-Media%20Buying%20Strategy-orange)

## 1. Executive Summary

This project presents a comprehensive analysis of **Coca-Cola's media spending landscape** throughout the fiscal year 2020. Utilizing a high-dimensional dataset (approx. 200MB) encompassing granular media investment logs, this study applies advanced Data Science techniques to decode advertising strategies during a period of unprecedented global disruption (COVID-19).

The primary objective is to evaluate the efficiency of media allocation across various channels (TV, Digital, Outdoor, Cinema) and to reconstruct the brand's strategic response to shifting consumer behaviors. By leveraging **Time Series Forecasting**, **Cost Efficiency Analysis**, and **Competitive Benchmarking**, this project offers actionable insights into maximizing **Return on Ad Spend (ROAS)** and optimizing **Gross Rating Points (GRP)**.

## 2. Business Problem & Objectives

In the realm of **Brand Communication**, 2020 represented a "Black Swan" event. Traditional marketing models were disrupted by lockdowns and economic volatility. This project addresses the following critical business questions:

* **Media Mix Efficiency:** How did the allocation of the budget shift between traditional media (Linear TV, Out-of-Home) and digital channels during the pandemic peak (Q2 2020)?
* **Cost Dynamics:** What is the correlation between **Media Inflation** (Cost per Second) and **Audience Reach** (GRP) across different media types?
* **Crisis Resilience:** Did the brand adopt a "Recessionary Marketing" strategy (cutting spend) or a "Share of Voice" maintenance strategy?
* **Temporal Seasonality:** How did specific time slots (Dayparts) and weekly trends influence the cost-effectiveness of campaigns?

## 3. Project Structure

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

## 4. Methodology & Technical Approach

The project follows the **CRISP-DM** (Cross-Industry Standard Process for Data Mining) lifecycle, tailored for Marketing Analytics.

### A. Data Preprocessing & Engineering
* **High-Volume Data Handling:** Utilized `Pandas` optimized datatypes to process the 200MB+ dataset efficiently.
* **Temporal Feature Extraction:** Decomposed dates into `Quarter`, `Month`, `Week_of_Year`, and `Day_of_Week` to isolate seasonal trends.
* **Metric Calculation:** Engineered new features such as **CPP** (Cost Per Point) and **CPM** (Cost Per Mille) proxies to normalize cost efficiency comparisons.

### B. Exploratory Data Analysis (EDA)
* **Univariate Analysis:** Distribution of spend across `Medium Type` to visualize the **Marketing Mix**.
* **Bivariate Analysis:** Correlation matrices between `Seconds` (Duration) and `Cost` to detect pricing anomalies.
* **Trend Analysis:** Visualizing the "Pandemic Dip" in March-April 2020 and the subsequent "Rebound Strategy" in Q3/Q4.

### C. Advanced Analytics & Modeling
* **Marketing Mix Modeling (MMM) Concepts:** Applied regression techniques to estimate the contribution of each media channel to the overall visibility (GRP).
* **Time Series Forecasting:** Implemented **Facebook Prophet** to model weekly spending trends and forecast potential budget requirements for Q1 2021.
* **Anomaly Detection:** Statistical identification of outliers to pinpoint specific high-impact campaigns or erroneous data entries.

## 5. Key Insights & Strategic Deductions

* **Channel Migration:** A statistically significant pivot was observed from **Out-of-Home (OOH)** media to **Digital and TV** during the lockdown months, reflecting an agile adaptation to consumer mobility restrictions.
* **Cost Efficiency:** The analysis revealed that while TV commanded the highest total budget, specific niche channels provided a lower **Cost Per GRP**, suggesting opportunities for budget reallocation.
* **The "V-Shape" Recovery:** Spending patterns exhibited a sharp decline in early Q2 followed by an aggressive recovery in Q3, indicating a strategy to capitalize on "Revenge Spending" consumer behavior.
* **Daypart Optimization:** Analysis of `Daypart` data suggests that "Prime Time" spots yielded diminishing returns compared to specific "Day Time" slots, challenging traditional media buying heuristics.

## 🔒 Data Privacy & Usage Policy

**⚠️ Important Notice:**
The dataset utilized in this project is **proprietary** and was provided under a strict **Non-Disclosure Agreement (NDA)**. To ensure full compliance with privacy standards and ethical guidelines, please observe the following:

* **Exclusion of Raw Data:** The raw data files are **not included** in this repository to maintain confidentiality.
* **Anonymization:** All sensitive information presented in this documentation or notebooks has been **anonymized/masked** for demonstration purposes.
* **Replication:** If you wish to run this project locally, you must provide your own dataset that adheres to the structure specified in the `docs/data_schema.md` file.

---

## Data Obfuscation & Scaling (Veri Maskeleme ve Ölçeklendirme)

> **To protect the proprietary information (mülkiyet hakları saklı bilgiler) of the data provider (veri sağlayıcı), all financial figures (finansal rakamlar) and volume metrics (hacim metrikleri) have been scaled (ölçeklendirilmiş) or obfuscated (maskelenmiş/gizlenmiş). While the statistical relationships (istatistiksel ilişkiler) and trends (eğilimler) remain intact (bozulmadan korunmuş) for analysis purposes (analiz amaçları), the absolute values (mutlak değerler) do not represent actual business results (gerçek iş sonuçları).**

---

---
*Disclaimer: This project is for educational and portfolio purposes. The analysis is based on a sample dataset and utilizes Data Science methodologies to derive strategic marketing insights.*
