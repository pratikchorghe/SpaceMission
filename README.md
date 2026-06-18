# Amazon Global Store — Sales Analytics Dashboard

**End-to-end retail analytics dashboard analyzing global sales performance, profitability, regional trends, and customer segments across 165 countries — built with Power BI and the Global Superstore dataset.**

---

## Project Overview

This project analyzes the Global Superstore dataset to uncover sales trends, profit drivers, regional performance, and customer behavior across 5 global markets. The dashboard provides actionable business insights for retail decision-makers covering product categories, shipping modes, discount impact on profitability, and year-over-year growth.

---

## Tools and Technologies

| Tool | Purpose |
|------|---------|
| Power BI Desktop (DAX, Power Query) | Interactive dashboard and data modeling |
| Excel | Source dataset (Global Superstore 2016) |
| DAX | Calculated measures and KPIs |
| Power Query | Data transformation and cleaning |

---

## Dataset Summary

| Metric | Value |
|--------|-------|
| Total Orders | 51,290 rows |
| Countries | 165 |
| Markets | 5 (LATAM, Europe, Asia Pacific, USCA, Africa) |
| Years Covered | 2012 to 2015 |
| Categories | Technology, Furniture, Office Supplies |
| Customer Segments | Consumer, Corporate, Home Office |
| Total Sales | $12.6 Million |
| Total Profit | $1.47 Million |

### Dataset Columns (23 fields)

Order ID, Order Date, Ship Date, Ship Mode, Customer ID, Customer Name, Segment, Postal Code, City, State, Country, Region, Market, Product ID, Category, Sub-Category, Product Name, Sales, Quantity, Discount, Profit, Shipping Cost, Order Priority

---

## Key Business Questions Answered

| Question | Answer Found |
|----------|-------------|
| Which market generates highest revenue? | USCA and Europe lead total sales |
| Which category is most profitable? | Technology has highest profit margin |
| Which sub-category loses money? | Tables and Bookcases have negative profit due to high discounts |
| Which shipping mode is most used? | Standard Class — 60%+ of all orders |
| How does discount affect profit? | Discounts above 20% lead to consistent losses |
| Which customer segment is most valuable? | Consumer segment drives most volume |
| Which region has best YoY growth? | Asia Pacific shows fastest growth 2012-2015 |

---

## Dashboard Pages

### Page 1 — Executive Summary
- KPI cards: Total Sales, Total Profit, Profit Margin %, Total Orders, Avg Order Value
- Sales trend line chart 2012-2015
- Sales by Market donut chart
- Top 10 Countries by Sales bar chart
- Year and Market slicers

### Page 2 — Product Performance
- Sales and Profit by Category (Technology, Furniture, Office Supplies)
- Sub-Category profitability comparison
- Top 10 products by Sales
- Bottom 10 products by Profit (loss-making products)
- Discount vs Profit scatter chart

### Page 3 — Regional Analysis
- World map — bubble size by Sales, color by Profit Margin
- Market comparison bar chart
- Region drill-down (Market to Country)
- Shipping Cost by Region

### Page 4 — Customer Segments
- Consumer vs Corporate vs Home Office comparison
- Segment revenue trend 2012-2015
- Order Priority distribution
- Ship Mode preference by Segment

---

## DAX Measures

```
Total Sales = SUM(Orders[Sales])

Total Profit = SUM(Orders[Profit])

Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0)

Total Orders = COUNTROWS(Orders)

Avg Order Value = DIVIDE([Total Sales], [Total Orders], 0)

YoY Sales Growth = 
DIVIDE(
    [Total Sales] - CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Date'[Date])),
    CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Date'[Date])),
    0
)

Loss Making Orders = 
CALCULATE(COUNTROWS(Orders), Orders[Profit] < 0)
```

---

## Key Insights

1. **Technology leads profitability** — Despite lower order volume than Office Supplies, Technology generates the highest profit margin at 18%+.

2. **Furniture loses money on discounts** — Tables and Bookcases show negative profit when discount exceeds 30%. High shipping costs compound the loss.

3. **Standard Class dominates shipping** — Over 60% of orders use Standard Class. Same Day delivery is less than 5% of orders.

4. **USCA and Europe are revenue leaders** — Combined they account for over 55% of total global sales.

5. **Consumer segment drives volume** — Consumer orders represent 50%+ of total orders but Corporate has higher average order value.

6. **Asia Pacific growing fastest** — Year-over-year sales growth in Asia Pacific outpaces all other markets from 2013 to 2015.

7. **Heavy discounts destroy profit** — Orders with 40%+ discount show consistent negative profit across all categories.

---

## File Structure

```
amazon-global-store-analytics/
│
├── data/
│   └── global_superstore_2016.xlsx     # Source dataset (51,290 rows)
│
├── dashboard/
│   └── AmazoneGlobalStore.pbix         # Power BI dashboard file
│
└── README.md
```

---

## How to Run

**Power BI:**
1. Download Power BI Desktop (free) from microsoft.com/powerbi
2. Open `AmazoneGlobalStore.pbix`
3. If data source path error appears: Transform Data → Data Source Settings → update path to your local `global_superstore_2016.xlsx`
4. Click Refresh

---

## Dataset Source

Global Superstore Dataset — widely used retail analytics benchmark dataset covering global orders across 4 years, 165 countries and 3 product categories.

---

## About

**Analyst:** Pratik Chorghe

**Experience:** 3+ years Data Analyst | Power BI, Python, SQL | Hospitality Domain (GIATA GmbH)

**Other Projects:**
- [Global Hotel Industry Analytics Dashboard](https://github.com/pratikchorghe/Global-Hospitality-Analytics-Dashboard) — End-to-end hospitality project with Python, SQL, forecasting and Power BI
- [Cricket T20 World Cup Analysis](https://github.com/pratikchorghe/Cricket-T20-World-cup-data)
- [Hospital Management Dashboard](https://github.com/pratikchorghe/Hospital-Management-Dashbard)

**Connect:** [LinkedIn](https://linkedin.com/in/pratikchorghe) | [GitHub](https://github.com/pratikchorghe)
