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

![Dashboard Overview](https://github.com/eatunw/sales-forecast-fmcg/blob/main/visual%20(6).png?raw=true)

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
   - ![This chart compares total sales (units_sold) against total inventory (stock_available) by brand, revealing critical issues in inventory management. (%)](https://github.com/eatunw/sales-forecast-fmcg/blob/main/Picture2.png?raw=true)
   This chart compares total sales (units_sold) against total inventory (stock_available) by brand, revealing critical issues in inventory management.
   - *Major Stock Imbalance for MiBrand3*: WBrand3 has an alarmingly high level of stock available relative to its actual sales. This indicates severe overstocking, which ties up capital, increases storage costs, and risks obsolescence or spoilage.
   - *Efficient Performers*: Brands like Redrand1, Redrand2, SrBrand1, and the YoBrand series show a much healthier ratio, with sales figures much closer to their stock levels. This suggests better demand forecasting and inventory turnover for these brands.
   - *MiBrand1 & MiBrand2 Concerns*: These brands also show a disparity where inventory significantly outpaces sales, though not as drastically as WBrand3. This warrants investigation into their sales strategies or product viability.

- **Recommendation**:

   - *Immediate Action on MiBrand3*: Conduct a deep-dive analysis into WBrand3. Implement aggressive sales promotions, discounts, or bundle deals to liquidate excess stock. Simultaneously, halt or drastically reduce new production/purchasing until inventory levels are corrected.
   - *Review Supply Chain Parameters*: For overstocked brands, reassess safety stock levels, reorder points, and lead times with suppliers to prevent future overstocking.
     
2. **Category-Wise Sales & Inventory**

   The following charts break down performance by product category, which is crucial for strategic planning.
   - ![image](https://github.com/eatunw/sales-forecast-fmcg/blob/main/Picture5.png?raw=true)
      - *Revenue Leadership*: Milk is the undisputed revenue leader (€382,439.76), contributing the largest share of total income. This is followed by Yogurt (€180,500.38) and Ready Meals (€169,309.49). This highlights which categories are the biggest cash cows for the business.
   - ![image](https://github.com/eatunw/sales-forecast-fmcg/blob/main/Picture3.png?raw=true)
      - *Volume vs. Value*: While Milk leads in revenue, the relationship between its units_sold and stock_available needs to be compared with the first chart to see which specific brands are driving this. The high revenue suggests Milk may have a higher average selling price or simply much higher volume.
      - *Niche Categories*: Juice and Snack Bar generate significantly lower revenue. This doesn't necessarily mean they are underperforming; they could be newer categories or have different strategic roles.
        
- **Recommendation**:

   - Protect & Invest in Core Categories: Allocate marketing and prime shelf space to Milk and Yogurt to protect their dominant market position and maximize their high revenue generation.
   - Strategic Review for Niche Categories: Analyze the profitability (not just revenue) of Juice and Snack Bars. Decide if they are worth further investment to grow or if they should be maintained as a complementary product range for customer convenience.
     
3. **Sales Trend & Seasonality**

   The time-series analyses reveal strong, predictable patterns in consumer demand.
   - ![image](https://github.com/eatunw/sales-forecast-fmcg/blob/main/vizual(1).png?raw=true)
      - *Clear Growing Trend*: The 3-month Moving Average (3M MA) clearly shows an upward trend in sales since early 2022, indicating healthy business growth. The trend is not perfectly smooth, showing the impact of seasonality.
   - ![image](https://github.com/eatunw/sales-forecast-fmcg/blob/main/visual%20(2).png?raw=true)
      - *Pronounced Monthly Seasonality*: Sales are highly seasonal. Peaks occur around Month 1 (January) and Month 8 (August). The high in January could be post-holiday replenishment or New Year's resolution buying (e.g., healthy snacks, yogurt). The August peak likely corresponds to summer holidays and increased consumption of refreshments.
   - ![image](https://github.com/eatunw/sales-forecast-fmcg/blob/main/visual%20(4).png?raw=true)
      - *Consistent Daily Demand*: Sales distribution across weekdays is remarkably consistent. There is no significant "weekend spike" or "Monday slump." This suggests stable, daily consumption habits typical of essential FMCG goods.

- **Recommendation**:

   - *Align Operations with Seasonality*: Plan marketing campaigns, promotions, and major stock deliveries in the months leading into the high-season periods (e.g., Q4 for January peak, Q2 for August peak).
   - *Forecast-Driven Procurement*: Use these seasonality indices to create more accurate demand forecasts. Ensure inventory levels are built up ahead of peak months to avoid stockouts and drawn down during slower months to avoid overstock.
   - *Staffing & Logistics*: The consistent daily pattern simplifies staffing and delivery scheduling, as demand is evenly spread throughout the week.
  
4. **Sales Forecast**

   The forecast predicts future sales, but the model's uncertainty is a critical factor.
   - ![image](https://github.com/eatunw/sales-forecast-fmcg/blob/main/visual%20(3).png?raw=true)
      - *Positive Short-Term Forecast*: The forecast for the next 3 months shows strong growth, increasing from ~80,000 to over ~100,000 units. This aligns with the positive historical trend.
      - *High Model Uncertainty*: The extremely large numbers on the x-axis (1.735e^18) are a technical error in the chart, but the wide confidence intervals (in the image below) that fan out dramatically in 2025 are the true takeaway. This indicates that the model's forecast becomes highly uncertain the further out it projects.
   - ![image](https://github.com/eatunw/sales-forecast-fmcg/blob/main/visual.png?raw=true)

- **Recommendation**:

   - *Trust the Short-Term and Question the Long-Term*: Base Q1 operational plans (procurement, staffing) on the strong 3-month forecast. However, do not make long-term strategic investments or commitments based on the highly uncertain forecast for late 2024 and 2025.
   - *Adopt a Rolling Forecast*: Instead of a static annual forecast, implement a rolling 3-6 month forecast that is updated monthly with actual sales data. This allows the business to be agile and adjust to changing market conditions reflected in the model's high uncertainty.
  

---

## Summary of Key Conclusions
- Inventory Crisis: The business has a critical overstocking issue, primarily with the MiBrand3 brand, which is draining profitability.
- Category Powerhouses: Milk and Yogurt are the primary revenue drivers and should be the focus of strategic protection and growth.
- Predictable Demand: Sales show strong and predictable seasonal peaks (Jan & Aug) and remarkably consistent daily patterns, enabling efficient operational planning.
- Growth with Uncertainty: The business is on a strong growth trajectory in the short term, but the forecasting model lacks confidence in long-term predictions, advising a cautious and agile approach to planning beyond the next quarter.

These insights provide a powerful foundation for data-driven decision-making across sales, marketing, supply chain, and finance functions within the company.

---

## Contact
  
- **Contact**: [EMAIL](atundeemmanuel7@gmail.com)

