# Customer Behavior & RFM Analysis | Power BI

**Customer analytics portfolio project** exploring revenue performance, RFM-based customer segmentation, repeat purchasing, and customer retention through a four-page interactive Power BI report.

> **Dataset notice:** This project uses **synthetic data** for learning and portfolio demonstration. The findings, customer records, and business recommendations do not describe a real company.

## Dashboard Preview

### 1. Customer Analytics | Executive Overview

![Customer Analytics Executive Overview](Customer%20Overview.png)

An executive view of revenue, order volume, registered and purchasing customers, average order value, monthly revenue trends, regional performance, top customers, and selected customer-level RFM details.

### 2. Customer Analytics | RFM Segmentation

![RFM Customer Segmentation](RFM%20Segmentation.png)

Segments customers using **Recency, Frequency, and Monetary (RFM)** analysis. Compares customer counts and revenue contribution across Champions, Loyal Customers, Potential Loyalists, Regular Customers, At Risk, Lost Customers, and No Purchases. Includes a segment performance summary and business insights.

### 3. Customer Analytics | Retention & Loyalty

![Customer Retention and Loyalty](Customer%20Retention.png)

Examines purchasing behavior with a **cohort retention matrix**, monthly retention performance table, monthly retention trend, repeat-purchase metrics, and retention-focused insights. The cohort heatmap helps highlight changes in purchasing activity over time.

### 4. Customer Analytics | Executive Insights

![Customer Analytics Business Insights](Business%20Insights.png)

Summarizes the most important findings and proposes actionable business initiatives focused on protecting high-value customers, reactivating At Risk customers, encouraging first and second purchases, and monitoring retention.

## Data Model & Relationships

![Power BI Data Model](Model%20View.png)

The report uses a dimensional model centered on the `orders` fact table, with one-to-many relationships from the `customers`, `products`, and `Date` dimensions to `orders`.

- **`orders` (fact table):** Order-level transactions, customer and product keys, purchase dates, and quantities.
- **`customers` (dimension):** Customer attributes and calculated fields supporting customer and RFM analysis.
- **`products` (dimension):** Product information and categories.
- **`Date` (date dimension):** Calendar fields for monthly trends and time-based analysis.
- **`Key Measures`:** A dedicated table for organizing DAX measures.
- **`Cohort Periods`:** A supporting table for cohort month offsets.
- **`RFM Segments`:** A supporting table for customer segment reporting and ordering.

The cohort and RFM helper tables are not shown as directly related to the `orders` fact table in the model view; they support analysis through report calculations and measures.

## Business Questions

- How much revenue did customers generate, and how does performance vary by month and region?
- Which customers and customer segments contribute the most revenue?
- Which customers may benefit from re-engagement campaigns?
- What share of purchasing customers placed more than one order?
- How does monthly and cohort retention vary over time?
- What customer-focused actions could the business test next?

## Data & Model

The project uses three synthetic source files:

- [`customers.csv`](customers.csv) — customer information
- [`orders.csv`](orders.csv) — customer orders and purchase activity
- [`products.csv`](products.csv) — product information

The Power BI model also includes supporting date, RFM segment, and cohort-analysis structures. Relationships enable analysis across customer, order, product, and time dimensions.

**Data preparation:** Power Query was used to import and inspect source data, validate column types, and prepare the data for analysis. DAX was used to calculate business metrics, customer segments, and retention measures.

## Tools & Analytical Skills

| Area | Skills demonstrated |
|---|---|
| Power BI Desktop | Interactive dashboards, KPI cards, tables, matrices, charts |
| Power Query | Data import, inspection, type validation, preparation |
| DAX | Revenue measures, customer counts, RFM logic, retention calculations |
| Data Modeling | Relationships and supporting dimension/analysis tables |
| Customer Analytics | RFM segmentation, customer value analysis, repeat purchases |
| Retention Analytics | Monthly retention, cohort analysis, retention heatmap |
| Business Communication | Executive insights and recommendations |

## Key Metrics

*Reference values below represent the complete synthetic dataset without additional report filters. Displayed figures may be rounded.*

| Metric | Result |
|---|---:|
| Total Revenue | SAR 306,804.50 |
| Total Orders | 700 |
| Registered Customers | 180 |
| Purchasing Customers | 161 |
| Average Order Value | SAR 438.29 |
| Repeat Customers | 136 |
| One-Time Customers | 25 |
| Repeat Purchase Rate | 84.47% |
| Champions | 31 customers |
| At Risk | 30 customers |

## RFM Segmentation Results

RFM groups customers according to three behavioral dimensions:

- **Recency:** How recently a customer purchased.
- **Frequency:** How often a customer purchased.
- **Monetary:** How much revenue a customer generated.

| Segment | Customers | Revenue (SAR) | Revenue Share |
|---|---:|---:|---:|
| Champions | 31 | 114,557.10 | 37.34% |
| Loyal Customers | 42 | 95,798.40 | 31.22% |
| At Risk | 30 | 59,980.05 | 19.55% |
| Regular Customers | 16 | 18,620.90 | 6.07% |
| Potential Loyalists | 14 | 9,620.55 | 3.14% |
| Lost Customers | 28 | 8,227.50 | 2.68% |
| No Purchases | 19 | 0.00 | 0.00% |
| **Total** | **180** | **306,804.50** | **100.00%** |

*Revenue shares are rounded to two decimal places. “At Risk” is an RFM classification, not proof that a customer has churned.*

## Retention & Repeat Purchase Analysis

The report distinguishes two different behavioral concepts:

**Repeat Purchase Rate** measures the share of purchasing customers who placed at least two orders during the analysis period:

`Repeat Purchase Rate = Repeat Customers / Purchasing Customers`

`136 / 161 = 84.47%`

**Monthly Retention Rate** tracks customers who purchased again in a given month relative to the previous month's purchasing customers, using the report's monthly retention logic. It should not be confused with the overall repeat purchase rate.

**Cohort Retention** groups customers by their first purchase month and measures subsequent purchasing activity by months since that first purchase. Month `0` represents the initial cohort period and appears as 100% in the matrix.

## Key Business Findings

1. **Revenue concentration:** Champions and Loyal Customers generated approximately **68.56%** of total revenue (based on the displayed segment shares).
2. **Customer reactivation opportunity:** The **30 At Risk customers** generated approximately **SAR 59.98K** in historical revenue.
3. **Repeat purchasing:** **136 of 161 purchasing customers** placed at least two orders, yielding an **84.47%** repeat purchase rate.
4. **Regional performance:** **Madinah** generated the highest regional revenue at approximately **SAR 89.8K**.
5. **Retention variation:** Monthly and cohort views show differences in repeat purchasing activity across time periods.

These findings are descriptive. Additional customer, marketing, and operational data would be needed to establish causes or predict the impact of interventions.

## Business Recommendations

1. **Protect high-value customers:** Test loyalty initiatives for Champions and Loyal Customers.
2. **Re-engage At Risk customers:** Pilot targeted reactivation campaigns and measure their effectiveness.
3. **Encourage first and second purchases:** Develop targeted offers for registered non-buyers and one-time customers.
4. **Monitor retention consistently:** Track repeat purchase rate, monthly retention, and cohort retention separately.
5. **Investigate regional differences:** Compare regional revenue alongside customer counts, order volume, and average order value.

## Report Pages & Interaction

1. **Executive Overview:** Explore revenue and customer activity by time, region, and customer.
2. **RFM Segmentation:** Compare segment size, revenue contribution, and customer value.
3. **Retention & Loyalty:** Review cohort and monthly retention patterns alongside repeat purchasing.
4. **Executive Insights:** Read the consolidated findings and recommended actions.

Visual interactions and filters are available in the analytical pages. **Executive insight text is static** and summarizes the unfiltered dataset; it does not automatically update with every visual selection.

## How to Run

1. Download the [Power BI report](Customer_RFM_Analysis_Professional.pbix) from this repository.
2. 2. Open it using **Microsoft Power BI Desktop**.
3. Navigate through the four report pages.
4. Interact with charts and tables to explore different subsets of the data.
5. If a refresh is needed, ensure the included CSV files are available locally and update their paths through **Transform data → Data source settings** or the relevant Power Query source steps.

## Suggested Repository Structure

```text
Customer-Behavior-RFM-Analysis-PowerBI/
├── README.md
├── Customer_RFM_Analysis_Professional.pbix
├── customers.csv
├── orders.csv
├── products.csv
├── Customer Overview.png
├── RFM Segmentation.png
├── Customer Retention.png
└── Business Insights.png
```

> Screenshot links above assume the five PNG files are stored in the repository root, alongside `README.md`. If you put them in a subfolder, update the image paths accordingly.

## Project Scope & Limitations

- The dataset is **synthetic** and intended solely for educational and portfolio purposes.
- Results describe historical behavior in the supplied sample; they are not causal findings or forecasts.
- RFM categories depend on the scoring and segmentation rules implemented in the report.
- Static executive insight cards describe the full dataset and are not dynamic narrative measures.

---

**Portfolio focus:** Power BI · Power Query · DAX · RFM Segmentation · Cohort Retention · Customer Analytics · Business Intelligence
