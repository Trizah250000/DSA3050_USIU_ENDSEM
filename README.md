# DSA3050_USIU_ENDSEM
# Advanced Power BI Analytical Solution: Brazilian E-Commerce Performance Dashboard

## 1. Project Title

**Brazilian E-Commerce Performance Dashboard: Revenue, Delivery Logistics & Customer Satisfaction Analytics**

---

## 2. Student Name and Admission Number

| Field | Information |
|:---|:---|
| **Student Name** | [Trizah Nzioka] |
| **Admission Number** | [----74] |


---

## 3. Course Code and Class

| Field | Information |
|:---|:---|
| **Course Code** | DSA 3050A |
| **Course Title** | Business Intelligence and Data Visualization |
| **Class** | SS 2026 |
| **Institution** | [United States International University-Africa(USIU-A) ] |

---

## 4. Project Overview

This project presents a complete end-to-end Power BI analytical solution for an e-commerce marketplace. Using the Brazilian E-Commerce Public Dataset by Olist, I built a star-schema data model, performed data cleaning and transformation in Power Query, created 11 DAX measures, and designed a 3-page interactive dashboard.

The dashboard enables stakeholders to understand:
- Overall sales performance and revenue drivers
- Product category profitability
- Delivery logistics efficiency across Brazilian states
- Customer satisfaction patterns
- Payment method performance


---

## 5. Problem Statement

Olist, a Brazilian e-commerce marketplace, seeks to improve its operational efficiency, customer satisfaction, and revenue performance through data-driven insights. The analysis focuses on the following key areas:

### 5.1 Product Category Performance and Revenue Drivers
- Identify product categories generating the highest revenue and order volume
- Evaluate average order value (AOV) across categories
- Detect underperforming categories and potential causes

### 5.2 Delivery Logistics Efficiency and Customer Satisfaction
- Analyze the impact of delivery delays on customer reviews
- Examine relationships between freight costs, delays, and negative feedback
- Identify regions experiencing delivery inefficiencies

### 5.3 Payment Methods Performance
- Determine the most frequently used payment methods
- Compare total revenue and average transaction value by payment type

### 5.4 Sales Trends and Growth Patterns
- Analyze monthly and seasonal sales trends
- Identify peak periods and key growth-driving categories

### 5.5 Seller Performance and Risk Identification
- Identify regions with consistent underperformance
- Assess potential impact on customer satisfaction

---

## 6. Dataset Description

### 6.1 Dataset Source
- **Name:** Brazilian E-Commerce Public Dataset by Olist
- **Source:** Kaggle (https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
- **License:** Open for public use
- **Time Period:** 2016-2018

### 6.2 Dataset Size
| Metric | Value |
|:---|:---|
| Total rows (order_items) | 112,650+ |
| Total tables used | 7 |
| Total file size | ~126 MB |

### 6.3 Tables Used

| Table Name | Key Columns | Purpose |
|:---|:---|:---|
| olist_orders | order_id, customer_id, order_purchase_timestamp, order_delivered_customer_date | Order timeline and delivery |
| olist_order_items | order_id, product_id, price, freight_value | Transaction line items (fact table) |
| olist_products | product_id, product_category_name | Product attributes |
| olist_customers | customer_id, customer_city, customer_state | Customer geography |
| olist_order_reviews | order_id, review_score | Customer satisfaction |
| olist_order_payments | order_id, payment_type, payment_value | Payment method analysis |
| product_category_name_translation | product_category_name, product_category_name_english | Portuguese to English translation |

### 6.4 Why This Dataset is Suitable for Advanced Power BI Analysis

| Requirement | How Dataset Meets It |
|:---|:---|
| 3+ related tables | 7 related tables enable star schema |
| 9,000+ rows in main table | 112,650+ rows in order_items |
| Categorical + numerical variables | Categories (state, product) + numbers (price, review_score) |
| Date field for time intelligence | order_purchase_timestamp (2016-2018) |

---

## 7. Tools Used

| Tool | Purpose |
|:---|:---|
| **Power BI Desktop** | Data modeling, DAX measures, dashboard design |
| **Power Query Editor** | Data cleaning, transformation, merging |
| **GitHub** | Version control and project submission |
| **Kaggle** | Dataset source |
| **Microsoft Word** | PDF report documentation |

---

## 8. Steps Followed

### 8.1 Part A: Data Acquisition and Understanding (10 Marks)
- Downloaded 7 CSV files from Kaggle
- Defined business problem and domain (E-commerce Analytics)
- Documented table structures and relationships
- Took screenshots of raw data

### 8.2 Part B: Data Cleaning and Transformation (20 Marks)
Performed **11 transformations** in Power Query:

| # | Transformation | Purpose |
|:---|:---|:---|
| 1 | Remove unnecessary columns | Reduce memory, improve performance |
| 2 | Fix wrong data types | Enable calculations (dates to Date type, prices to Decimal) |
| 3 | Merge translation into products | Convert Portuguese categories to English |
| 4 | Create Delivery Days custom column | Calculate days from purchase to delivery |
| 5 | Create Review Category conditional column | Group scores into Positive/Neutral/Negative |
| 6 | Extract Year from date | Enable year filtering |
| 7 | Extract Quarter from date | Enable quarterly analysis |
| 8 | Extract Month Name from date | Readable charts |
| 9 | Merge orders + order_items | Create central fact table |
| 10 | Trim text columns | Remove hidden spaces |
| 11 | Add full state names via mapping table | Improve readability (SP → São Paulo) |

### 8.3 Part C: Data Modeling (15 Marks)
- Identified **Order_Items** as fact table
- Identified **Customers, Products, Reviews, Payment, Date** as dimension tables
- Created relationships (Many-to-One, One-to-Many)
- Created **Date table** using Power Query (continuous date range 2016-01-01 to 2018-12-31)
- Hidden lookup tables (Product_translation, State_mapping) for clean model view

### 8.4 Part D: DAX Measures and Calculated Columns (20 Marks)
Created **11 measures** and **2 calculated columns**:

**Calculated Columns:**
- `DeliveryDelayCategory` (Fast/Normal/Slow/Very Slow)
- `ReviewSentimentScore` (Very Poor/Poor/Average/Good/Excellent)

**Measures:**
1. Total Revenue
2. Total Orders
3. Average Order Value
4. Distinct Customers
5. Average Delivery Days
6. Average Review Score
7. Revenue YTD
8. Revenue Growth (MoM)
9. Category Revenue %
10. Revenue per Item
11. Top Category Rank

### 8.5 Part E: Dashboard Design (20 Marks)
Designed **3 interactive report pages**:

| Page | Name | Key Visuals |
|:---|:---|:---|
| 1 | Executive Summary | KPI cards, line chart, bar chart, slicers |
| 2 | Detailed Analysis | Scatter plot, stacked column chart, matrix |
| 3 | Insights & Performance | Top 5/Bottom 5 tables, delivery by state bar chart |

### 8.6 Part F: Analytical Insights (10 Marks)
Extracted 5 insights and 3 recommendations (see Section 11 below)

### 8.7 Part G: GitHub Documentation (5 Marks)
Created this repository with all files and detailed README

---

## 9. Dashboard Features

### 9.1 Page 1: Executive Summary
| Feature | Description |
|:---|:---|
| KPI Cards | Total Revenue ($14.42M), Total Orders (99K), AOV ($146), Distinct Customers (96K), Avg Review Score (4.09) |
| Line Chart | Revenue trend over time (2016-2018) |
| Bar Chart | Top 10 categories by revenue |
| Slicers | Year filter, Category filter |

### 9.2 Page 2: Detailed Analysis
| Feature | Description |
|:---|:---|
| Scatter Plot | Delivery days vs Review score by category |
| Stacked Column Chart | Revenue by category and state |
| Slicers | Payment type filter, State filter |

### 9.3 Page 3: Insights & Performance
| Feature | Description |
|:---|:---|
| Top 5 Table | Highest revenue categories |
| Bottom 5 Table | Lowest revenue categories |
| Bar Chart | Average delivery days by state (sorted worst to best) |
| Line Chart | Revenue YTD trend |

### 9.4 Interactive Features
- Cross-filtering across all pages
- Drill-down on date hierarchy (Year → Quarter → Month)
- Tooltips on all visuals
- Slicers for filtering by Year, Category, State, Payment Type

---

## 10. Key DAX Measures

| Measure | DAX Formula | Purpose |
|:---|:---|:---|
| Total Revenue | `SUMX('Order_Items', [price] + [freight_value])` | Primary KPI |
| Total Orders | `DISTINCTCOUNT('Order_Items'[order_id])` | Transaction volume |
| Average Order Value | `DIVIDE([Total Revenue], [Total Orders])` | Customer spending |
| Distinct Customers | `DISTINCTCOUNT('Order_Items'[customer_id])` | Customer base size |
| Average Delivery Days | `AVERAGE('Order_Items'[delivery_days])` | Logistics efficiency |
| Average Review Score | `AVERAGE('Reviews'[review_score])` | Satisfaction |
| Revenue YTD | `TOTALYTD([Total Revenue], 'Date'[Date])` | Annual progress |
| Revenue Growth | `DIVIDE(CurrentMonth - PreviousMonth, PreviousMonth)` | MoM growth |
| Category Revenue % | `DIVIDE([Total Revenue], CALCULATE([Total Revenue], ALL('Products')))` | Category contribution |
| Top Category Rank | `RANKX(ALL('Products'[category_english]), [Total Revenue])` | Category ranking |

---

## 11. Key Insights and Recommendations

### 11.1 Analytical Insights (5)

**Insight #1: Revenue Concentration in Top Categories**
- Top 5 categories generate $5.66M (39% of $14.42M total revenue)
- health_beauty ($1.36M), watches_gifts ($1.26M), bed_bath_table ($1.07M)

**Insight #2: Severe Delivery Delays in Northern States**
- Roraima (28 days), Amapá (26 days), Amazonas (25 days)
- 2-3 times higher than expected (8-10 days)

**Insight #3: High Customer Satisfaction Despite Delivery Issues**
- Average review score: 4.09/5
- Suggests product quality compensates for delivery delays

**Insight #4: Underperforming Categories with Minimal Revenue**
- Bottom 5 categories generate only $4,183 combined (<0.03% of total)

**Insight #5: Seasonal Revenue Patterns**
- Mid-year peaks (May-July) indicate seasonal demand cycles

### 11.2 Actionable Recommendations (3)

**Recommendation #1: Investigate Logistics in Northern States**
- Launch logistics audit for Roraima, Amapá, Amazonas, Alagoas, Pará
- Expected impact: Reduce delivery days from 25-28 to under 12 days

**Recommendation #2: Discontinue Bottom 5 Categories**
- Stop active marketing and inventory for cds_dvds_musicals, fashion_childrens_clothes, flowers, home_comfort_2, security_and_services
- Expected impact: Free working capital, reduce storage costs

**Recommendation #3: Implement Seasonal Inventory Planning**
- Pre-position inventory for top 5 categories before mid-year peaks
- Increase marketing spend 4-6 weeks before peak periods

---

## 12. Challenges Encountered and Solutions

| Challenge | Solution |
|:---|:---|
| Portuguese category names | Merged with translation table to create English column |
| Missing relationships causing same totals across states | Rebuilt relationships, ensured customer_id was brought into fact table |
| Delivery_days stored as text causing AVERAGE errors | Changed data type to Whole Number in Power Query |
| Scatter plot showing blank categories | Applied filter to exclude null category values |
| Matrix showing identical revenue for all states | Replaced with stacked column chart and simple table |
| Date table not relating to fact table | Created Date table in Power Query and established Many-to-One relationship |
| Month names displaying alphabetically (April, August) | Sorted MonthName by Month number |

---

## 13. Conclusion

This project successfully delivered a complete Power BI analytical solution for Olist's e-commerce data. The solution meets all examination requirements:

### Key Achievements
- Built a star schema with 1 fact table and 5 dimension tables
- Created 11 DAX measures including time intelligence and ranking
- Designed 3 interactive dashboard pages with cross-filtering
- Identified 5 actionable insights and 3 recommendations
- Documented all steps with screenshots

### Business Value Delivered
The dashboard enables Olist stakeholders to:
- Identify top revenue drivers (health_beauty, watches_gifts categories)
- Pinpoint logistics problem areas (Northern states with 25+ day delivery)
- Optimize category portfolio by discontinuing underperformers
- Plan inventory around seasonal peaks

---


