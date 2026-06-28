# Business Problem Summary

A retail company's leadership team requires an executive dashboard to monitor overall business performance and support strategic decision-making. The organization generates large volumes of sales data, making it difficult to quickly identify trends, profitable areas, operational issues, and business risks through raw reports alone.

The objective of this project is to develop an interactive Tableau dashboard that consolidates key business metrics into a single view. The dashboard enables leadership to analyze sales trends, regional performance, product category profitability, customer segment performance, shipping efficiency, discount impact, and return patterns.

By providing visual insights and interactive filtering, the dashboard helps decision-makers answer important business questions such as:

* How are sales changing over time?
* Which regions generate the highest sales and profit?
* Which product categories and sub-categories are the most profitable?
* Which customer segments contribute the most revenue?
* How do discounts affect profitability?
* Which shipping modes experience longer delivery times?
* Which products or customer groups have higher return rates?
* What are the key business risks and opportunities?

The dashboard transforms raw transactional data into meaningful business insights, allowing executives to identify performance trends, monitor key performance indicators (KPIs), detect operational challenges, and make informed, data-driven decisions to improve profitability, customer satisfaction, and overall business performance.

# Dataset Description

The dataset used in this project contains retail transaction data that captures information about customer orders, product sales, profitability, shipping details, and returns. It is designed to support business analysis and executive reporting by providing both operational and financial metrics.

### Dataset Contents

The dataset includes the following types of information:

* **Order Information:** Order ID, Order Date, Ship Date
* **Customer Information:** Customer Name, Customer Segment
* **Geographic Information:** City, State, Region
* **Product Information:** Category, Sub-Category, Product Name
* **Sales Metrics:** Sales, Profit, Discount, Quantity
* **Shipping Information:** Ship Mode and Shipping Days (calculated)
* **Return Information:** Return Flag (0 = Not Returned, 1 = Returned)

### Data Types

| Data Type          | Examples                                            |
| ------------------ | --------------------------------------------------- |
| Date Fields        | Order Date, Ship Date                               |
| Geographic Fields  | Region, State, City                                 |
| Categorical Fields | Category, Sub-Category, Customer Segment, Ship Mode |
| Numerical Measures | Sales, Profit, Quantity, Discount                   |
| Binary Field       | Return Flag                                         |

### Calculated Fields Created

To support dashboard analysis, the following calculated fields were created in Tableau:

* Profit Margin
* Cost
* Average Order Value
* Return Rate
* Shipping Days
* Shipping Delay Bucket

### Purpose of the Dataset

The dataset enables analysis of:

* Sales trends over time
* Regional sales and profitability
* Product category performance
* Customer segment performance
* Shipping efficiency
* Discount impact on profit
* Product return patterns

The data provides the foundation for building an executive dashboard that helps business leaders monitor performance, identify risks, and make data-driven decisions.

# Tableau Workbook Description

The Tableau workbook was developed to provide an interactive executive dashboard for retail business analysis. It transforms transactional sales data into meaningful visualizations that help leadership monitor sales performance, profitability, customer behavior, shipping efficiency, discount impact, and return patterns.

The dashboard combines KPIs, charts, filters, and interactive features into a single view, allowing users to quickly identify trends, business risks, and growth opportunities.

---

# Calculated Fields Created

The following calculated fields were created in Tableau:

| Calculated Field          | Formula                                                                                     | Purpose                                               |
| ------------------------- | ------------------------------------------------------------------------------------------- | ----------------------------------------------------- |
| **Profit Margin**         | `SUM([Profit]) / SUM([Sales])`                                                              | Measures profitability as a percentage of sales.      |
| **Cost**                  | `[Sales] - [Profit]`                                                                        | Calculates the estimated cost of goods sold.          |
| **Average Order Value**   | `SUM([Sales]) / COUNTD([Order Id])`                                                         | Calculates the average sales value per order.         |
| **Return Rate**           | `AVG([Return Flag])`                                                                        | Calculates the percentage of returned orders.         |
| **Shipping Days**         | `DATEDIFF('day',[Order Date],[Ship Date])`                                                  | Calculates the number of days taken to ship an order. |
| **Shipping Delay Bucket** | Categorizes shipping days into Fast (0–2 Days), Standard (3–5 Days), and Delayed (6+ Days). | Supports shipping performance analysis.               |

---

# Dashboard Components

The executive dashboard includes the following components:

### KPI Cards

* Total Sales
* Total Profit
* Profit Margin
* Total Orders
* Return Rate

### Charts

* Sales Trend (Line Chart)
* Regional Performance (Bar Chart)
* Category Profitability (Bar Chart)
* Customer Segment Performance (Bar Chart)
* Shipping Performance (Bar Chart)
* Discount vs Profit (Scatter Plot)
* Return Analysis (Bar Chart)

The layout follows a logical hierarchy, beginning with KPIs, followed by trend analysis, performance comparisons, operational metrics, and return analysis.

---

# Filters and Interactions Used

### Interactive Filters

* Region
* Category
* Customer Segment
* Ship Mode
* Order Date (if included)

### Dashboard Interaction

A filter action was implemented so that selecting a region updates the other charts dynamically. This enables users to drill down into specific business areas without leaving the dashboard.

---

# Key Business Insights

The dashboard provides several important business insights:

* Sales demonstrate overall growth with seasonal fluctuations.
* Some regions consistently outperform others in sales and profit.
* Certain product categories generate strong sales but lower profit margins.
* Customer segments contribute differently to business performance.
* Higher discounts are often associated with reduced profitability.
* Shipping performance varies across shipping modes.
* Return rates are higher in specific product categories or customer groups.
* Opportunities exist to improve profitability by optimizing pricing, reducing returns, and improving shipping efficiency.

---

# Dashboard Story Summary

The dashboard tells a connected business story by combining financial, operational, and customer performance into one executive view. Leadership can quickly understand overall business health, identify high-performing regions and products, recognize operational challenges, and discover opportunities for growth.

Rather than viewing each chart independently, the dashboard allows executives to explore relationships between sales, profit, discounts, shipping performance, and returns through interactive filtering and drill-down analysis.

---

# Assumptions and Limitations

## Assumptions

* The dataset is complete and accurately represents retail transactions.
* Sales, profit, and return information are correctly recorded.
* Return Flag values represent returned (1) and non-returned (0) orders.
* Shipping dates accurately reflect delivery processing times.
* Calculated fields accurately represent the required business metrics.

## Limitations

* The dashboard is limited to the available dataset and does not include external factors such as marketing campaigns, competitor performance, inventory levels, or customer satisfaction.
* Historical data is used for descriptive analysis only and does not predict future performance.
* Correlations shown in the dashboard should not be interpreted as direct cause-and-effect relationships without additional analysis.
* Business decisions should be supported with further investigation where necessary.


##Part 4
## Task 1-Connect and Inspect Data

Retail Executive Dashboard
Task 1: Connect and Inspect Data
Dataset
File Name: dashboard_sales_data.xlsx
Tool Used: Tableau Desktop
Data Inspection

The dataset was successfully connected to Tableau using the Microsoft Excel connector. The fields were reviewed to verify their data types and classifications.

Date Fields
Order Date
Ship Date
Geographic Fields
Country
Region
State
City
Postal Code
Categorical Fields
Order ID
Customer ID
Customer Name
Segment
Category
Sub-Category
Product Name
Ship Mode
Numerical Measures
Sales
Profit
Quantity
Discount
Binary / Flag Fields
Returned (Yes/No)
Assumptions

The following assumptions were made during data inspection:

Each row in the dataset represents a single order line item.
Order Date and Ship Date are complete and stored in a valid date format.
Sales, Profit, Quantity, and Discount are numeric fields and contain valid business values.
Discount values are assumed to be stored as decimal percentages (for example, 0.20 represents a 20% discount).
Negative profit values are considered valid and represent loss-making transactions.
Geographic fields (Country, Region, State, City, and Postal Code) are assumed to be accurate for mapping and regional analysis.
The Returned field correctly identifies returned orders using Yes/No values.
Missing values, if any, are assumed to be minimal and do not significantly impact the overall dashboard analysis.
All monetary values are assumed to be recorded in the same currency throughout the dataset.

## Task 2


Task 2: Calculated Fields

The following calculated fields were created in Tableau to support executive dashboard analysis.

Calculated Field	Formula	Business Purpose
Profit Margin	SUM([Profit]) / SUM([Sales])	Measures profitability as a percentage of sales.
Cost	[Sales] - [Profit]	Estimates the cost associated with each sale.
Average Order Value	SUM([Sales]) / COUNTD([Order ID])	Calculates the average sales value per order.
Return Rate	SUM(IF [Returned]="Yes" THEN 1 ELSE 0 END) / COUNTD([Order ID])	Calculates the percentage of orders that were returned.
Shipping Days	DATEDIFF('day',[Order Date],[Ship Date])	Calculates the number of days between order and shipment.
Shipping Delay Bucket	Categorizes shipping days into Fast (0–2 Days), Standard (3–5 Days), and Delayed (6+ Days).	Helps identify shipping performance and operational delays.
Business Value

These calculated fields provide key metrics for evaluating profitability, operational efficiency, customer purchasing behavior, return patterns, and shipping performance. They form the foundation of the executive dashboard and enable leadership to make informed business decisions.

# Task-8
# Business Insights

## Insight 1: Sales Trend

**Observation:**
Sales show an overall upward trend over time, with noticeable peaks during certain months.

**Data Evidence:**
The Sales Trend line chart indicates higher sales during peak periods compared to other months.

**Business Interpretation:**
Seasonal demand and promotional campaigns likely contribute to increased sales during these periods.

**Recommended Action:**
Plan inventory and marketing campaigns ahead of peak sales periods to maximize revenue.

---

## Insight 2: Regional Performance

**Observation:**
Some regions generate significantly higher sales and profit than others.

**Data Evidence:**
The Regional Performance chart shows that the top-performing region contributes the highest sales and profitability.

**Business Interpretation:**
Customer demand and market presence vary across regions.

**Recommended Action:**
Study the strategies used in high-performing regions and apply similar practices in lower-performing regions.

---

## Insight 3: Category Profitability

**Observation:**
Not all product categories contribute equally to profit.

**Data Evidence:**
The Category Profitability chart shows that some categories have high sales but relatively low profit margins.

**Business Interpretation:**
Higher sales do not always translate into higher profitability due to costs or discounting.

**Recommended Action:**
Review pricing, product costs, and promotional strategies for low-profit categories.

---

## Insight 4: Customer Segment Behavior

**Observation:**
Customer segments contribute differently to total sales and profit.

**Data Evidence:**
The Customer Segment chart compares sales across all customer segments.

**Business Interpretation:**
Certain customer segments provide greater business value and profitability.

**Recommended Action:**
Develop targeted marketing campaigns and loyalty programs for the highest-value customer segments while improving engagement with lower-performing segments.

---

## Insight 5: Discount Impact

**Observation:**
Higher discounts are generally associated with lower profit.

**Data Evidence:**
The Discount vs Profit scatter plot shows a decline in profit as discount levels increase for many products.

**Business Interpretation:**
Excessive discounting reduces profitability and may not generate sufficient additional sales.

**Recommended Action:**
Review discount policies and apply targeted promotions instead of broad discounts.

---

## Insight 6: Shipping Performance

**Observation:**
Some shipping modes require longer delivery times than others.

**Data Evidence:**
The Shipping Performance chart compares average shipping days across shipping modes.

**Business Interpretation:**
Long delivery times may reduce customer satisfaction and increase operational costs.

**Recommended Action:**
Investigate delayed shipping modes and improve logistics or carrier performance where necessary.

---

## Insight 7: Return Pattern

**Observation:**
Return rates vary across product categories and customer groups.

**Data Evidence:**
The Return Analysis chart identifies categories or customer segments with higher return rates.

**Business Interpretation:**
High return rates may indicate product quality issues, customer expectation gaps, or fulfillment problems.

**Recommended Action:**
Analyze the root causes of returns and implement improvements in product quality, descriptions, or fulfillment processes.

---

## Insight 8: Business Risk and Opportunity

**Observation:**
Products with high sales but low profitability represent both a business risk and an opportunity.

**Data Evidence:**
The dashboard highlights products or categories that generate strong sales while producing limited profit.

**Business Interpretation:**
Revenue growth alone is not sufficient if profit margins remain low.

**Recommended Action:**
Focus on improving margins through pricing optimization, cost reduction, supplier negotiations, and product mix adjustments while continuing to invest in profitable products and regions.
