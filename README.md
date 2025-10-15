# 🚴‍♂️ AdventureWorks Bike Sales Dashboard (Power BI)

This Power BI project provides an end-to-end analysis of the **AdventureWorks Bike Sales dataset**, covering key business metrics like revenue, profit, orders, and customer segmentation.  
The goal of this dashboard is to deliver clear, actionable insights for management and sales teams to make data-driven decisions.

---

## 🧩 Project Overview

The **AdventureWorks Bike Sales Dashboard** visualizes company-wide performance across different countries, product categories, and customer segments.  
It highlights trends, KPIs, and sales behavior to understand overall growth, identify high-performing products, and analyze return patterns.

---

## ⚙️ Tools & Technologies Used

- **Power BI Desktop** – for data modeling, DAX calculations, and visualization  
- **Power Query** – for ETL (Extract, Transform, Load) operations  
- **DAX (Data Analysis Expressions)** – for creating measures and KPIs  
- **Excel / CSV** – as the source dataset (AdventureWorks sample data)  

---

## 🔄 Workflow Stages

### 🧹 1. ETL (Extract, Transform, Load)
- Imported multiple datasets from AdventureWorks (Sales, Products, Geography, Customers).
- Cleaned and transformed data using **Power Query**:
  - Changed data types (Date, Currency, Text).
  - Removed duplicates and null values.
  - Merged tables using relationships (ProductKey, CustomerKey, etc.).
  - Created a proper date table for time intelligence.

---

### 📊 2. EDA (Exploratory Data Analysis)
- Analyzed overall sales distribution across categories and subcategories.
- Identified top-selling products and high-return items.
- Studied geographic performance by country and region.
- Explored customer segmentation by **income level** and **occupation**.

---

### 🧮 3. DAX Measures & KPIs
Custom DAX measures were created to support the dashboard visuals, such as:

```DAX
Total Revenue = SUM(Sales[Revenue])
Total Profit = SUM(Sales[Profit])
Total Orders = COUNT(Sales[OrderNumber])
Return Rate (%) = DIVIDE(SUM(Sales[Returns]), SUM(Sales[Orders]))
Revenue Target = CALCULATE([Total Revenue] * 1.05)
Monthly Growth % = ([Current Month Revenue] - [Previous Month Revenue]) / [Previous Month Revenue]
Revenue per Customer = DIVIDE([Total Revenue], DISTINCTCOUNT(Customers[CustomerKey]))

Dasboard Overview 

https://github.com/Harshits9/Bike-Shop-Dashboard/blob/main/Exec%20Dashboard.png

