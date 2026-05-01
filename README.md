# Sales Analytics Power BI Dashboard
<table>
  <tr>
    <td align="center"><b>Overview Page</b></td>
    <td align="center"><b>Customer Analysis Page</b></td>
    <td align="center"><b>Product Analysis Page</b></td>
  </tr>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/df1d09e2-1e08-48bb-89f3-7903370ae223" width="400"/></td>
    <td><img src="https://github.com/user-attachments/assets/9a57b90e-2a5f-4443-a0ee-03bcf9c2fd53" width="400"/></td>
    <td><img src="https://github.com/user-attachments/assets/b791a9f4-fbd6-4cfc-b06d-068ed548d247" width="400"/></td>
  </tr>
</table>

## Project Overview

This project is an interactive **Power BI Sales Analytics Dashboard** developed as a continuation of my previous **SQL Data Warehouse Project**. The dashboard transforms cleaned and structured business data into actionable insights for sales, customer, and product performance analysis.

The dataset used in this dashboard was prepared through a complete SQL-based ETL and data warehousing process, where raw transactional data was transformed into reporting-ready Gold Layer tables.

### SQL Project Foundation

This dashboard is built directly on top of the Gold Layer outputs from my SQL Data Warehouse project:

**SQL Data Warehouse Repository:**
(https://github.com/sehammanqari/sql-data-warehouse-project)

---

## Project Objective

The main objective of this project is to provide business users, managers, and decision-makers with an end-to-end analytical solution for:

* Monitoring overall sales performance
* Understanding customer behavior and segmentation
* Evaluating product profitability and performance
* Identifying top-performing products and customers
* Supporting strategic business decisions through interactive business intelligence

---

## Tools & Technologies Used

### Data Engineering & Preparation:

* SQL Server
* Data Warehousing (Bronze / Silver / Gold architecture)
* ETL processes
* Data Cleaning & Transformation

### Business Intelligence & Visualization:

* Power BI Desktop
* Power Query
* DAX (Data Analysis Expressions)
* Power BI Service
* Figma (dashboard design planning)

### Documentation & Portfolio:

* GitHub

---

## Dataset Source

The dashboard uses the following Gold Layer reporting tables generated from the SQL Data Warehouse project:

### Tables Used:

* `gold_fact_sales`
* `gold_report_customers`
* `gold_report_products`

### Table Purposes:

#### `gold_fact_sales`

Contains transactional sales data including:

* Sales amount
* Quantity
* Orders
* Dates
* Customer keys
* Product keys

#### `gold_report_customers`

Contains customer-level reporting metrics including:

* Customer demographics
* Customer segmentation
* Average monthly spend
* Average order value
* Customer recency
* Lifespan metrics

#### `gold_report_products`

Contains product-level reporting metrics including:

* Product category
* Subcategory
* Product segment
* Product sales
* Product cost
* Profitability metrics

## Note: The dataset used in this project is a sample dataset designed for learning, analytics practice, and portfolio development.
---

## Data Model

This dashboard follows a **Star Schema** structure:

### Fact Table:

* `gold_fact_sales`

### Dimension / Reporting Tables:

* `gold_report_customers`
* `gold_report_products`

### Benefits:

* Optimized analytical performance
* Simplified filtering and slicing
* Better Power BI scalability
* Strong support for DAX calculations

---

## Dashboard Pages

# 1. Overview Page
<img width="1447" height="811" alt="image" src="https://github.com/user-attachments/assets/df1d09e2-1e08-48bb-89f3-7903370ae223" />

### Purpose:

Provides an executive summary of overall business performance.

### KPIs:

* Total Sales
* Total Orders
* Total Customers
* Total Quantity Sold

### Visualizations:

* Sales Trend Over Time
* Revenue by Customer Segment
* Revenue by Product Category
* Top 5 Products Table

### Business Questions Answered:

* How is the business performing overall?
* Which customer groups generate the most revenue?
* Which categories dominate sales?
* What are the top-selling products?

---

# 2. Customer Analysis Page
<img width="1445" height="817" alt="image" src="https://github.com/user-attachments/assets/9a57b90e-2a5f-4443-a0ee-03bcf9c2fd53" />

### Purpose:

Analyzes customer demographics, spending behavior, segmentation, and retention.

### KPIs:

* Total Customers
* Average Customer Age
* Average Monthly Spend
* Average Order Value

### Visualizations:

* Customer Segment Performance
* Customer Distribution by Segment
* Customer Recency Analysis
* Top 5 Customers Table

### Business Questions Answered:

* Which customer groups are most valuable?
* How do customers behave?
* What is the retention health of customers?
* Who are the top customers?

---

# 3. Product Analysis Page
<img width="1445" height="817" alt="image" src="https://github.com/user-attachments/assets/b791a9f4-fbd6-4cfc-b06d-068ed548d247" />


### Purpose:

Provides deep product profitability and performance analysis.

### KPIs:

* Total Sales
* Profit
* Profit Margin %
* Average Order Revenue

### Visualizations:

* Product Performance Breakdown (Decomposition Tree)
* Product Segment Performance
* Product Detail Matrix

### Business Questions Answered:

* Which products generate the most sales and profit?
* Which product categories dominate?
* How are products segmented by performance?
* Which products should be prioritized?

---

## Key DAX Measures

### Profit:

```DAX
Profit = [Total Sales] - [Total Cost]
```

### Profit Margin %:

```DAX
Profit Margin % = DIVIDE([Profit], [Total Sales])
```

### Average Order Value:

```DAX
Average Order Value = DIVIDE([Total Sales], [Total Orders])
```

---

## Product Segmentation Logic

Products were segmented in SQL using the following logic:

```SQL
CASE
    WHEN total_sales > 50000 THEN 'High-Performer'
    WHEN total_sales >= 10000 THEN 'Mid-Range'
    ELSE 'Low-Performer'
END AS product_segment
```

### Segment Definitions:

* **High-Performer:** Strongest revenue-generating products
* **Mid-Range:** Moderate contributors
* **Low-Performer:** Minimal contributors

---

## Key Business Insights

### Overview:

* Bikes dominate total sales revenue
* A small number of products generate the majority of revenue
* Sales peaked significantly in 2013

### Customer Analysis:

* New customers generate the highest sales
* VIP customers maintain strong purchase quality
* Customer behavior supports targeted retention strategies

### Product Analysis:

* High-performing products generate the majority of profit
* Product profitability is highly concentrated
* Certain categories and subcategories significantly outperform others

---

## Project Workflow

### Step 1: SQL Data Warehouse Development

* Raw data ingestion
* Data cleaning
* ETL pipelines
* Bronze / Silver / Gold architecture

### Step 2: Gold Layer Reporting Tables

* Customer reporting table
* Product reporting table
* Sales fact table

### Step 3: Power BI Development

* Data import
* Data modeling
* DAX calculations
* Dashboard design in Figma
* Dashboard implementation

### Step 4: Publishing & Documentation

* Power BI Service publishing
* GitHub repository creation
* Portfolio presentation

---

## Repository Structure

```text
sales-analytics-power-bi-dashboard/
│
├── README.md
│
├── dataset/
│   ├── gold.fact_sales.csv
│   ├── gold.report_customer.csv
│   └── gold.report_product.csv
│
├── design/
│   │
│   ├── button/
│   │   ├── Customer-default.png
│   │   ├── Customer-hover.png
│   │   ├── Customer-pressed.png
│   │   ├── Overview-default.png
│   │   ├── Overview-hover.png
│   │   ├── Overview-pressed.png
│   │   ├── Product-default.png
│   │   ├── Product-hover.png
│   │   └── Product-pressed.png
│   │
│   └── layout/
│       ├── Overview page.png
│       ├── Customer page.png
│       └── Product page.png
│
└── images/
    ├── Sales_Overview_page.JPG.png
    ├── Customer_Analysis_page.jpg.png
    └── Product_Analysis_page.jpg.png

```

---

## Future Improvements

* Drill-through pages for deeper product/customer analysis
* Dynamic titles
* Custom tooltips
* Mobile dashboard optimization
* Forecasting models
* Expanded customer lifetime value analysis
* Additional profitability forecasting

---

## Conclusion

This project demonstrates a full end-to-end Business Intelligence workflow, beginning with SQL data warehousing and ending with an interactive Power BI dashboard.

It showcases practical skills in:

* Data Analytics
* Data Engineering
* Data Modeling
* Business Intelligence
* Dashboard Design
* Data Visualization
* Strategic Analytics

This dashboard serves as both a portfolio project and a real-world business intelligence solution for analyzing sales, customers, and product performance.

---

## Author

**Seham Manqari**

Data Analytics Portfolio Project
