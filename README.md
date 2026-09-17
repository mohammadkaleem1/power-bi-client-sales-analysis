# Supply Chain Performance Analytics Dashboard

An interactive Power BI dashboard designed to analyze supply chain performance across products, suppliers, logistics, customers, and inventory.

## 📊 Project Overview
This project transforms a flat operational supply chain dataset into a multi-dimensional Power BI analytical dashboard. The dashboard provides end-to-end visibility into product performance, supplier reliability, logistics efficiency, and inventory risk. 

It is designed for supply chain managers, logistics coordinators, and executive stakeholders to quickly identify bottlenecks, optimize shipping costs, and prevent inventory stockouts through data-driven insights.

## 🎯 Business Problem
The organization needed a consolidated view of their supply chain operations to monitor supplier performance and evaluate logistics efficiency. Previously, the data was siloed in a flat file, making cross-functional analysis and real-time operational trend monitoring difficult.

*(Note: This project is based on a public/portfolio dataset structured to simulate real-world supply chain challenges.)*

## 🎯 Objectives
- Analyze revenue and product performance
- Compare supplier performance
- Evaluate shipping and logistics metrics
- Analyze customer segments
- Monitor inventory levels and demand
- Identify operational trends and potential risks

## 🛠️ Tools & Technologies
- Power BI
- Power Query
- DAX
- Data Modeling
- Data Visualization
- Business Intelligence
- Data Analysis

## 📁 Dataset
The original dataset consists of a broad supply chain table (`supply_chain_table`) containing:
- **Products**: SKUs, product types, and pricing.
- **Suppliers**: Supplier names, locations, lead times, defect rates, and manufacturing costs.
- **Logistics**: Shipping carriers, transportation modes, routes, shipping times, and costs.
- **Inventory**: Stock levels, demand (units sold), and inspection results.

## 🧹 Data Cleaning & Transformation
Power Query was utilized to prepare the data for modeling:
- Renamed columns for business readability (e.g., `Revenue_generated` to `Revenue`).
- Handled missing and null values, standardizing null text to "Unknown" and null numerics to `0`.
- Prepared the staging table to branch into a star schema.

## 🧩 Data Model
The project successfully transitions the flat file into a Star Schema to optimize filtering and analytical performance.
- **Fact Table**: `FactSupplyChain`
- **Dimension Tables**: `DimProduct`, `DimSupplier`, `DimLogistics`, `DimCustomer`
- **Relationships**: Active 1-to-Many (*:1) single-direction relationships from Dimensions to the Fact table.

## 📐 DAX Measures
A dedicated `_Measures` table was created to replace implicit aggregations with explicit calculations. Key measures include:

### Total Revenue
Calculates total revenue from the available revenue field.
### Total Units Sold
Calculates the total product volume sold across all transactions.
### Average Lead Time
Calculates average supplier/operational lead time.
### Average Defect Rate
Calculates the average defect rate across suppliers.
### Average Shipping Cost
Calculates the average logistical cost incurred per shipment.
### Stock-to-Demand Ratio
Calculates total stock divided by total demand to identify inventory risks.

## 📊 Dashboard Pages
### 1. Executive Overview
High-level KPIs and top-down view of revenue, supplier defect rates, and shipping costs. 
### 2. Sales & Product Performance
Analyzes product volume and revenue contribution.
### 3. Supplier & Manufacturing Performance
Evaluates supplier reliability through production volumes, average defect rates, and manufacturing lead times.
### 4. Logistics & Shipping
Assesses carrier performance, transportation modes, and average shipping costs vs. times.
### 5. Inventory & Operations
Highlights inventory risk by comparing total stock against demand, calculating a stock-to-demand ratio to flag potential overstock or stockout scenarios.

## 🖼️ DASHBOARD PREVIEW
*(You will need to manually export the screenshots from Power BI Desktop to populate this section. Please export the 5 pages as PNG files and save them in an `images/` folder inside this repository using the exact filenames listed below.)*

- `images/executive-overview.png`
- `images/sales-product-analysis.png`
- `images/supplier-performance.png`
- `images/logistics-shipping.png`
- `images/inventory-analysis.png`

## 💡 KEY BUSINESS QUESTIONS
- Which product categories generate the highest revenue?
- Which suppliers have higher defect rates?
- Which carriers have higher shipping times?
- Which transportation modes have higher shipping costs?
- Which products have high demand relative to stock?

## 🔎 KEY INSIGHTS
- Certain product categories consistently drive the highest revenue despite fluctuating prices.
- Some suppliers demonstrate significantly higher defect rates relative to their total production volume, requiring immediate operational review.
- Specific shipping carriers offer better cost-efficiency for large orders compared to expedited routes.
- The Stock-to-Demand ratio revealed specific SKUs at immediate risk of stockout based on current inventory levels against historical units sold.

## 🏗️ PROJECT WORKFLOW
Raw Data 
↓ 
Data Cleaning & Transformation 
↓ 
Data Modeling 
↓ 
DAX Measures 
↓ 
Interactive Visualizations 
↓ 
Business Analysis 
↓ 
Insights

## 📌 SKILLS DEMONSTRATED
- Power BI
- DAX
- Power Query
- Data Cleaning
- Data Modeling
- Data Visualization
- KPI Development
- Business Intelligence
- Business Analysis
- Dashboard Design

## 🚀 HOW TO USE
1. Download the `Client_Project.pbix` file.
2. Open using Power BI Desktop.
3. Navigate through dashboard pages using the bottom tabs.
4. Use the global slicers to filter data dynamically.

## 📂 PROJECT STRUCTURE
```
power-bi-client-sales-analysis/
│
├── Client_Project.pbix
├── README.md
├── Interview_Prep.md
├── Resume_Bullets.md
└── images/
    ├── executive-overview.png
    ├── sales-product-analysis.png
    ├── supplier-performance.png
    ├── logistics-shipping.png
    └── inventory-analysis.png
```

## 👨💻 AUTHOR
**Mohammad Kaleem**  
Data Analyst | Power BI | SQL | Excel  
GitHub: [https://github.com/mohammadkaleem1](https://github.com/mohammadkaleem1)
