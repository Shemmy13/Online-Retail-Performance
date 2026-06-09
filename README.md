# # Online Retail Performance Analysis

## 📌 Project Overview
This project involves the development of an end-to-end data pipeline to clean, analyze, and visualize a retail dataset containing over 540,000 transactions. Utilizing Python and Power BI, the analysis uncovers key revenue drivers, evaluates customer purchasing behavior, and provides actionable recommendations to optimize business operations.

## Tools & Technologies Used
*   **Data Cleaning & Analysis:** Python (Pandas, NumPy) & Jupyter Notebook
*   **Dashboard & Visualization:** Power BI (DAX, Interactive Reporting)

---

## The Data Cleaning Process (Handling Messy Data)
Real-world transactional data requires rigorous preprocessing to ensure analytical accuracy. The raw dataset was processed using Python to address inconsistencies:

*   **Handling Missing Values:** Identified and removed 1,454 rows missing product descriptions. For the 135,080 transactions missing a `CustomerID`, rows were retained but labeled as **"Guest"** to ensure millions in transactional revenue were not lost while tracking overall financial impact.
*   **Removing Duplicates:** Detected and eliminated 5,268 identical duplicate rows to prevent artificial inflation of metrics.
*   **Filtering Anomalies:** Removed rows with negative quantities and negative unit prices (representing cancelled orders, returns, or system adjustments) to isolate true sales performance.
*   **Standardizing Text:** Normalized country names and product descriptions using text formatting rules (`.str.title()`) to eliminate grouping discrepancies.

### Feature Engineering
To deepen the analysis, the dataset was expanded with engineered dimensions:
*   **Sales (Revenue):** Calculated dynamically by multiplying `Quantity` and `UnitPrice`.
*   **Time Dimensions:** Extracted `Month` and `Year` from invoice dates to perform time-series and seasonal trend analysis.

---

## 💡 Key Insights & Business Recommendations

### 1. Optimize the "Guest" Checkout Funnel
*   **The Insight:** A substantial percentage of total revenue originates from unlogged "Guest" accounts rather than returning registered profiles.
*   **The Action:** Implement low-friction loyalty incentives or a one-click account creation prompt post-checkout to convert anonymous, high-value buyers into identifiable repeat customers.

### 2. Capitalize on Q4 Seasonal Surges
*   **The Insight:** Transaction volume experiences exponential growth between September and December, heavily driven by holiday shopping patterns.
*   **The Action:** Supply chain management should optimize safety stock levels by late summer. Mitigating stockouts during October and November protects the year's most profitable operational window.

### 3. Inventory Rationalization via the Pareto Principle
*   **The Insight:** A small fraction of core products accounts for the vast majority of gross revenue and transaction volume.
*   **The Action:** Prioritize high-performing products by giving them prime visibility on the platform. Additionally, implement cross-selling strategies that bundle slower-moving items with these top sellers to accelerate inventory turnover and optimize warehouse space.

### 4. Market Penetration: UK Volume vs. European Value
*   **The Insight:** While the UK dominates absolute sales volume, international markets—specifically the Netherlands and Ireland (Eire)—exhibit significantly higher Average Order Value (AOV).
*   **The Action:** Maintain defensive marketing strategies to secure the core UK market share, while deploying targeted, high-margin campaigns in the Netherlands and Ireland to capture premium order values.

---

## 📊 Performance & Data Summary

### Data Pipeline Impact
| Stage | Total Rows | Total Columns | Operational Change |
| :--- | :--- | :--- | :--- |
| **Initial Dataset** | 541,909 | 8 | Raw, uncleaned transaction logs. |
| **Cleaned Dataset** | 524,878 | 11 | Validated data enriched with revenue and temporal features. |

### Top 5 Global Markets by Sales
| Rank | Country | Total Sales ($) |
| :--- | :--- | :--- |
| **1** | United Kingdom | 9,001,744.09 |
| **2** | Netherlands | 285,446.34 |
| **3** | Eire | 283,140.52 |
| **4** | Germany | 228,678.40 |
| **5** | France | 209,625.37 |


## What's Inside This Repository
* 📁 `OnlineRetail_Cleaned.csv` – The final, clean dataset ready for analysis.
* 📓 `OnlineRetail_Cleaned.ipynb` – The Jupyter Notebook containing all my Python code for cleaning and exploring the data.
* 📊 `OnlineRetailDashboard.pbix` – The interactive Power BI dashboard with dynamic filters and customer KPI tracking.
