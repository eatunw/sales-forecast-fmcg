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

![Dashboard Overview](https://github.com/eatunw/ecommerce-churn-analysis/blob/main/e-commerce%20dashboard.png)

---

## 🚀 Key Findings
- **Countries with the highest churn**: Australia, France, Germany, Netherlands and Norway top the list. Their churn rates approach 
100, meaning almost all customers in those markets bought only once during the observed period  
- **Total quantity sold by country**: As expected, the United Kingdom dominates overall volume, followed (at a much smaller scale) by Ireland, Norway, France and Germany.  
- **Average unit price by product**: The ten products shown command the highest mean prices; they are typically large decorative items (e.g., wall clocks, cake stands) rather than low-ticket trinkets  
- **Top-5 products by sales value**: High-velocity + mid-to-high price point gives these five items the largest revenue contributions. 
- **Unique customers per country**: Again the United Kingdom is by far the largest base, but several EU markets contribute dozens of unique buyers each.
- **Average churn rate**: Overall, about 86% of customers are single-purchase, so retention efforts have huge room for improvement.
- **Products driving repeat purchases**: Repeat-customer spend concentrates around decorative homeware (e.g., Red Woolly Hottie, Regency Cake-stand, Babushka Boxes, Chilli Lights, Hanging Heart T-Light Holder). These items resonate strongly enough for customers to buy again.
- **Behavioral Insight**: Customers with more than 3 distinct purchase days are **70% less** likely to churn.

---

## 📈 Visualizations & Analysis
1. **KPI Cards**  
   - ![Total vs. churned customers & churn rate (%)](https://github.com/eatunw/ecommerce-churn-analysis/blob/main/Screenshot%202025-07-20%20132000.png)  
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
