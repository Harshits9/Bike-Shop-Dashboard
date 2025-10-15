# 🚴 Adventure Works Bike Sales Analysis Dashboard

A complete Power BI analytics project that digs into bike sales performance, customer behavior, and product trends for Adventure Works.

![Dashboard Preview](https://raw.githubusercontent.com/Harshits9/Bike-Shop-Dashboard/main/Exec%20Dashboard.png)

## 📊 What This Project Does

This project takes raw sales data and turns it into something actually useful. Built interactive dashboards that help make real business decisions about inventory, marketing, and sales strategies. Walked through the entire data pipeline from messy CSVs to polished visualizations.

**The Numbers:**
- Revenue: $24.9M
- Profit: $10.5M
- Total Orders: 25.2K
- Return Rate: 2.2%
- Unique Customers: 17.4K

## 🎯 What I Was Trying to Solve

- Track sales across different products, regions, and time periods
- Figure out who's buying what and why
- Find the best and worst performing products
- Keep an eye on return rates to spot quality issues
- Compare how we're doing against targets
- Calculate customer lifetime value

## 🛠️ How I Built This

### ETL Process

Started with data from multiple sources - sales transactions, customer info, product catalogs, and geographic data. The data was messy, so I spent time cleaning it up, standardizing product names, filling in gaps, and making sure everything connected properly.

### Power Query Magic

This is where the real data prep happened. Removed duplicates, fixed data types, created useful date columns for time analysis, and joined all the tables together. Also set up some parameters to make the dashboard dynamic so users can filter and explore on their own.

### Data Model

Built a star schema because it's fast and makes sense:
- Sales table sits in the middle with all the transactions
- Connected it to dimension tables for customers, products, dates, geography, and targets
- Made sure relationships were clean and optimized for performance

### DAX Measures

Wrote a bunch of custom calculations to make the dashboard actually useful:

**Revenue stuff:**
- Total revenue, previous month comparisons, growth percentages
- Year-to-date and month-to-date calculations

**Profit tracking:**
- Profit margins, adjusted profit scenarios
- What-if analysis for price changes

**Customer metrics:**
- How many unique customers we have
- Revenue per customer to understand value

**Order analytics:**
- Total orders, monthly trends
- Comparison against targets

**Return analysis:**
- Return rates by product and category
- Helped identify problem areas

Used time intelligence functions heavily and played around with filter contexts to get the calculations just right.

### Exploring the Data

Spent time really digging into patterns:

**Product insights:**
- Accessories are the volume driver with 17K orders
- Bikes bring in the most revenue per unit
- Tires and tubes fly off the shelves
- Shorts have a return problem we need to fix

**Customer patterns:**
- Average customer spends $1,431
- Professionals are our biggest customer group
- High-income folks place the most orders
- Mr. Maurice Shan is our MVP with $12.4K in revenue

**Geography:**
- Strong in US, Australia, and Canada
- Growing presence in Europe

**Time trends:**
- Huge 260% growth in orders over the year
- Steady month-over-month improvements
- Found a weird dip on July 1, 2021 that needs investigation

### Building the Dashboards

Created four main pages that tell the whole story:

**Executive Summary** - The big picture with KPIs, trending revenue, category breakdown, top products, and a map showing where orders come from.

**Product Analysis** - Drill down into specific products, see how categories perform, play with price adjustments, and spot return rate issues.

**Customer Analytics** - Who our customers are, what they're worth, top spenders, and how different segments behave.

**Performance Tracking** - How we're doing against targets for orders, revenue, and profit. Shows variance and trends over time.

Everything's connected, so clicking on one thing filters everything else. Set up drill-throughs so you can go deep on any metric. Made it work on mobile too.

## 📈 What I Learned

- Accessories are goldmines - high volume, low returns, good margins
- Focus marketing on professionals and high-income customers
- Something's wrong with shorts - returns are too high
- Geographic expansion opportunity in emerging markets
- Price sensitivity varies by product - the adjustment feature shows this

## 🔧 Tech Stack

- Power BI Desktop for everything visual
- Power Query (M language) for data transformation
- DAX for calculations and measures
- Started with Excel/CSV files

## 📁 How It's Organized

```
├── Data/
│   ├── raw/
│   ├── processed/
│   └── data_dictionary.md
├── Reports/
│   ├── AdventureWorks_Dashboard.pbix
│   └── screenshots/
├── Documentation/
│   ├── DAX_Measures.md
│   ├── Data_Model.png
│   └── Requirements.md
└── README.md
```

## 🚀 Want to Use This?

Clone it:
```bash
git clone https://github.com/Harshits9/Bike-Shop-Dashboard.git
```

You'll need Power BI Desktop installed. Open the .pbix file and you're good to go. Hit refresh if you want to update the data. Play around with the filters and slicers to explore different angles.

## 📊 More Screenshots

Check out the repository for additional dashboard views showing customer analytics, product performance details, and target comparisons.

## 👤 About Me

**Harshit**
- GitHub: [@Harshits9](https://github.com/Harshits9)

## 🙏 Thanks

Built using the Adventure Works sample dataset from Microsoft. Learned a ton from the Power BI community along the way.

---

If this helped you, drop a star! ⭐

**Last Updated:** October 2025
