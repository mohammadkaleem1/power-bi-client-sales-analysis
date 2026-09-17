# Supply Chain Performance Analytics Dashboard

## Project Overview
This project transforms a flat, single-table supply chain dataset into a professional, multi-dimensional Power BI analytical dashboard. It provides end-to-end visibility into product performance, supplier reliability, logistics efficiency, and inventory risk. 

## Business Problem
The organization needed a consolidated view of their supply chain operations to identify bottlenecks, track supplier performance, optimize shipping costs, and prevent inventory stockouts. Previously, the data was siloed in a flat file, making cross-functional analysis and time-series reporting difficult.

## Objectives
- **Data Architecture**: Upgrade the flat file structure into a robust Star Schema (Fact and Dimension tables) to improve performance and enable scalable analysis.
- **Analytics**: Replace implicit aggregations with reusable explicit DAX measures.
- **Business Intelligence**: Design a 5-page interactive dashboard answering key operational questions for executive stakeholders.

## Dataset
The dataset contains operational supply chain data including:
- **Products**: SKUs, product types, and pricing.
- **Suppliers**: Supplier names, locations, lead times, defect rates, and manufacturing costs.
- **Logistics**: Shipping carriers, transportation modes, routes, shipping times, and costs.
- **Inventory**: Stock levels, demand (units sold), and inspection results.
- *Note: A standard Date dimension was not included as the source dataset lacked explicit transactional dates.*

## Tools & Technologies
- **Power BI Desktop**: Data visualization, modeling, and reporting.
- **Power Query (M)**: Data extraction, transformation, and cleansing.
- **DAX (Data Analysis Expressions)**: KPI development and business logic.
- **Data Modeling**: Star schema design.

## Data Cleaning
Power Query was utilized to structure the `Staging_SupplyChain` table:
- Renamed columns for business readability (e.g., `Revenue_generated` to `Revenue`).
- Handled missing and null values, standardizing null text to "Unknown" and null numerics to `0`.
- Prepared the staging table to be branched into dimension tables.

## Data Model
Designed a Star Schema to optimize filtering and analytical performance:
- **Fact Table**: `FactSupplyChain` (Revenue, Units Sold, Costs, Lead Times, Stock Levels).
- **Dimension Tables**: `DimProduct` (SKU), `DimSupplier` (Supplier Name), `DimLogistics` (LogisticsKey), `DimCustomer` (Customer Demographics).
- **Relationships**: Configured active 1-to-Many (*:1) single-direction relationships between dimensions and the fact table.

## DAX Measures
Developed a comprehensive `_Measures` table. Key calculations include:
- **Sales**: `Total Revenue`, `Total Units Sold`, `Revenue Contribution %`
- **Suppliers**: `Average Lead Time`, `Average Defect Rate`, `Total Manufacturing Cost`
- **Logistics**: `Average Shipping Time`, `Average Shipping Cost`, `Shipping Cost per Unit`
- **Inventory**: `Total Stock`, `Stock-to-Demand Ratio`, `Potential Stockout Risk`

## Dashboard Pages
### 1. Executive Overview
High-level KPIs and top-down view of revenue, supplier defect rates, and shipping costs. Answers: *"What is happening in this supply chain?"*
### 2. Sales & Product Performance
Analyzes product profitability, volume, and customer demographic contribution. Identifies top-performing SKUs.
### 3. Supplier & Manufacturing Performance
Evaluates supplier reliability through production volumes, average defect rates, and manufacturing lead times.
### 4. Logistics & Shipping
Assesses carrier performance, transportation modes, and average shipping costs vs. times.
### 5. Inventory & Operations
Highlights inventory risk by comparing total stock against total units sold, calculating a stock-to-demand ratio to flag potential overstock or stockout scenarios.

## Key Business Questions Answered
- Which product categories contribute the highest revenue margin?
- Which suppliers have the highest defect rates and longest lead times?
- Which shipping carriers offer the best balance of time and cost?
- Which products are at high risk of stockouts based on current demand?

## Skills Demonstrated
- Data Cleansing & Transformation (Power Query)
- Relational Data Modeling (Star Schema)
- Advanced DAX Calculation
- Interactive Dashboard UI/UX Design
- Supply Chain Domain Knowledge

## Dashboard Screenshots
*(Placeholder for images - export from Power BI and save to an `images/` folder)*
- `images/executive-overview.png`
- `images/sales-product-analysis.png`
- `images/supplier-performance.png`
- `images/logistics-shipping.png`
- `images/inventory-analysis.png`

## How to Use
1. Download the `.pbix` file.
2. Open in Power BI Desktop.
3. Use the global slicers on the left/top to filter by Product Type, Supplier, or Shipping Carrier.
4. Navigate through the pages using the bottom page tabs or established navigation buttons.

## Author
[Your Name] - Data Analyst | Power BI Developer
[Your LinkedIn URL] | [Your GitHub URL]
