# Amazon Sales Performance Analysis

An Excel project that turns 250 order-level Amazon sales records into an interactive dashboard with KPIs, charts, slicers, insights and recommendations.

**Raw Data → Data Checks → Calculated Fields → PivotTables → Dashboard → Insights & Recommendations**

---

## Project Overview

This project analyzes order-level sales data from an Amazon seller using Microsoft Excel. The orders span **2 February 2025 to 2 April 2025** (about two months). The analysis covers product performance, category performance, customer locations, payment methods, order status, customer spending, and monthly sales.

>

## Business Problem

An Amazon seller wants to understand how its orders are performing and where attention is needed. The analysis answers:

- Which products generate the highest total sales?
- Which categories contribute the most to total sales?
- Which customer locations show strong or weak performance?
- Which payment methods are used most often?
- What share of orders are completed/delivered, pending, or cancelled?
- Which customers contribute the highest total sales?
- How does sales performance change by month?

---

## Project Objectives

1. Load and understand the Amazon sales dataset.
2. Check the data quality and standardize the order-level data.
3. Create calculated fields for analysis.
4. Analyze sales using Excel PivotTables.
5. Build an interactive dashboard with charts, KPIs and slicers.
6. Identify business insights from the dashboard.
7. Present recommendations based on the analysis.

---

## Dataset Overview

The workbook contains **250 order records**, covering **10 customers** in **10 locations**.

| Column | Description |
|---|---|
| Order ID | Unique identifier for each order |
| Date | Date on which the order was placed |
| Product | Product purchased |
| Category | Product category |
| Price | Price per unit |
| Quantity | Number of units ordered |
| Total Sales | Price × Quantity |
| Customer Name | Name of the customer |
| Customer Location | Customer city |
| Payment Method | Payment method used (PayPal, Credit Card, Debit Card, Gift Card, Amazon Pay) |
| Status | Original order status (Completed, Pending, Cancelled) |

**Categories (5):** Electronics, Home Appliances, Footwear, Clothing, Books

**Products (10):** Refrigerator, Laptop, Smartphone, Washing Machine, Smartwatch, Headphones, Running Shoes, Jeans, T-Shirt, Book

**Locations (10):** Miami, Denver, Houston, Dallas, Seattle, Boston, Chicago, New York, Los Angeles, San Francisco

---

## Tools and Technologies

- Microsoft Excel (Tables, formulas, PivotTables, PivotCharts, Slicers)
- Data checking and preprocessing
- Dashboard design
- GitHub for documentation and version control

---

## Workbook Structure

The workbook `Amazon_Sales_Performance_Analysis.xlsx` contains four sheets:

1. **Raw Data**: the original order-level dataset.
2. **Cleaned Data**: the dataset plus two calculated fields:
   - **Month**: derived from the order date (Feb, Mar, Apr).
   - **Order Status Flag**: groups the source status into *Delivered* (from Completed), *Pending* and *Cancelled*.
3. **Pivot Tables**: 7 PivotTables summarizing category sales, product sales, location sales, payment method usage, order status, top customers, and monthly sales.
4. **Dashboard**: the final interactive dashboard with:
   - KPIs: Total Sales and Total Orders
   - 7 charts: Sales by Category, Sales by Product, Sales by Customer Location, Order Status Breakdown, Orders by Payment Method, Top Customers by Total Sales, Monthly Sales Trend
   - 4 slicers: Category, Customer Location, Order Status, Month

---

## Data Checks and Preprocessing

The following checks were performed on the dataset:

- Checked the dataset structure and data types.
- Checked for duplicate records: **none found** (no duplicate rows or Order IDs).
- Checked for missing values: **none found**.
- Converted the Date column to short date format, formatted Price to two decimal places, and confirmed Price, Quantity and Total Sales are numeric.
- Checked category, product and location names for consistency: **no inconsistencies found**.
- Validated that **Total Sales = Price × Quantity** for all 250 orders: **no mismatches**.
- Added the **Month** field for monthly analysis.
- Added the **Order Status Flag** field to group order statuses for the dashboard.

The dataset has no cost price or profit information, so the analysis focuses on **Total Sales and order-level performance**, not profit.

> **Important:** *Total Sales* is the value of all orders placed, **including cancelled and pending orders**. It is not realised revenue (see the Order Status findings below).

---

## Dashboard KPIs

| KPI | Result |
|---|---:|
| Total Orders | **250** |
| Total Sales (all orders) | **243,845** |
| Average Sales per Order | **975.38** |
| Completed / Delivered Orders | **88 (35.2%)** |
| Pending Orders | **85 (34.0%)** |
| Cancelled Orders | **77 (30.8%)** |

> The dashboard displays Total Sales and Total Orders as KPI cards. The other figures come from the analysis in the Pivot Tables and Cleaned Data sheets.
> The source `Status` field uses *Completed*; the cleaned data maps it to the label *Delivered*.

---

## Insights & Findings

### 1. Electronics is the highest-selling category

| Category | Total Sales | Share of Total Sales |
|---|---:|---:|
| Electronics | 129,950 | 53.29% |
| Home Appliances | 105,000 | 43.06% |
| Footwear | 4,320 | 1.77% |
| Clothing | 3,540 | 1.45% |
| Books | 1,035 | 0.42% |
| **Total** | **243,845** | **100%** |

Electronics and Home Appliances together contribute about **96.35%** of total sales, so the business depends heavily on high-value products.

### 2. Refrigerator is the top-selling product

| Rank | Product | Total Sales |
|---:|---|---:|
| 1 | Refrigerator | 78,000 |
| 2 | Laptop | 58,400 |
| 3 | Smartphone | 48,500 |
| 4 | Washing Machine | 27,000 |
| 5 | Smartwatch | 15,750 |
| 6 | Headphones | 7,300 |
| 7 | Running Shoes | 4,320 |
| 8 | Jeans | 2,480 |
| 9 | T-Shirt | 1,060 |
| 10 | Book | 1,035 |

Refrigerator alone contributes about **31.99%** of total sales. Refrigerator, Laptop and Smartphone together generate **184,900 (75.83%)**.

### 3. Miami leads locations, but sales are fairly evenly spread

| Rank | Location | Total Sales | Share |
|---:|---|---:|---:|
| 1 | Miami | 31,700 | 13.00% |
| 2 | Denver | 29,785 | 12.21% |
| 3 | Houston | 28,390 | 11.64% |
| 4 | Dallas | 27,145 | 11.13% |
| 5 | Seattle | 26,890 | 11.03% |
| 6 | Boston | 26,170 | 10.73% |
| 7 | Chicago | 20,810 | 8.53% |
| 8 | New York | 18,940 | 7.77% |
| 9 | Los Angeles | 17,820 | 7.31% |
| 10 | San Francisco | 16,195 | 6.64% |

Miami is the strongest location, but its lead over Denver is only about 1,900. The **weakest locations are San Francisco, Los Angeles and New York**, each below 8% of total sales, which makes them candidates for review or targeted promotions.

### 4. Only about a third of orders are completed/delivered

| Status | Orders | % of Orders | Sales Value | % of Sales |
|---|---:|---:|---:|---:|
| Delivered / Completed | 88 | 35.2% | 88,530 | 36.3% |
| Pending | 85 | 34.0% | 90,285 | 37.0% |
| Cancelled | 77 | 30.8% | 65,030 | 26.7% |
| **Total** | **250** | **100%** | **243,845** | **100%** |

- Delivered is the largest status group, but only narrowly (88 vs 85 pending).
- **64.8%** of orders are pending or cancelled.
- Cancelled orders account for **65,030** of the 243,845 total. Excluding them, sales are **178,815**.
- Delivered orders account for only 88,530 in sales, so a large share of the value is still pending or was lost to cancellations.

### 5. PayPal is the most-used payment method

| Payment Method | Orders | Percentage |
|---|---:|---:|
| PayPal | 60 | 24.0% |
| Credit Card | 54 | 21.6% |
| Debit Card | 53 | 21.2% |
| Gift Card | 42 | 16.8% |
| Amazon Pay | 41 | 16.4% |
| **Total** | **250** | **100%** |

Usage is spread across all five methods; no single method dominates.

### 6. February recorded the highest monthly sales

| Month | Orders | Total Sales |
|---|---:|---:|
| February | 113 | 122,695 |
| March | 131 | 117,730 |
| April | 6 | 3,420 |
| **Total** | **250** | **243,845** |

February's sales are slightly higher than March's even though March had more orders. The data starts on 2 February and ends on 2 April, so **April contains only 6 orders and should not be compared with the full months**.

### 7. Top customers by total sales

| Rank | Customer | Total Sales |
|---:|---|---:|
| 1 | Olivia Wilson | 36,170 |
| 2 | Jane Smith | 31,185 |
| 3 | Emma Clark | 29,700 |
| 4 | John Doe | 26,870 |
| 5 | Emily Johnson | 23,475 |

Olivia Wilson is the highest-value customer, based on total order value (including cancelled and pending orders).

---

## Key Business Findings Summary

| Area | Key Finding |
|---|---|
| Total Sales (all orders) | 243,845 |
| Total Orders | 250 |
| Best Category | Electronics (129,950) |
| Best Product | Refrigerator (78,000) |
| Best Location | Miami (31,700) |
| Weakest Location | San Francisco (16,195) |
| Most Used Payment Method | PayPal (60 orders) |
| Largest Order Status | Completed / Delivered (88 orders, narrowly) |
| Sales Value of Cancelled Orders | 65,030 (26.7%) |
| Highest-Sales Customer | Olivia Wilson (36,170) |
| Highest-Sales Month | February (122,695) |

---

## Recommendations

1. **Focus on high-performing categories.** Electronics and Home Appliances generate the majority of sales, so inventory planning and promotions can prioritize them.
2. **Keep top products in stock.** Refrigerators, Laptops and Smartphones are the strongest contributors, and stock-outs here would cost the most.
3. **Investigate pending orders.** 85 orders (34.0%, worth 90,285) are pending. Check for payment issues, fulfilment delays, inventory availability and processing delays.
4. **Reduce cancellations.** 77 orders (30.8%, worth 65,030) were cancelled. Analyzing cancellation reasons could reduce lost sales and improve the customer experience. The dataset has no cancellation reason, so this needs additional data.
5. **Strengthen strong locations and review weak ones.** Miami, Denver and Houston lead on sales and suit retention campaigns. San Francisco, Los Angeles and New York underperform and may need local promotions or investigation.
6. **Keep multiple payment options.** PayPal is the most used, but Credit Card and Debit Card are close behind.
7. **Monitor monthly trends as more data arrives.** The data covers about two months, with April nearly empty, so it is too short to establish reliable trends.

---

## Dashboard Features

**Visualizations:** Sales by Category, Sales by Product, Sales by Customer Location, Order Status Breakdown, Orders by Payment Method, Top Customers by Total Sales, Monthly Sales Trend.

**Slicers:** Category, Customer Location, Order Status, Month. These let users filter all dashboard views interactively.

---

## Limitations

- No cost or profit data, so profitability cannot be analyzed.
- Total Sales includes pending and cancelled orders, so it overstates realised revenue.
- The data covers about two months, and April has only 6 orders.
- Only 10 customers appear in the data, so customer rankings reflect a very small base.
- No cancellation or delay reasons are recorded.

---

## Repository Structure

```text
Amazon-Sales-Performance-Analysis/
│
├── README.md
├── Amazon_Sales_Performance_Analysis.xlsx   # Raw Data, Cleaned Data, Pivot Tables, Dashboard
├── Dashboard_Screenshot.png
│
└── Documentation/
    └── Project_Documentation.pdf
```

---

## Skills Demonstrated

Microsoft Excel · Data Quality Checks · Data Preprocessing · Excel Formulas · PivotTables · PivotCharts · Slicers · KPI Development · Data Visualization · Business Data Analysis · Insight Generation · Dashboard Development · GitHub Documentation

---

## Conclusion

The analysis covers **250 orders and 243,845 in total sales** from February to early April 2025. Electronics was the strongest category, Refrigerator the top product, Miami the top location, and PayPal the most-used payment method.

The most important finding is operational: only **35.2% of orders were completed/delivered**, while **34.0% were pending and 30.8% cancelled**. Because Total Sales includes all of these orders, addressing pending and cancelled orders is the clearest opportunity to improve results.

---

**Deliverable:** `Amazon_Sales_Performance_Analysis.xlsx` · **Tool:** Microsoft Excel · **Dataset:** 250 orders · **Total Sales analyzed:** 243,845