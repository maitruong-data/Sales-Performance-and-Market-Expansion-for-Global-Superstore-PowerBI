# Sales Performance and Market Expansion for Global Superstore | Power BI

Author: Mai Truong\
Created Date: 20 November 2025\
Updated Date: 19 December 2025\
Tool Used: Power BI

***

## 📑**Table of Contents**
1. 📌[Overview](#overview)

2. 🔎[Key Insights & Recommendations](#key-insights--recommendations)

3. 📊[Analysis in Details](#-analysis-in-details)

3.1. 📂[Dataset Description & Data Structure](#-dataset-description--data-structure)

3.2. 🧠[Design Thinking Process](#-design-thinking-process)

3.3. 📊[Visualizations and Insights in detailed](#-visualizations)

## 📌Overview
🎯**Project Objectives**

This project uses Power BI to analyze and visualize global sale data for a retail company named Superstore, which operates across multiple markets and continents. The company is growing fast and aiming to expand their markets and strategic products.

Our main goal is to provide senior managers data-driven insights to:
- Get an overview of business performance in terms of sales, profit, products and order return rate over the years, markets and products
- Identify growth markets and strategic products, which lead to better market strategy, commercial tactics and product portfolio
- Shorten decision time

❓**Business questions**
- Overall performance: How is the business performing in general?
- Market performance: How different markets are performing and where should we expand?
- Product performance: What are strategic products should be prioritized?

👤**Target Audience**
- Senior Managers, Regional Managers or Finance Managers who need a reliable view of business performance to compare markets and products, where they are winning or losing, to guide market expansion and product strategy
- Product Managers, Business Strategy, Marketing and Management teams who decide market growth, strategic products and marketing strategies
- Data analysts and Data team who are looking for actionable insights

## 🔎Key Insights & Recommendations

### Key Insights

1️⃣ **Business overview**

<img width="1554" height="875" alt="Overview" src="https://github.com/user-attachments/assets/d3c617ca-19fc-4dd9-bae0-6a1703f00206" />

- **The company was in a strong growth cycle:** Sales $12.64M and Profit $1.47M. Total Orders also rose at a similar pace (\~52%), so growth was volume-driven, not only price or mix.
- **Quality held while scaling:** Margin 11.61%, Return Rate 4.68%, AOV ~$505 (stable). In short, company had more revenue, better retention of profit, and lower waste.
- Technology products were the profit engine. Furniture drove revenue but had low profit margin. Smaller regions like EMEA, Africa, Canada showed the fastest profit YoY momentum.
- **By Customer segment**: Consumer customers brought the most profit in all product categories: Furniture, Office Supplies and Technology.

2️⃣**Markets**

<img width="1554" height="875" alt="Market" src="https://github.com/user-attachments/assets/f6fcb947-6b5d-43c5-bd29-5191beeac69d" />


- Where to grow: APAC, EU, and US delivered \~70%+ of profit contribution with solid margins and highest orders. EMEA, Africa, Canada showed the fastest profit YoY%, signaling rising markets.
- What to sell: Pareto chart showed which products and sub-products that each market should concentrate. For example, in APAC market, Phones, Copiers, Appliances/Bookcases/Chairs made up ~80% of profit.

3️⃣**Categories & sub-categories**

<img width="1386" height="777" alt="Product" src="https://github.com/user-attachments/assets/a642c089-f81c-42ee-9619-62b70995b8f8" />

- Office Supplies drove volume but low value. It had the most orders and clear Q4 seasonality, but the lowest AOV (\~$199). Technology and Furniture were profit drivers with much higher AOVs (\~$568/\~$501) despite fewer orders.
- Top performers by sub-category were concentrated across markets were Copiers, Labels, Bookcases, Appliances, Binders, Storage repeatedly contributed outsized profit. Return risk at product level stayed at around 6%–7%.

### Recommendations
📌**Lift AOV in Office Supplies:** Package best-seller bundles (e.g., Paper + Binders + Storage), add subscribe-and-save, and set free-shipping thresholds to raise AOV from ~$199 toward $230–$250 without extra operational load.

📌**Protect and scale Technology and Furniture products:** Attach warranties or installation, tighten product content and packaging, and route bulky SKUs to premium ship modes, targeting returns ≤ 6% and margin ≥ 15%.

📌**Focus growth by market:** Double down on APAC, EU, US with Pareto sub-category assortments, and pilot a light rollout in EMEA, Africa, Canada where profit YoY are strongest.

📌**Replace blanket discounts for Corporate:** Use value-based offers (e.g., warranty, SLAs, implementation), set price guardrails, and pass through freight on heavy items to protect margin.

### Where to expand & What to expand

| Market | Product | 
|----------|----------|
|APAC| Phones, Copiers, Appliances, Bookcases, Chairs |
|EU | Bookcases, Copiers, Appliances, Phones, Accessories, Art, Storage |
|US| Copiers, Phones, Accessories, Paper, Binders|

## 📊 Analysis in Details

## 📂 Dataset Description & Data Structure
### 📌 Data Source
- Context: This is a dataset about a fictional online retail company named Global Superstore, which sells furniture, office supplies and technology products globally.
- The dataset includes 3 tables:
  - Order: 51,281 records
  - People: 13 records
  - Returns: 1172 records
- Format: CSV

### 📊 Data Structure & Relationships

1️⃣ **Table Schemas**
<details>
  <summary>Table 1: Order - sales transactions and customer information (51,281 records) </summary>
  
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
  <summary>Table 2: People - sales managers responsible for each region (13 records) </summary>

| Column Name | Data Type | Description |
|----------|----------|----------|
|Person| String| Name of sale manager|
|Region| String| Region where the sale manager is responsible for|

</details>

<details>
  <summary>Table 3: Returns - orders that were returned by customers (1172 records) </summary>

| Column Name | Data Type | Description |
|----------|----------|----------|
|Returned| String| Indication if the order was returned (e.g., Yes)|
|Order ID| String| The unique identifier for each order|

</details>

2️⃣**Data Relationship**

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

## 🧠 Design Thinking Process

Design Thinking is a human-centered, iterative way to solve problems. You start with people, frame the right problem, explore options, build quick versions, and learn by testing and looping until it works.

1️⃣ **Empathize - understand people & context**

Use **5W1H** to ground the work.
- Who are the stakeholders and users?
- What decisions do they need to make? What info helps/hurts?
- Why does this matter (business goals, pain points)?
- When will they use the solution (cadence, time pressure)?
- Where will they use it (device, meeting room, field)?
- How do they work today (tools, workflows, constraints)?

**Outputs:** user personas, roles, pains & gains, current workflow map, list of must-have metrics.


2️⃣ **Define point of view - frame the problem clearly**

What are the core reasons users should use this dashboard? If there's no such dashboard, what are their pains?

Define Northstar metrics, points of view the stakeholders want to see. For each point of view, develop growth formula to look deeper the problem

**Outputs:** problem statement, objectives, KPIs, acceptance criteria.

3️⃣ **Ideate - explore solution options**

Start with Growth Formula breakdown from each point of view, brainstorming the dashboard related to that point of view and connect to the Northstar metrics

**Outputs:** shortlisted concepts, information architecture, draft layouts.

4️⃣**Prototype**

Build the smallest thing that proves the idea.
Questions: What’s the fastest prototype that stakeholders can react to? What sample data or interactions do we need?
**Outputs:** clickable prototype or dashboard ver 1

5️⃣**Review & iterate**

Put it in front of real users; measure, tweak, repeat.

- Questions: Can they answer their key questions in < N minutes? What’s confusing? What’s missing? What would they change?
- Metrics: task success rate, time to insight, error points, satisfaction.

Prioritize fixes, next iteration plan, validated solution

## 📊 Visualizations and Insights in detailed

1️⃣ **Overview**

<img width="1554" height="875" alt="Overview" src="https://github.com/user-attachments/assets/cfac5988-cd45-4c39-8362-cd9c0ab876bb" />


📌 **Key Findings**
- **Overall**, in 2011-2014 period, the company was in a strong growth cycle. Total sales reached $12.64M and total profit was $1.47M. Both had +51% YoY. Total Order volume increased around 52%, which showed growth was broad-based and not just price effects. Profit margin was 11.61%, return rate improved by 1.45%, and AOV was steady around $505 => This suggested that the company sold more, kept margins intact, and reduced product returns => good operating discipline.
- **Time len:** Sales and profit grew, while margin peaked in 2013 and eased slightly. Returns trended down overall while Order trend ramped.
- **Market len:** APAC, EU, and US contributed the bulk of revenue and profit. Smaller regions such as EMEA, Canada and Africa had much less revenue and profit but showed the fastest YoY profit, suggesting room to invest where we already see momentum.
- **Product Category len:** Technology was the largest and profitable. Furniture drove revenue but showed a low margin compared to the other categories. Office Supplies was stable mid-margin => Furniture was likely where leakage sat.
- **Customer Segment len:** Demand and profit were high for all producr categories from Consumer customers, followed by Corporate and Home Office => This was an opportunity to design segment-specific growth, especially to lift Corporate and Home Office penetration and basket size.

2️⃣ **Market**

<img width="1554" height="875" alt="Market" src="https://github.com/user-attachments/assets/284d0a19-e2a5-400d-bc79-d3effc028017" />

**Pareto 80/20**
Within the selected market (viewed by product categories or sub-categories), products were sorted by profit. The pareto line 80% showed 20% strategic products that drove 80% of the profit. This chart answered for the question: “If we focus, which products move the needle here?”

📌 **Key Findings**

- **Where to expand next:** The markets with highest profit contribution were APAC, EU & US. They also had high profit margin, only after Canada (26.62%).

- **What are strategic products:** The Pareto chart showed each market’s profit concentration by category and sub-category. For example, in APAC, items such as Phones, Copiers, Appliances, Bookcases, Chairs accounted for ~80% of profit. 
  
- **Quality guardrails:** Return Rate was high in markets with high profit contribution and vice versa. A few likely reasons for the high return rate in big, mature markets:
  - Product mix effect: Large markets sell more variety, including high-return categories (e.g., furniture with sizing/fit issues or fragile items). Mix alone can push the rate up even when processes are good.
  - Promo & price effects: Aggressive discounting drives trial and higher buyer’s remorse. Campaigns that spike orders often spike returns.
  - Ship-mode: Faster modes (and cross-border hops) can correlate with damage or mismatched expectations
  - Customer behavior & policy maturity: Mature markets have easier return policies and more seasoned shoppers. Thus, convenience increases return propensity.
  - Operational scale: With volume, small defects (packaging, QC leakage, inaccurate content) become meaningful at rate level if not actively managed by SKU.

- **Top 5 Sales Managers** were listed. Anna Andreadi ranked 1st with $2.82M Sales across the markets
  
3️⃣ **Product**

<img width="1386" height="777" alt="Product" src="https://github.com/user-attachments/assets/8f5c6769-c350-47a8-acc9-74795ad6ab5d" />


📌 **Key Findings**
- **Seasonality by month:** Office Supplies had clear seasonality with orders rose through Q4 with peaks in November – December. Technology and Furniture were steadier, with smaller late-year lifts.
- **Ship mode usage:** Standard Class dominated order volume across all categories. First/Second Class were used selectively. Same Day ship mode was niche. That mix likely protected margin but also hid opportunity where faster modes could lift conversion.
- **Return Risk:** At category level, all categories had similar return risk (6-7%)
- **Sub-category performance (by market):** Copiers, Tables, Bookcases, Appliances, Labels, Binders, Storage are top products that bring high-impact profit across several markets with high profit margin.
- Office Supplies had by far the most orders and units, but the smallest average order value (\~$199). Technology and Furniture are profit drivers with much higher average order values (\~$568 for Tech, \~$501 for Furniture) though they have far fewer orders => We should bundle and cross-sell to lift AOV without adding more operational load.
- **Quality vs Growth by customer segment (Top 10 sub-category products by Sales YoY:**
  - Consumer (Margin target 15%, Average Sales YoY 49.92%)
    - Most sub-category products had medium and high return rate.
    - Labels, Art, Copiers, Paper, Art sat (top-right) had healthy margin, above average growth.
  - **Corporate (Margin target 15%, Average Sales YoY 56.6%):**
    - Most product fell below Margin Target and Average Sales YoY.
    - Accessories was top candidate, but with high return rate
  - **Home Office (Margin target 15%, Average Sales YoY 63.24%):**
    - Most product fell below Margin Target and Average Sales YoY.
    - Labels and Copiers are the top products worth investing

