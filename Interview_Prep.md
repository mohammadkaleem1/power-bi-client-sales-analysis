# Supply Chain Analytics Dashboard - Interview Preparation

Use these 20 questions and answers to prepare for data analyst or BI interviews where you present this portfolio project.

**1. Why did you choose this project?**
"I chose this project because supply chain analytics is highly relevant to real-world business operations. I wanted to demonstrate my ability to take a flat dataset and transform it into a robust, multi-dimensional analytical tool that answers actual business questions regarding supplier reliability, logistics, and inventory risk."

**2. What was the business problem?**
"The organization had access to broad supply chain data but it was stored in a flat, single-table format. This made it difficult to analyze supplier performance against defect rates, or track logistics efficiency. The problem was turning raw operational data into actionable executive insights."

**3. What was your role?**
"I acted as the lead Power BI Developer and Data Analyst. I was responsible for end-to-end development: extracting the data, structuring the data model in Power Query, writing the DAX measures, and designing the final dashboard UX/UI."

**4. How did you clean the data?**
"I used Power Query to rename columns into professional, business-friendly terms. I handled missing values by replacing text nulls with 'Unknown' and numeric nulls with '0' where logically appropriate. Finally, I staged the main table to be split into dimension and fact tables."

**5. Why did you use Power Query?**
"Power Query is essential for creating a repeatable ETL process. By cleaning the data and creating the star schema in Power Query, I ensured that any future data refreshes would automatically inherit the structural changes without manual intervention."

**6. How did you design the data model?**
"I transformed the single-table model into a Star Schema. I created dimension tables for Product, Supplier, Customer, and Logistics by referencing the staging table and removing duplicates to establish primary keys. Then I connected these via 1-to-Many relationships to the central Fact table."

**7. Why use a star schema?**
"A star schema is the best practice for Power BI. It optimizes the underlying VertiPaq engine for performance, makes the DAX code simpler and more efficient, and ensures that cross-filtering across different report pages works accurately."

**8. What DAX measures did you create?**
"I created a dedicated `_Measures` table and wrote explicit DAX for core KPIs. This included Sales (`Total Revenue`, `Total Units Sold`), Supplier (`Average Lead Time`, `Average Defect Rate`), Logistics (`Average Shipping Cost`), and Inventory (`Stock-to-Demand Ratio`)."

**9. What is the difference between a calculated column and a measure?**
"A calculated column is computed row-by-row during data load and consumes RAM in the data model. A measure is calculated on-the-fly based on the filter context of the visual. I prioritized measures for aggregations (like Total Revenue) to keep the model fast and dynamic."

**10. How did you calculate profit margin?**
"The dataset did not explicitly provide Cost of Goods Sold or Net Profit. To maintain data integrity, I did not fabricate a profit margin. Instead, I focused on `Revenue Contribution %` and `Manufacturing Cost` to analyze financial impact based on actual fields."

**11. How did you handle missing values?**
"During the Power Query phase, I identified nulls. For dimensions like Customer Demographics, I replaced nulls with 'Unknown' to ensure those records weren't dropped. For numeric fields, I evaluated if a '0' was mathematically appropriate (e.g., 0 defects)."

**12. How did you validate the dashboard?**
"I validated the dashboard by cross-referencing the new explicit DAX measures (like Total Revenue) against the original implicit aggregations in the raw table to ensure the totals matched. I also tested the cross-filtering of the Star Schema to ensure slicers properly filtered the Fact table."

**13. How did you improve performance?**
"First, I moved away from a wide, flat table to a Star Schema. Second, I replaced implicit aggregations with explicit DAX measures. Third, I reduced visual clutter by consolidating 6 heavy pages into 5 focused pages, reducing the number of queries fired per page load."

**14. Why did you select particular visualizations?**
"I focused on business readability. I used KPI cards for top-level metrics so executives can read them instantly. I used bar charts for categorical comparisons (like Defect Rate by Supplier) and scatter plots to show relationships (like Demand vs. Stock Level)."

**15. How did you create slicers?**
"I implemented global slicers for `Product Type`, `Supplier`, and `Shipping Carrier`. I used dropdowns to save page space and synced them across pages so the user maintains their filter context as they navigate through the report."

**16. How did you implement drill-through?**
"If needed, a user could right-click a specific SKU on the Sales page and drill through to an Inventory Details page to see the exact manufacturing lead times and stock levels for that specific product."

**17. What business insights did you identify?**
"By analyzing the `Stock-to-Demand Ratio`, I could identify specific SKUs that had high demand but low stock, highlighting a potential stockout risk. I also identified which suppliers had the highest defect rates relative to their production volume."

**18. What challenges did you face?**
"The main challenge was the lack of a proper Date dimension in the source data. Because there were no transactional dates, I couldn't use Time Intelligence functions like Year-over-Year growth. I chose to document this limitation rather than fabricate fake dates."

**19. What would you improve next?**
"If we get access to historical timestamp data, I would implement a `DimDate` table and add Time Intelligence DAX. I would also love to pull in actual Cost of Goods Sold (COGS) to build out a true Profitability analysis page."

**20. Explain the project end-to-end.**
"I started with a flat supply chain dataset. I audited the data and used Power Query to clean columns and build a Star Schema (Products, Suppliers, Logistics, Customers, and Fact). I built an explicit DAX measure layer for all KPIs. Finally, I designed a 5-page interactive dashboard focusing on Executive Overview, Sales, Suppliers, Logistics, and Inventory Risk, resulting in a highly professional, performant BI tool."
