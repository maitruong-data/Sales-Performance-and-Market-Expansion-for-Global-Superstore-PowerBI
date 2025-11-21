# Sales Performance and Market Expansion for Global Superstore | Power BI

Author: Mai Truong\
Date: 20 November 2025\
Tool Used: Power BI

***

## 📑**Table of Contents**
1. 📌Overview
2. 📂Dataset Description & Data Structure
3. 🧠Design Thinking Process
4. 📊Key Insights & Visualizations
5. 🔎Final Conclusion & Recommendations

## 📌Overview
🎯**Project Objectives**

This project uses Power BI to analyze and visualize global sale data for a retail company named Superstore, which operates across multiple markets and continents. The company is growing fast and aiming to expand their markets and strategic products\ 
Our main goal is to provide senior managers data-driven insights to:
- Get an overview of business performance in terms of sales, profit, and order return rate over the years, markets and products
- Identify growth markets and strategic products, which lead to better market strategy, commercial tactics and product portfolio
- Shorten decision time

❓**Business questions**
- Overall performance: How is the business performing in general?
- Market performance: How different markets are performing and where should we expand?
- Product performance: What are strategic products should be prioritized?

👤**Target Audience**
- Senior Managers, Regional Managers or Finance Managers who need a reliable view of business performance to compare markets and products, where are they winning or losing, to guide market expansion and product strategy
- Product Managers, Business Strategy, Marketing and Management teams who decide market growth, strategic products and marketing strategies
- Data analysts and Data team who are looking for actionable insights

## 📂Dataset Description & Data Structure
### 📌Data Source
- Context: This is a dataset about a fictional online retail company named Global Superstore, which sells furniture, office supplies and technology products globally.
- The dataset includes 3 tables:
  - Order: 51,281 records
  - People: 13 records
  - Returns: 1172 records
- Format: CSV

### 📊Data Structure & Relationships
1️⃣ **Tables Used**
  - Order: contains sales transactions and customer information (51,281 records)
  - People: contains sales managers responsible for each region (13 records)
  - Returns: contains orders that were returned by customers (1172 records)

2️⃣ **Table Schemas**
<details>
  <summary>Table 1: Order - sales transactions and customer information </summary>
  
| Column Name | Data Type | Description |
|----------|----------|----------|
|OrderID| String| The unique identifier for each order|
|Order Date| Date| The date the order was placed|
|Ship Date| Date| The date the order was shipped|
|Ship Mode| String| Shipping method|
|Customer ID| String| The unique identifier for each customer|
|Customer Name| String| Name of customer|
|Segment| String| Customer Segment (Consumer, Coporate, Home Office)|
|City| String| Customer's city|
|State| String| Customer's state|
|City| String| Customer's city|
|Country| String| Customer's country|
|Postal Code| String| Customer's postal code|
|Market| String| Geographical market|
|Region| String| Geographical region|
|Product ID| String| The unique identifier for each product|
|Category| String| Product's main category|
|Sub-Category| String| Product's sub-category|
|Product Name| String| Name of product|
|Sales| Float| Sales value of the transaction|
|Quantity| Integer| Quantity of product sold in the transaction|
|Profit| Float| Profit from the transaction|

</details>

<details>
  <summary>Table 2: People - sales managers responsible for each region</summary>

| Column Name | Data Type | Description |
|----------|----------|----------|
|Person| String| Name of sale manager|
|Region| String| Region where the sale manager is responsible for|

</details>

<details>
  <summary>Table 3: Returns - orders that were returned by customers</summary>

| Column Name | Data Type | Description |
|----------|----------|----------|
|Returned| String| Indication if the order was returned (e.g., Yes)|
|Order ID| String| The unique identifier for each order|

</details>

3️⃣**Data Relationship**

From the data tables above, I created Star Schema Model as below

<img width="1015" height="733" alt="Data Model" src="https://github.com/user-attachments/assets/a741fffe-5a51-4c98-8ba5-1316a999d0a6" />

**Relationships between tables**

| From Table | To Table | Join Key | Relationship Type |
|----------|----------|----------|----------|
|Orders| DimCustomer| Orders.CustomerID = DimCustomer.CustomerID| Many-to-One |
|Orders| DimProduct| Orders.ProductKey = DimProduct.ProductKey| Many-to-One |
|Orders| Return| Orders.OrderID = Returns.OrderID| Many-to-One |
|Orders| DimDate| Orders.Order Date = DimDate.Date| Many-to-One |
|Orders| People| Orders.Region = People.Region| Many-to-One |

## 🧠Design Thinking Process

1️⃣ Empathize
2️⃣ Define point of view
3️⃣ Ideate
4️⃣ Prototype and review


## 📊Key Insights & Visualizations

### 🔍Dashboard Preview

1️⃣ **Overview**

<img width="1482" height="830" alt="P2_Overview" src="https://github.com/user-attachments/assets/6f5445d2-cd62-46b1-b0be-1d0ea76e3a7f" />

📌 **Key Findings**
- Overall, in 2011-2014 period, the company was in a strong growth cycle. Total sales reached $12.64M and total profit was $1.47M. Both were up a little over +51% YoY. Order volume increased around +52%, which shows growth is broad-based and not just price effects. Profit margin was 11.61%, return rate improved by 1.45%, and AOV was steady around $505 => This suggested that the company sold more, kept margins intact, and reduced product returns—good operating discipline.
- Time len: Sales and profit grew, while margin peaked around 2013 and eased slightly. Returns trended down overall while orders ramped.
- Market len: APAC, EU, and US contribute the bulk of revenue and profit. Smaller regions such as EMEA and Africa show the fastest YoY profit growth, suggesting room to invest where we already see momentum. All markets had positive profit YoY%, in which EMEA and Africa ranked highest.
- Product Category len: Technology was the largest and profitable. Furniture drove revenue but showed a low margin compared to the other categories. Office Supplies was stable mid-margin. Furniture was likely where leakage sat.
- Demand and profit were high from Consumer customer segment, followed by Corporate and Home Office => This was an opportunity to design segment-specific growth, especially to lift Corporate and Home Office penetration and basket size.

2️⃣ **Market**


📌 **Recommendations**
- Scale impactful markets: double-down on APAC, EU, US with the current product winner.
- As Average Order Value (AOV) was flat, recommendations to use bundles and premium tiers to add value without discounting
- Fix the margin sink in Furniture. Within each big market, cut or reprice low-margin SKUs, and tighten discounting (Product Performance table in page Product will give more details about this)
- Focus on fast growers. EMEA and Africa were markets where YoY profit growth were strongest. Keep a margin/returns gate so growth wouldn't come at the expense of quality.
- Segment plays to lift revenue quality.
