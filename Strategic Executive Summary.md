# 📊 1. Strategic Executive Summary (Key Insights)

The analysis of the dataset yields four critical conclusions regarding the 2020 media landscape:

* **Dominance of TV (Overwhelming Precedence):** Out of a total budget of **162.37 Million TL**, **91.8%** was allocated to Television. This indicates that brands selected TV as a "Safe Haven" during the period of uncertainty.
* **Efficiency Champion:** Interestingly, despite commanding the highest expenditure, TV offered the **lowest Cost Per Point (CPP)**. While the absolute cost appears high, it remains the most cost-effective medium relative to the audience reach it delivers.
* **Crisis Reflex (V-Shaped Recovery):** A sharp decline in spending is observed during the "Lockdown" period between March and May. However, budgets returned to normal levels in June, driven by a **"Revenge Spending"** strategy.
* **Market Leader:** In terms of total visibility (**Share of Voice**), **COCA-COLA** leads the market with **25.5%**. It has established a clear dominance in share of voice against its competitors.

---

# 📈 2. Analysis Outputs & Visualizations

### A. Media Mix Optimization

<img width="862" height="406" alt="image" src="https://github.com/user-attachments/assets/0763d34f-0fd1-4a27-9d09-0458bdd1cb58" />

* **Visualization:** Refer to the chart titled *Media Mix Optimization*.
* **Interpretation:** Budgets for Out-of-Home (OOH) and Cinema remained at marginal levels due to the pandemic. As Digital Media was not included in this specific dataset, Television alone dominated the media mix.

### B. Crisis Resilience

<img width="1043" height="482" alt="image" src="https://github.com/user-attachments/assets/058f98ea-a80c-4d4b-999d-35918f15a1ae" />


* **Visualization:** Refer to the chart titled *Crisis Resilience* containing the red shaded region.
* **Interpretation:** The red shaded area represents the full lockdown period (March–June). The graph hits rock bottom during this interval. Brands implemented a **"Recessionary Marketing"** (Budget Contraction) strategy rather than a "Share of Voice Maintenance" strategy.

### C. Cost Efficiency (CPP)

<img width="922" height="411" alt="image" src="https://github.com/user-attachments/assets/25c1ab01-0932-4775-bc9a-9b21e69fe7bd" />

<img width="721" height="414" alt="image" src="https://github.com/user-attachments/assets/fc696536-e2df-4b0e-8963-d04c62e2ed95" />

<img width="872" height="486" alt="image" src="https://github.com/user-attachments/assets/25c96da9-a9d2-4496-b471-25088d09ad31" />

* **Visualization:** Refer to the chart titled *Cost Efficiency*.
* **Interpretation:** The shorter the bar, the more efficient the medium. TV is positioned on the far left (most efficient), while Magazines and Newspapers are positioned further to the right (expensive reach).

### D. Competitive Benchmarking

<img width="632" height="540" alt="image" src="https://github.com/user-attachments/assets/2f790e89-b9ce-4127-90df-0f5b9a8510a4" />

* **Visualization:** Refer to the pie chart titled *Competitive Benchmarking*.
* **Interpretation:** Coca-Cola is likely followed by Pepsi and Fanta. The size of the "Others" slice indicates how fragmented the market structure is.

### E. Strategic Forecast

<img width="888" height="519" alt="image" src="https://github.com/user-attachments/assets/28680c6c-e876-4310-a784-c385377185d0" />

* **Visualization:** Refer to the trend line chart titled *Strategic Forecast*.
* **Interpretation:** The orange dashed line illustrates the trajectory of Q1 2021 spending if current trends persist. Due to high spending at the end of the year (Q4), the model predicts an **upward opening** for the beginning of 2021.


# 🔮 Future Outlook: Moving Beyond Univariate Forecasting
## A Roadmap for "Next-Generation" Predictive Media Modeling

While the current *Prophet* and *Linear Regression* models provide a solid baseline based on historical run-rates, a truly robust Strategic Forecast requires integrating **Multivariate Regressors**. To elevate the prediction accuracy from "Descriptive" to "Prescriptive," the following dimensions should be integrated into the next phase of the project:

| **Strategic Dimension** | **Objective** | **Data Science Implementation Strategy** |
| :--- | :--- | :--- |
| **1. Econometric Integration** | **Inflation-Proofing** | Incorporate external datasets such as **CPI (Consumer Price Index)** and **FX Rates (USD/TRY)** as exogenous regressors in SARIMAX models. This allows the model to differentiate between organic budget growth and forced inflationary spending. |
| **2. Game Theory Modeling** | **Competitor Response** | Move from static forecasting to dynamic **"War Gaming"**. Analyze the *Cross-Elasticity* of competitor Spend vs. our Share of Voice. Predict required defensive spending thresholds based on competitor GRP momentum signals. |
| **3. Inventory Futures** | **Scarcity Pricing** | Build a **"Demand-Supply"** index for TV inventory. Quantify the *Cost-Per-GRP (CPP)* volatility during peak seasons (Q4) to forecast not just the budget needed, but the actual **Purchasing Power** of that budget. |
| **4. Synergy Attribution** | **Mix Optimization** | Utilize **Media Mix Modeling (MMM)** with Ridge Regression to quantify the interaction effects between channels (e.g., *Does increasing TV spend improve OOH recall?*). Forecast the optimal split rather than just the total volume. |

### 🛠️ Proposed Technical Architecture for Phase 2
* **Model:** Migration from `Prophet` to **`Bayesian Structural Time Series (BSTS)`**.
* **Feature Set:** Historical Spend + Seasonality + *Macro Indicators* + *Competitor SOV*.
* **Output:** A "Scenario-Based" forecast (Best Case / Worst Case / Inflation-Adjusted Case).


# 🛠️ Requirements for Phase 2: Advanced Predictive Modeling
## Data Architecture & Integration Roadmap

To transition from *Descriptive Analytics* to *Prescriptive Strategic Forecasting*, the current dataset must be enriched with the following exogenous variables. This integration enables the measurement of "Real Impact" vs. "Nominal Spending."

| **Data Layer** | **Required Dataset** | **Purpose in Modeling** | **Target Analysis** |
| :--- | :--- | :--- | :--- |
| **1. Macro-Economic** | [`USD_TRY_Exchange_Rate.csv`](https://www.tcmb.gov.tr/kurlar/kur2020_tr.html) | To deflate media costs and calculate **"Purchasing Power Parity"** of the budget. | **Econometric Integration** (Inflation-Proofing) |
| **2. Consumer Behavior** | `Sales_Volume_Weekly.csv` OR `Google_Trends_Index.csv` | To serve as the **Dependent Variable (Y)**. Essential for measuring ROI and channel synergy. | **Synergy Attribution** & **MMM (Marketing Mix Modeling)** |
| **3. Competitive Intel** | `Category_Total_GRP.csv` | To calculate the dynamic **Share of Voice (SOV)** and detect competitor aggression levels. | **Game Theory Modeling** (Competitor Response) |
| **4. Inventory Supply** | `TV_Rate_Cards_2020.csv` | To establish a baseline price and identify **"Demand-Pull Inflation"** (Scarcity Pricing). | **Inventory Futures** (Price Forecasting) |

### 🧬 Proposed Feature Engineering
* **Interaction Terms:** `TV_Spend * Digital_Search_Volume` (To measure synergy).
* **Lagged Variables:** `Competitor_Spend_t-1` (To measure reaction time).
* **Seasonality Indices:** `Temperature_Index` (For correlating soft drink consumption with weather).

---
*Note: This roadmap assumes the implementation of a Multivariate Regression or Bayesian Structural Time Series (BSTS) model in the next iteration.*
---
*Roadmap designed by analyzing data gaps in the current 2020 Media Log dataset.*
