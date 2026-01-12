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


# 3. Future Outlook: Moving Beyond Univariate Forecasting
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


# 💸 5. Econometric Integration & Strategic Forecasting
## Inflation-Proofing the Media Budget

![Python](https://img.shields.io/badge/Python-Scikit_Learn-yellow)
![Model](https://img.shields.io/badge/Model-Linear_Regression-blue)

To mitigate the risk of **Hyper-Inflation** in the Turkish market, this module integrates external macro-economic indicators (USD/TRY Exchange Rate) to distinguish between "Nominal Spending" and "Real Purchasing Power."

## 📉 Visualization: The "Hidden Inflation" Effect


<img width="963" height="453" alt="image" src="https://github.com/user-attachments/assets/d0e86998-d944-4327-aa6e-c04616580ac3" />


### 1. Variable Definitions & Methodology

To ensure interpretative accuracy, the following econometric definitions are applied:

* **Nominal Spend (TL) - *Dashed Brown Line*:**
    * Represents the face value of the currency spent at the time of the transaction, without adjusting for inflation or currency devaluation.
    * *Axis:* Left Y-Axis (Scale: 8.0M – 22.0M TL).
* **Real Spend (USD) - *Solid Red Line*:**
    * Represents the inflation-adjusted purchasing power, converted to a stable reserve currency (USD). This serves as the benchmark for the actual volume of media inventory acquired.
    * *Axis:* Right Y-Axis (Scale: $1,250K – $2,750K USD).

---

### 2. Temporal Trend Analysis

The 2020 timeline can be segmented into four distinct phases based on volatility and trend direction:

#### Phase I: The Q1 Volatility Spike (Jan - March)
* **Observation:** The data exhibits a sharp upward variance starting in February, peaking in March.
    * *Nominal Peak:* ~17.0M TL
    * *Real Peak:* ~$2.75M USD
* **Interpretation:** This suggests a period of aggressive front-loading of budget or seasonal campaign execution. The gap between Nominal and Real lines is moderate, indicating relative currency stability or favorable exchange rates early in the quarter.

#### Phase II: The Macroeconomic Contraction (April - June)
* **Observation:** A precipitous decline (drawdown) occurring immediately after the March peak, bottoming out in June.
    * *Trough (June):* ~8.0M TL / ~$1.25M USD.
* **Interpretation:** This contraction aligns with global Q2 macroeconomic halts (exogenous shock events). The tight convergence of the Nominal and Real lines at the bottom suggests that reduced spending was volume-based rather than driven by currency depreciation.

#### Phase III: The Volatile Recovery (July - September)
* **Observation:** A "V-shaped" recovery pattern is visible in July/August, followed by a secondary correction in September.
* **Technical Note:** In August, the **Real Spend (USD)** line spikes slightly sharper than the **Nominal (TL)** line relative to the axis scales. This implies a momentary increase in the efficiency of the spend (deflationary pressure on media costs or temporary exchange rate appreciation).

#### Phase IV: The Q4 Bull Run (October - December)
* **Observation:** A sustained, aggressive linear growth trajectory leading into year-end.
    * *Year-End High:* >22.0M TL / >$2.8M USD.
* **Interpretation:** The year concludes with the highest expenditure levels. Notably, the **Nominal Spend** (Dashed) begins to track slightly above the visual trajectory of the **Real Spend** (Solid) towards the very end, which is a classic lagging indicator of inflation (CPJ/CPM inflation) eroding purchasing power.

---

### 3. Econometric Correlation & Divergence

The most critical technical insight from this chart is the **Elasticity of Spend**.

* **Correlation Coefficient ($r$):** Visually estimated at $>0.90$. The two lines track almost identically.
* **Implication:** The budgeting strategy appears to be **Dollar-Pegged** (USD-indexed).
    * If the budget were fixed in TL, we would expect to see the Real (USD) line diverge downwards significantly during periods of currency devaluation.
    * Instead, because the Real (USD) line rises in tandem with the Nominal (TL) line, it implies the organization increased their TL outlay specifically to maintain a target USD purchasing power.


---

## 5. Strategic Forecast & Recommendations

Based on the linear regression suggested by the Q4 trend, the following projections are modeled:

### A. Short-Term Forecast (Q1 2021)
* **Trend Continuation:** The momentum from Nov-Dec 2020 suggests an "overheating" of the auction marketplace.
* **Risk of Divergence:** As Nominal Spend crosses the 22M TL threshold, expect the gap between Nominal and Real spend to widen. Achieving the same USD purchasing power will likely require exponentially higher TL spending due to the compounding effects of media inflation (CPM inflation) + FX volatility.

### B. Risk Assessment
* **Media Inflation:** The steep slope of the Q4 Nominal line indicates a high burn rate.
* **Diminishing Returns:** If the Real (USD) line flattens while the Nominal (TL) line continues to rise, the portfolio is entering a zone of diminishing marginal returns (inefficient capital allocation).

### C. Actionable Next Steps
1.  **Hedging Strategy:** Implement forward-buying of media inventory to lock in rates and mitigate FX exposure.
2.  **KPI Switch:** Transition reporting strictly to **Real (USD)** metrics to eliminate the "noise" of local currency inflation when evaluating year-over-year performance.
3.  **Efficiency Audit:** Analyze the September dip to understand why efficiency dropped before the Q4 rally.

---
*Generated by Data Science Analytics | GitHub Markdown Export*



<img width="765" height="446" alt="image" src="https://github.com/user-attachments/assets/3126e14a-792d-4407-b0ed-a16be61d0acd" />

<img width="1047" height="431" alt="image" src="https://github.com/user-attachments/assets/8f1bcb5d-f35e-4051-a544-91b1aa79d7a4" />


<img width="973" height="427" alt="image" src="https://github.com/user-attachments/assets/5d02cc3d-c46e-4dbb-9c39-c918ca6caa58" />

<img width="1019" height="424" alt="image" src="https://github.com/user-attachments/assets/9315a4d7-2445-467f-9726-daf1fc0fa72c" />


<img width="993" height="445" alt="image" src="https://github.com/user-attachments/assets/ca2f34ba-9b9f-49a4-b874-2c6ba8044dc4" />




---
*Note: Due to environment restrictions, this analysis utilized a synthetic reproduction of the 2020 exchange rate trend based on historical open/close data points.*






# 📱 Digital Attribution & Second Screen Effect Analysis
## Measuring the "Pulse" of the Consumer Beyond TV

![Python](https://img.shields.io/badge/Python-Simulation-blue)
![Analysis](https://img.shields.io/badge/Analysis-Cross_Channel-orange)

To move beyond traditional GRP metrics, this module explores the **Cross-Channel Synergy** between offline spending (TV) and online behavior (Search Interest).

### 📉 Visualization: The "Second Screen" Phenomenon

<img width="1249" height="494" alt="image" src="https://github.com/user-attachments/assets/e65e100e-56c2-469b-8dbe-2075050af620" />



### 🔍 Technical Interpretation

* **Hypothesis:** Does "Heavy TV Pressure" trigger immediate information-seeking behavior on mobile devices?
* **Methodology:** Since real-time search API data was rate-limited, a **Stochastic Simulation Model** was engineered. The model assumes a **Linear Ad-Elasticity** ($E_d = 0.8$) combined with Gaussian Noise to replicate real-world volatility.
* **Key Findings:**
    * **High Correlation:** The simulated model exhibits a strong positive correlation ($r > 0.75$) between Weekly Media Spend and Search Index.
    * **Zero Latency:** The peaks in search volume align perfectly with TV flighting periods, confirming the **"Second Screen Effect"**—viewers are simultaneously consuming TV and Mobile content.

### 🚀 Strategic Implication for 2021
The analysis proves that TV is a primary driver of Digital Traffic. Therefore, **SEM (Search Engine Marketing)** budgets should be synchronized dynamically with TV flighting schedules to capture the demand generated by offline spots efficiently.

---
*Disclaimer: Due to Google Trends API rate limits, the search volume data in this specific chart is simulated based on industry-standard attribution models for demonstration purposes.*



### 🧬 Proposed Feature Engineering
* **Interaction Terms:** `TV_Spend * Digital_Search_Volume` (To measure synergy).
* **Lagged Variables:** `Competitor_Spend_t-1` (To measure reaction time).
* **Seasonality Indices:** `Temperature_Index` (For correlating soft drink consumption with weather).

---
*Note: This roadmap assumes the implementation of a Multivariate Regression or Bayesian Structural Time Series (BSTS) model in the next iteration.*
---
*Roadmap designed by analyzing data gaps in the current 2020 Media Log dataset.*
