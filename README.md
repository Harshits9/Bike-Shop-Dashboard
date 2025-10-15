# 🚴 Adventure Works Bike Sales Analysis Dashboard

A comprehensive Power BI analytics project analyzing bike sales performance, customer behavior, and product trends for Adventure Works company.

![Dashboard Preview]([link-to-your-dashboard-screenshot.png](https://github.com/Harshits9/Bike-Shop-Dashboard/blob/main/Exec%20Dashboard.png)

## 📊 Project Overview

This project transforms raw sales data into actionable business insights through interactive dashboards. It covers the complete data analytics lifecycle from ETL to final visualization, enabling stakeholders to make data-driven decisions about inventory, marketing, and sales strategies.

**Key Metrics:**
- Revenue: $24.9M
- Profit: $10.5M
- Total Orders: 25.2K
- Return Rate: 2.2%
- Unique Customers: 17.4K

## 🎯 Business Objectives

- Track sales performance across product categories, regions, and time periods
- Analyze customer demographics and purchasing patterns
- Monitor product performance and identify top-selling items
- Evaluate return rates and identify problematic product categories
- Compare actual performance against targets
- Calculate revenue per customer and customer lifetime value

## 🛠️ Technical Implementation

### 1. ETL (Extract, Transform, Load)

**Data Sources:**
- Sales transactions data
- Customer demographics
- Product catalog
- Geographic information
- Target metrics

**Transformation Steps:**
- Cleaned and standardized product names and categories
- Handled missing values and data inconsistencies
- Created date hierarchies for time-based analysis
- Merged multiple data sources using appropriate keys
- Validated data quality and integrity

### 2. Power Query (Data Preparation)

- **Data Cleansing:** Removed duplicates and null values
- **Column Transformations:** Created calculated columns for derived metrics
- **Data Type Conversions:** Ensured proper data types for calculations
- **Table Merging:** Joined customer, product, and sales tables
- **Parameter Setup:** Created dynamic filters and parameters
- **Custom Columns:** Added business-specific calculations (e.g., profit margins, customer segments)

### 3. Data Modeling

**Star Schema Implementation:**
- **Fact Table:** Sales transactions (Orders, Revenue, Returns, Profit)
- **Dimension Tables:**
  - DimCustomer (Customer demographics, income, occupation)
  - DimProduct (Product hierarchy: Category → Subcategory → Product)
  - DimDate (Calendar with year, quarter, month, day hierarchies)
  - DimGeography (Country, region information)
  - DimTarget (Monthly targets for comparison)

**Relationships:**
- Established one-to-many relationships between dimension and fact tables
- Created bidirectional filters where necessary
- Optimized cardinality for performance

### 4. DAX (Data Analysis Expressions)

**Key Measures Created:**

```dax
// Revenue Calculations
Total Revenue = SUM(Sales[Revenue])
Previous Month Revenue = CALCULATE([Total Revenue], DATEADD(DimDate[Date], -1, MONTH))
Revenue Growth % = DIVIDE([Total Revenue] - [Previous Month Revenue], [Previous Month Revenue], 0)

// Profit Metrics
Total Profit = SUM(Sales[Profit])
Profit Margin = DIVIDE([Total Profit], [Total Revenue], 0)
Adjusted Profit = [Total Profit] * (1 + 'Price Adjustment'[Value])

// Customer Metrics
Unique Customers = DISTINCTCOUNT(Sales[CustomerKey])
Revenue per Customer = DIVIDE([Total Revenue], [Unique Customers], 0)

// Order Metrics
Total Orders = COUNTROWS(Sales)
Monthly Orders = CALCULATE([Total Orders], DATESMTD(DimDate[Date]))
Orders vs Target = [Monthly Orders] - [Target Orders]

// Return Analysis
Total Returns = SUM(Sales[Returns])
Return Rate = DIVIDE([Total Returns], [Total Orders], 0)

// Time Intelligence
YTD Revenue = TOTALYTD([Total Revenue], DimDate[Date])
MTD Orders = TOTALMTD([Total Orders], DimDate[Date])
```

**Advanced DAX Techniques:**
- Time intelligence functions (DATEADD, TOTALYTD, DATESMTD)
- Context transition using CALCULATE
- Filter context manipulation
- Dynamic segmentation
- Statistical calculations for anomaly detection

### 5. Exploratory Data Analysis (EDA)

**Key Findings:**

- **Product Performance:**
  - Accessories lead with 17K orders
  - Bikes generate highest revenue per unit
  - Tires and Tubes most ordered subcategory
  - Shorts have highest return rate

- **Customer Insights:**
  - Average customer value: $1,431
  - Professionals generate most orders (7.8K)
  - High-income segment: 11.6K orders
  - Top customer: Mr. Maurice Shan ($12.4K revenue)

- **Geographic Distribution:**
  - Primary markets: United States, Australia, Canada
  - European presence: UK, France, Germany

- **Temporal Trends:**
  - 260% growth in orders (June 2021 - June 2022)
  - Consistent month-over-month growth
  - Seasonal patterns identified
  - Anomaly detected: July 1, 2021 (unexpectedly low orders)

### 6. Interactive Reports & Dashboards

**Dashboard Pages:**

1. **Executive Summary**
   - KPI cards for revenue, profit, orders, return rate
   - Revenue trending line chart
   - Orders by category breakdown
   - Top 10 products table
   - Geographic map visualization

2. **Product Analysis**
   - Product hierarchy drill-through
   - Category/subcategory performance
   - Price adjustment simulation
   - Return rate analysis by product type
   - Interactive filters for deep-dive analysis

3. **Customer Analytics**
   - Customer demographics (income, occupation)
   - Revenue per customer trends
   - Top 100 customers table
   - Customer growth over time
   - Segment-wise order distribution

4. **Performance vs Target**
   - Monthly orders vs target comparison
   - Revenue vs target variance
   - Profit vs target tracking
   - Adjusted profit scenarios
   - Trend analysis with targets

**Interactive Features:**
- Cross-filtering across all visuals
- Drill-down/drill-through capabilities
- Dynamic slicers (date, category, region)
- Tooltips with detailed information
- Bookmarks for different views
- Mobile-optimized layout

## 📈 Key Insights & Recommendations

1. **Product Strategy:** Focus on accessories marketing - high volume, low return rate
2. **Customer Targeting:** Prioritize professional and high-income segments
3. **Inventory Management:** Monitor shorts category for quality issues (high returns)
4. **Geographic Expansion:** Strengthen presence in emerging markets
5. **Pricing Optimization:** Use price adjustment feature to test scenarios

## 🔧 Tools & Technologies

- **Power BI Desktop:** Dashboard creation and data visualization
- **Power Query (M):** Data transformation and ETL
- **DAX:** Advanced calculations and measures
- **Excel/CSV:** Source data format
- **SQL:** (if applicable) Data extraction

## 📁 Project Structure

```
├── Data/
│   ├── raw/                  # Original data files
│   ├── processed/            # Cleaned data
│   └── data_dictionary.md    # Data schema documentation
├── Reports/
│   ├── AdventureWorks_Dashboard.pbix
│   └── screenshots/
├── Documentation/
│   ├── DAX_Measures.md
│   ├── Data_Model.png
│   └── Requirements.md
└── README.md
```


---

⭐ If you find this project helpful, please consider giving it a star!

**Last Updated:** October 2025
