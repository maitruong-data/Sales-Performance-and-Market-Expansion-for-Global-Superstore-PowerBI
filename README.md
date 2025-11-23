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

<img width="1474" height="829" alt="P2_Market " src="https://github.com/user-attachments/assets/84a1c081-ab8a-42bb-8408-f21d7e2ce5f7" />

**Two important features in this page:**
- **Opportunity Score (Market)**
The Opportunity Score ranks markets by four criterias: Growth (Sales YoY%), Profitability (Margin%), Size (Sales), and Risk (Return rate). Each market is normalized against its peers and scored on a 0–100 scale:
_Score = 0.40*Growth + 0.30*Margin + 0.20*Size – 0.10*ReturnRate_
That weighting favors future upside (growth) and healthy unit economics (margin), rewards scale, and penalizes returns. It lets you rank markets objectively instead of looking at one metric at a time.

- **Pareto 80/20**
Within the selected market, sub-categories are sorted by profit. The cumulative line and the 80% target show the strategic product set that drives most of the money. This chart answers for the question: “If we focus, which products move the needle here?”

📌 **Key Findings**

- **Where to expand next:** The areas with higest opportunity to expand are Canada, EMEA, and Africa. Though APAC, EU, LATAM, US had higher Sales, they showed margin dips or return spikes, which dragged their score.

- **What are strategic products:** The Pareto chart showed each market’s profit concentration by sub-category. For example, in the high-score Canada market, items such as storage, phones, copiers, appliances, bookcases, accessories accounted for ~80% of profit. 
  
- **Quality guardrails:** Return Rate was high in  markets with high order numbers like APAC, LATAM, US, EU. A few likely reasons for the high return rate in big, mature markets:
  - Product mix effect: Large markets sell more variety, including high-return categories (e.g., furniture with sizing/fit issues or fragile items). Mix alone can push the rate up even when processes are good.
  - Promo & price effects: Aggressive discounting drives trial and higher buyer’s remorse. Campaigns that spike orders often spike returns.
  - Ship-mode: Faster modes (and cross-border hops) can correlate with damage or mismatched expectations
  - Customer behavior & policy maturity: Mature markets have easier return policies and more seasoned shoppers. Thus, convenience increases return propensity.
  - Operational scale: With volume, small defects (packaging, QC leakage, inaccurate content) become meaningful at rate level if not actively managed by SKU.

- **Top 5 Sales Managers** were listed. Anna Andreadi ranked 1st with $2.82M Sales across the markets
  
3️⃣ **Product**

<img width="1478" height="829" alt="P2_Product" src="https://github.com/user-attachments/assets/ae16686d-6e75-498a-9d63-c4164a8e6934" />

📌 **Key Findings**
- **Seasonality by month:** Office Supplies had clear seasonality with orders rose through Q4 with peaks in November – December. Technology and Furniture were steadier, with smaller late-year lifts.
- **Ship mode usage:** Standard Class dominated order volume across all categories. First/Second Class were used selectively. Same Day ship mode was niche. That mix likely protected margin but also hid opportunity where faster modes could lift conversion.
- **Category quality:** At category level, Office Supplies carried the lowest return rate (4.95%), Technology was mid (5.77%), and Furniture was the highest (5.92%). So the furniture portfolio continued to be the main returns risk.
- **Sub-category performance (by market):** Copiers, Bookcases, Appliances, Labels, Binders, Storage are top products that bring high-impact profit across several markets. Their Opportunity Score was stronger because they combined good growth, acceptable margin, decent size, and manageable returns.
- **Quality vs Growth by customer segment:**
  - Consumer (growth threshold 49.23%)
    - Points clustered around the 15% margin line with a mix of Low (green) and Medium (amber) returns.
    - Labels, Art, Copiers, Paper sat in Invest (top-right) with healthy margin, above median growth, but mostly medium and high returns.
  - **Corporate (growth threshold 51.71%):**
    - More dispersion and more amber or red than Consumer segment.
    - There were a couple of Invest candidates (Copiers, Applicances, Accessories), but with high return rate
  - **Home Office (growth threshold 55.41%):**
    - A healthy set in Invest and Optimize with low and medium returns => the segment looked the most scalable compared to the other two


🔎 **Recommendations**
- Scale impactful markets: double-down on APAC, EU, US with the current product winner.
- As Average Order Value (AOV) was flat, recommendations to use bundles and premium tiers to add value without discounting
- Fix the margin sink in Furniture. Within each big market, cut or reprice low-margin SKUs, and tighten discounting (Product Performance table in page Product will give more details about this)
- Focus on fast growers. EMEA and Africa were markets where YoY profit growth were strongest. Keep a margin/returns gate so growth wouldn't come at the expense of quality.
- Segment plays to lift revenue quality.

🔎 **Recommendations**
- Expand in the top-score markets (Canada, EMEA, Africa).
  - Fund demand and channel in those markets.
  - Use the Pareto list to build focused campaigns and inventory priorities around the top 4–6 sub-categories.
- Lift Furniture-like margin drags in the big markets (APAC/EU/US).
  - Use the market’s Pareto to find high-volume/low-margin SKUs; fix pricing, bundles, vendor terms, or freight.

🔎 **Recommendations**
- adjust pre-purchase info/QA and ship-mode policies on the worst SKUs to push the rate below 4%.
- Decompose return rate by Market × Sub-Category × Ship Mode and by reason code (if available). Look for “long tails” of a few SKUs driving most returns.
- Mix-normalized view: Compare return rate by category across markets to separate process problems from mix problems.
- Campaign lens: Overlay promo periods—see if spikes align with higher returns.
- Content & QA: For the worst SKUs, review size/spec accuracy, photos, packaging, and supplier QC.
- Policy/ship tuning: Tighten ship-mode rules for fragile or high-return SKUs; consider restocking fees only where abuse is proven.
- 
