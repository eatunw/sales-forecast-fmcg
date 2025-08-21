# sales-forecast-fmcg
Time series forecasting and demand planning for daily-level FMCG sales transactions 

This project focuses on forecasting sales performance for a Fast-Moving Consumer Goods (FMCG) company using a real-world dataset. It demonstrates how to preprocess raw transactional data with Python (Pandas), analyze patterns in Excel pivot tables, and build interactive dashboards in Power BI to visualize trends and predictions.

# Problem Statement

FMCG businesses rely on accurate sales forecasts to:

- Plan inventory and avoid stockouts.
- Optimize supply chain operations.
- Anticipate seasonal demand shifts.
- Improve decision-making for pricing and promotions.

This project addresses the question: *“What will sales look like in the coming months, and which products or regions will drive them?”*

  ## 📦 Dataset
- **Source**: Kaggle – FMCG_2022_2024.csv  
  https://www.kaggle.com/datasets/beatafaron/fmcg-daily-sales-data-to-2022-2024
- Time Period: 2022 – 2024
- Key Fields:
   - Date
   - Product
   - Category
   - Region
   - Sales Volume
   - Revenue
 

All data cleaning—filtering nulls, handling negative quantities, standardizing dates—was done via python scripts in jupyter notebook in the **`Sales_Forecasting.ipynb/`** folder. 

---

## 🛠 Tools & Technologies
| Tool                          | Purpose                                          |
|-------------------------------|--------------------------------------------------|
| **Jupyter notebook (python)** | Data cleaning, transformation, standardization   |
| **Power BI**                  | Dashboard design, visuals, interactive filters   |
| **Git & GitHub**              | Version control and portfolio hosting            |
| **Excel**                     | Pivot tables for quick aggregation and validation|


---

## 📊 Dashboard Preview

![Dashboard Overview](https://github.com/eatunw/sales-forecast-fmcg/blob/main/visual%20(6).png)

---

## 🚀 Key Findings
- **Busiest months**: Strong ramp from spring to late-year; peak months are in Q4 with notable strength in Nov–Dec. Weekday seasonality shows higher demand toward the end of the week and weekends.
- **Accurate forecast method**: A lightweight hybrid of seasonal naive (12-month seasonality) plus 3-month moving average delivered MAPE ≈ 9.5% and MAE ≈ 10,859 on the final 3 months. This is a solid baseline; can be enhanced with richer models if needed.
- **Business implications**:
   - Plan higher production and logistics capacity for Q4 and late-week spikes.
   - Promotions scheduled mid–late week may yield outsized returns.
   - Inventory holdings should reflect the next-month forecast of ~120,162 versus a current benchmark stock of ~151 units (benchmark likely needs to be in the same unit basis).

---

## 📈 Visualizations & Analysis
1. **Brand Performance & Inventory Health**  
   - ![This chart compares total sales (units_sold) against total inventory (stock_available) by brand, revealing critical issues in inventory management. (%)](https://github.com/eatunw/ecommerce-churn-analysis/blob/main/Screenshot%202025-07-20%20132000.png)  
2. **Top 10 Countries by Churn Rate**
   - ![image](https://github.com/eatunw/ecommerce-churn-analysis/blob/main/Screenshot%202025-07-20%20132000.png)  
3. **Total Number of Sales Over Time**
   - ![image](https://github.com/eatunw/ecommerce-churn-analysis/blob/main/Screenshot%202025-07-20%20132752.png)  
4. **Unique Customer Per Country**
   - ![image](https://github.com/eatunw/ecommerce-churn-analysis/blob/main/Screenshot%202025-07-20%20131909.png)  
5. **Top Quantity Sold**
   - ![image](https://github.com/eatunw/ecommerce-churn-analysis/blob/main/Screenshot%202025-07-20%20131711.png)  
6. **Average Unit Price**
   - ![image](https://github.com/eatunw/ecommerce-churn-analysis/blob/main/Screenshot%202025-07-20%20131745.png)  
7. **Top Products for Retained Users**
   - ![image](https://github.com/eatunw/ecommerce-churn-analysis/blob/main/Screenshot%202025-07-20%20131835.png)  
  

---

## ✏️ SQL Scripts Overview
- **`data_cleaning.sql`**  
  - I converted `InvoiceDate` strings to DATETIME  
  - I filtered out null `CustomerID` and negative quantities  
  - Deduplicates cancelled transactions  
- **`churn_analysis.sql`**  
  - I derived each customer’s last purchase date  
  - I calculated `DaysSinceLast` and flags `IsChurned` (90+ days)  
  - I got aggregates churn metrics and cohorts


---

## Contact
  
- **Contact**: [EMAIL](atundeemmanuel7@gmail.com)


 
FMCG-Sales-Forecasting/
│── data/
│   └── FMCG_2022_2024.csv
│── notebooks/
│   └── analysis.ipynb        # Python cleaning & EDA
│── excel/
│   └── pivots.xlsx           # Pivot tables summary
│── powerbi/
│   └── sales_forecast.pbix   # Power BI dashboard
│── README.md
