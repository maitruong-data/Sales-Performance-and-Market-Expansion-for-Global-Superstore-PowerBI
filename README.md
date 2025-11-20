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

From the data tables above, I created Star Schema Model as below

<img width="1015" height="733" alt="Data Model" src="https://github.com/user-attachments/assets/a741fffe-5a51-4c98-8ba5-1316a999d0a6" />

