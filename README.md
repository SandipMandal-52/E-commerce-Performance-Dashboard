#  Adventure Works — Power BI Business Intelligence Dashboard

> **A 4-page interactive Power BI dashboard tracking revenue, profit, orders, and returns for Adventure Works Bike Shop across 2020–2022 — with executive KPIs, customer segmentation, product drill-through, and geographic performance analysis.**

---

## ⚡ Key Numbers Upfront

| Metric | Value |
|--------|-------|
| Total Revenue | **₹24.9M** |
| Total Profit | **₹10.5M** |
| Total Orders | **25,200** |
| Return Rate | **2.17%** |
| Unique Customers | **17,400** |
| Revenue Per Customer | **₹1,430.6** |
| Date Range | **Jan 2020 – Jun 2022** |
| Top Customer | **Mr. Maurice Shan — ₹12,408** |
| Highest Volume Category | **Accessories — 17,000 units** |
| Highest Revenue Category | **Bikes — ₹23.6M** |

---

## 📌 Project Overview

Adventure Works is a global manufacturing company specializing in cycling products — bikes, accessories, clothing, and components. This Power BI dashboard was built to give the management team a single, consolidated view of business performance across KPIs, product categories, customer segments, and regions from 2020 to 2022.

The dashboard answers four core business questions:

- How is the business performing overall, and are we hitting monthly targets?
- Which products are driving revenue — and which are being returned at high rates?
- Who are our highest-value customers, and what is happening to revenue per customer over time?
- Which geographies generate the most orders?

---

## 🏗️ Dashboard Structure — 4 Pages + Tooltip

### Page 1 — Executive Dashboard
<img width="1326" height="743" alt="Exe" src="https://github.com/user-attachments/assets/d449857b-f629-431c-b41a-35fd99de45f0" />

**The top-level command center.**

KPI cards: Total Revenue (₹24.9M), Total Profit (₹10.5M), Total Orders (25.2K), Return Rate (2.2%)

- **Revenue Trending line chart** — Jan 2020 to Jun 2022 with trendline overlay showing overall growth trajectory and post-2021 plateau
- **Category orders bar chart** — Accessories (17K), Bikes (13.9K), Clothing (7K)
- **Top 10 Products table** — Orders, Revenue, % Return per product. Water Bottle 30oz leads volume (3,983 orders) but carries the highest return rate (8.15%). Sport-100 Helmets dominate the top spots by revenue.
- **Monthly KPI cards** — Monthly Revenue (₹18,26,987 vs target ₹17,68,433 → +3.31%), Monthly Orders (2,146 vs target 2,165 → -0.88%), Monthly Returns (167 vs prior 169 → -1.18%)
- **Most Ordered Product Type:** Tires and Tubes
- **Most Returned Product Type:** Shorts

### Page 2 — Map
<img width="1496" height="843" alt="Map" src="https://github.com/user-attachments/assets/7038b2bc-76b2-4dbe-a38b-182ece5c264c" />

**Geographic orders distribution.**

- Bubble map showing orders by country/continent
- USA leads globally: **8,700 orders**
- Australia second: **6,060 orders**
- UK leads Europe: **2,771 orders**
- Custom tooltip on hover shows: Total Profit, Total Revenue, Total Orders, Total Returns, Return Rate, and Weekly Orders area chart

### Page 3 — Customer Details
<img width="1234" height="688" alt="customer" src="https://github.com/user-attachments/assets/e25056bf-3fad-4710-b9a2-eda128bcd381" />

**Customer segmentation and individual value analysis.**

- KPI cards: 17,400 Unique Customers | ₹1,430.6 Revenue Per Customer
- **Dual-axis line chart** — Total Customers vs Revenue Per Customer over time (Jan 2020 – Jun 2022). Customer base grew steadily but Revenue Per Customer declined sharply from ₹3K+ (early 2020) to ~₹1K by mid-2021 — an inverse relationship signaling volume growth but value dilution.
- **Orders by Income Level donut** — Average income: 46.98% (12K orders) | Low: 41.57% (10K) | High: 11.45% (3K)
- **Orders by Occupation donut** — Professional: 43.68% (8K) | Management: 22.84% (4K) | Skilled Manual: 33.47% (6K)
- **Top 100 Customers table** — filterable by year (2020 / 2021 / 2022)
- **Top customer:** Mr. Maurice Shan — 6 orders, ₹12,408 revenue
- **Hidden insight noted:** From the Low Income + Skilled Manual segment, Mrs. Isabella Ward generated ₹8.1K revenue

### Page 4 — Product Details *(Drill-through page)*
<img width="1230" height="695" alt="Product" src="https://github.com/user-attachments/assets/8d63351d-3302-43df-8238-582569b79b90" />

**Per-product deep dive — accessed via drill-through from Executive Dashboard.**

- Selected product shown in header card (e.g., AWC Logo Cap)
- **Three gauge charts:** Monthly Orders vs Target | Monthly Revenue vs Target | Monthly Profit vs Target
- **Price Adjustment (%) parameter slider** — tests impact of ±% price change on adjusted profit in real time (Total Profit vs Adjusted Profit line overlay)
- **Product Metric Selection radio buttons** — dynamically switches the trend chart between Orders / Profit / Revenue / Return / Return %
- **Daily orders area chart** — granular order volume view across the selected date range

### Bonus — Category Tooltip
<img width="1058" height="665" alt="tooltip" src="https://github.com/user-attachments/assets/07dafd84-19a9-45ba-9799-0857d87e7274" />

**Custom hover tooltip triggered from the Map page.**

Displays on hover: Total Profit (₹1,04,57,715) | Total Revenue (₹2,49,14,587) | Total Orders (25,164) | Total Returns (1,809) | Return Rate (2.17%) | Weekly Orders area chart

---

## 🗃️ The Data

**Source:** Maven Analytics (Udemy course dataset) — provided as raw CSV files

| Table Type | Tables |
|-----------|--------|
| Fact Tables | Sales Data, Returns Data |
| Dimension Tables | Customer Lookup, Product Lookup, Product Subcategory Lookup, Product Category Lookup, Territory Lookup, Calendar Lookup |

**Data Model:** Star Schema (core tables) + Snowflake Schema extension for Product Category → Subcategory → Product hierarchy. One-to-many relationships on primary/foreign keys, single cross-filter direction, downward flow layout in model view.

---

## 🧹 Data Cleaning & Transformation (Power Query)

| Step | What Was Done |
|------|--------------|
| Header Promotion | First row promoted to column headers |
| Data Type Formatting | Corrected types for dates, decimals, integers |
| Calculated Columns | Added fields for deeper analysis |
| Null Value Replacement | Missing values addressed appropriately |
| Column Merging & Extraction | Combined and split columns as needed |
| Folder Data Import | Used Folder connector to append multiple related CSV files in one step |
| Data Trimming | Removed whitespace from text fields |
| Standardization | Normalized column names, date formats, currency |
| Data Profiling | Column quality, distribution, and profile checks on full dataset |
| Duplicate & Column Removal | Removed irrelevant columns and duplicate rows |

---

## 📊 Key Insights

### Revenue & Growth
- Total revenue of **₹24.9M** and profit of **₹10.5M** across 25,200 orders from 2020–2022
- Revenue grew significantly from 2020 to 2021, crossing ₹9M annually, before a slight decline in 2022 momentum
- **2020 COVID impact:** Q3 2020 revenue dropped from ₹1.9M (Q2) → ₹1.3M → ₹1.2M (Q4), despite a 15.92% increase in Q3 orders over Q2 — demand held but profitability compressed
- Recovery began Q1 2021 with consistent upward trajectory

### Product Performance
- **Bikes** generate the most revenue: ₹23.6M from 13,929 units (₹9.7M profit)
- **Accessories** lead in volume: 17,000 units but only ₹906,673 revenue — low ASP, high volume
- **Water Bottle 30oz** — highest orders (3,983) but also highest return rate (8.15%) — a quality or expectation mismatch signal
- **Shorts** are the most returned product type — candidate for quality review or description audit

### Customer Behavior
- 17,400 unique customers with average revenue of ₹1,430.6 per customer
- Revenue per customer peaked at **₹3,476** in Feb 2020 (32 customers) — as customer base scaled, per-customer value declined
- Lowest point: ₹544 per customer in Aug 2021 (347 customers) — volume vs value trade-off
- **Professional occupation** drives most orders (43.68%) followed by Skilled Manual (33.47%)
- **Average income level** customers contribute the most orders (46.98% — 12K units)

### Geographic Performance
- USA: **8,700 orders** — largest single market
- Australia: **6,060 orders** — strong APAC presence
- UK: **2,771 orders** — leads European markets

---

## 🛠️ Technical Implementation

### DAX Measures Built

```dax
-- Total Revenue
Total Revenue = SUMX(Sales_Data, Sales_Data[OrderQuantity] * RELATED(Product_Lookup[ProductPrice]))

-- Total Profit
Total Profit = [Total Revenue] - [Total Cost]

-- Return Rate
Return Rate = DIVIDE([Total Returns], [Total Orders], 0)

-- Revenue Per Customer
Revenue Per Customer = DIVIDE([Total Revenue], [Total Customers], 0)

-- Previous Month Revenue (for MoM comparison)
Prev Month Revenue = CALCULATE([Total Revenue], DATEADD('Calendar_Lookup'[Date], -1, MONTH))
```

### Data Model Structure

```
Calendar_Lookup ──────────────────────────────────┐
Territory_Lookup ─────────────────────────────────┤
Customer_Lookup ──────────────────────────────────┤──► fact_Sales
Product_Category_Lookup                            │
        └── Product_Subcategory_Lookup             │
                └── Product_Lookup ────────────────┘
                                        │
                                        └──► fact_Returns
```

---

## 📁 Project Structure

```
adventure-works-powerbi/
│
├── Adventure_Works_Dashboard.pbix     # Main Power BI file
│
├── datasets/
│   ├── Sales_Data_2020.csv
│   ├── Sales_Data_2021.csv
│   ├── Sales_Data_2022.csv
│   ├── Returns_Data.csv
│   ├── Customer_Lookup.csv
│   ├── Product_Lookup.csv
│   ├── Product_Subcategory_Lookup.csv
│   ├── Product_Category_Lookup.csv
│   ├── Territory_Lookup.csv
│   └── Calendar_Lookup.csv
│
├── assets/
│   ├── Executives.png                 # Executive Dashboard screenshot
│   ├── Customer_detail.png            # Customer Details screenshot
│   ├── Product_details.png            # Product Details screenshot
│   └── Map.png                        # Geographic Map screenshot
│
└── README.md
```

---

## ▶️ How to Use

**1. Clone the repository**
```bash
git clone https://github.com/SandipMandal-52/adventure-works-powerbi.git
```

**2. Open the dashboard**
```
Open Adventure_Works_Dashboard.pbix in Power BI Desktop
If prompted, update data source paths to point to your local /datasets/ folder
Click Refresh
```

**3. Navigate the dashboard**
```
Use the left sidebar icons to move between pages:
  📊 Exec Dashboard  — Overall KPIs and revenue trending
  🌍 Map             — Geographic orders by country
  👥 Customer Details — Customer segmentation and top customers
  📦 Product Details  — Drill-through from product names on Exec Dashboard

Right-click any product name on the Executive Dashboard → Drill Through → Product Details
Hover over map bubbles to see the Category Tooltip with weekly orders chart
Use Price Adjustment slider on Product Details to simulate pricing scenarios
Use Product Metric Selection to toggle trend chart between Orders / Revenue / Profit / Returns
```

---

## 🔮 Next Steps

- **Forecasting layer** — Use Power BI's built-in forecasting on the Revenue Trending chart to project 2023 revenue
- **Return Rate Root Cause Analysis** — Deeper drill-down by product + region to identify if Water Bottle returns are geography-specific
- **Customer Lifetime Value (CLV) metric** — Build a DAX measure tracking cumulative revenue per customer over their full purchase history
- **Revenue per Customer Recovery analysis** — Cohort view to understand whether the post-2021 decline is a new-customer dilution effect or existing customer spend reduction

---

## 🛠️ Tools & Environment

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Power Query](https://img.shields.io/badge/Power_Query-217346?style=for-the-badge&logo=microsoft&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)

| Tool | Role |
|------|------|
| Power BI Desktop | Data cleaning, modeling, DAX, visualization, storytelling |
| Power Query (M) | ETL — extraction, transformation, and load pipeline |
| DAX | KPI measures, time intelligence, calculated columns |
| CSV files | Source data (10 tables — facts + dimensions) |

---

## 📝 About This Project

This is my first Power BI portfolio project, completed as part of the **Microsoft Power BI Desktop for Business Intelligence** course by Maven Analytics on Udemy. The dataset, business context, and course structure were provided by Maven Analytics. The data modeling decisions, DAX measure implementation, insight analysis, and dashboard design were built independently through the course.

---

## 👤 Author

**Sandip Mandal** — EDP Analyst | Aspiring Data Analyst
📍 Nagpur, Maharashtra, India
🔗 [LinkedIn](https://linkedin.com/in/sandipmandal52) | [GitHub](https://github.com/SandipMandal-52) | 📧 sandipmandalcv@gmail.com

---

*Built to understand the full Power BI stack — from raw CSV to executive-ready dashboard.*
