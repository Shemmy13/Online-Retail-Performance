# Online Retail Performance Analysis

## 📌 Project Overview
In this project, I built an end-to-end pipeline to clean, analyze, and visualize a retail dataset containing over 540,000 transactions. Using **Python, and Power BI**, I dug into the numbers to uncover what actually drives sales, how customers behave, and where the business can optimize its operations.

---

## Tools & Technologies Used
* **Data Cleaning & Analysis:** Python & Jupyter Notebook
* **Dashboard & Visualization:** Power BI (DAX, Interactive Reporting)

---

## The Data Cleaning Process (Handling Messy Data)
Real-world data is rarely clean. To make sure the analysis was accurate, I ran the raw data through a thorough cleanup process in Python:

* **Fixing Missing Values:** I found 1,454 rows missing product descriptions and dropped them. I also noticed 135,080 transactions missing a `CustomerID`. Instead of deleting them and losing millions in sales data, I labeled them as `"Guest"` so we could still track their revenue impact.
* **Removing Duplicates:** Spotted and removed 5,268 identical duplicate rows.
* **Filtering Out Noise:** Deleted rows with negative quantities and negative unit prices. These usually represent cancelled orders, returns, or system errors, which would have skewed our actual sales performance.
* **Standardizing Text:** Standardized country names and product descriptions (using formatting like `.str.title()`) to fix inconsistencies and make grouping easier.

### Adding New Features
To get deeper insights, I expanded the dataset by calculating a few new columns:
* **`Sales` (Revenue):** Created by multiplying `Quantity` and `UnitPrice`.
* **Time Dimensions:** Extracted `Month` and `Year` from the invoice dates to track sales trends over time.

---

## Key Insights & Real Business Recommendations

### 1. "Guest" Checkouts are a Goldmine
* **The Insight:** A massive chunk of total revenue comes from unlogged "Guest" accounts rather than returning registered customers. 
* **The Action:** The business shouldn't leave this money on the table. We should introduce quick, low-friction loyalty incentives or one-click account creation at checkout to turn these anonymous buyers into repeat customers.

### 2. Q4 Seasonal Revenue Surge
* **The Insight:** Sales experience an absolute skyrocket between September and December, driven by holiday shopping.
* **The Action:** Supply chain and inventory managers need to stock up heavily by late summer. Running out of best-selling items in October or November means losing out on the most profitable time of the year.

### 3. A Few Products Carry the Weight (Pareto Principle)
* **The Insight:** A very small percentage of products drive the vast majority of total sales and revenue. 
* **The Action:** Give these top-performing products the best real estate on the website. You can also bundle these highly popular items with slower-moving inventory to clear out warehouse space.

### 4. UK Dominates Volume, but Europe Spends More Per Order
* **The Insight:** The UK brings in the highest total revenue by far. However, international markets like the Netherlands and Ireland (Eire) actually have a much higher Average Order Value (AOV).
* **The Action:** Keep defending the core UK market, but launch targeted marketing campaigns in the Netherlands and Ireland to capture more of those high-spending, high-margin international orders.

---

## Final Data & Performance Summary

### Data Pipeline Impact
| Stage | Total Rows | Total Columns | What Changed? |
| :--- | :--- | :--- | :--- |
| **Initial Dataset** | 541,909 | 8 | Raw, uncleaned transaction logs. |
| **Cleaned Dataset** | **524,878** | **11** | Validated data with new revenue and date features. |

### Top 5 Global Markets by Sales
| Rank | Country | Total Sales ($) |
| :--- | :---: | :--- |
| 1 | United Kingdom | 9,001,744.09 |
| 2 | Netherlands | 285,446.34 |
| 3 | Eire | 283,140.52 |
| 4 | Germany | 228,678.40 |
| 5 | France | 209,625.37 |

---

## What's Inside This Repository
* 📁 `OnlineRetail_Cleaned.csv` – The final, clean dataset ready for analysis.
* 📓 `OnlineRetail_Cleaned.ipynb` – The Jupyter Notebook containing all my Python code for cleaning and exploring the data.
* 📊 `OnlineRetailDashboard.pbix` – The interactive Power BI dashboard with dynamic filters and customer KPI tracking.
