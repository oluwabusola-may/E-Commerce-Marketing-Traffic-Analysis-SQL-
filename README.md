
# E-Commerce Marketing & Traffic Analysis (SQL)

## Project Overview
This project involves a deep dive into e-commerce data to analyze website performance, marketing channel efficiency, and product profitability. Using SQL, I extracted insights from thousands of user sessions and orders to identify growth patterns, conversion bottlenecks, and refund risks.

## Business Questions Addressed
* How has website traffic grown over time, and what seasonal patterns exist?
* Which devices (Desktop vs. Mobile) provide the best conversion rates?
* How effective are specific marketing campaigns in driving high-quality traffic?
* Which products are driving the most profit, and which are underperforming?

## Tools & Skills
* **Language:** SQL (MySQL/PostgreSQL)
* **Key Techniques:** Joins, Aggregate Functions, Time-Series Analysis, Case Statements, Subqueries, and Conversion Rate (CR) Calculation.
* **Focus:** Growth Analysis, Retention Strategy, and Financial Optimization.

## Analysis & Insights

### 1. Traffic & Growth Trends
* **The Query:** Analyzed monthly sessions to track year-over-year growth.
* **Insight:** Found explosive **248% growth** in 2012, peaking at nearly 60,000 sessions in late 2014. However, a consistent "Post-Holiday Hangover" occurs every Q1, where traffic drops by up to 50% by March.
* **Recommendation:** Implement a loyalty re-engagement campaign in January to stabilize the Q1 slump.

### 2. Conversion Optimization (Device Type)
* **The Query:** Compared sessions vs. orders across Desktop and Mobile devices.
* **Insight:** Desktop users significantly outperform mobile users in conversion rates.
* **Recommendation:** Prioritize UI/UX improvements for the mobile checkout flow to capture the growing segment of mobile-first shoppers.

### 3. Product Profitability & Refunds
* **The Query:** Calculated net profit (Price - COGS) and refund rates per product.
* **Insight:** Product 1 is the primary revenue driver (generating over $738k), while certain products show negative profit margins or high refund rates.
* **Recommendation:** Discontinue or re-evaluate products with negative margins and investigate the supply chain for high-refund items.

## SQL Samples
*Below is an example of the logic used to calculate conversion rates by device:*

```sql
SELECT 
    ws.device_type,
    COUNT(DISTINCT ws.website_session_id) AS sessions,
    COUNT(DISTINCT o.order_id) AS orders,
    COUNT(DISTINCT o.order_id) / COUNT(DISTINCT ws.website_session_id) AS conversion_rate
FROM website_session ws
LEFT JOIN orders o ON o.website_session_id = ws.website_session_id
GROUP BY 1;
```

## How to Use This Repository
1.  **SQL Script:** View `[Marketing & Traffic Analysis fuzzy.sql](https://github.com/user-attachments/files/26522735/Marketing.Traffic.Analysis.fuzzy.sql) for the full list of queries.
2.  **Summary of Findings:** The `[Marketing & Traffic Analysis fuzzy.txt](https://github.com/user-attachments/files/26522704/Marketing.Traffic.Analysis.fuzzy.txt)` file contains the business logic and recommendations derived from the data.
### Why this project matters:
This analysis goes beyond just "writing code." It demonstrates a **Business-First** mindset—showing that I don't just see numbers, I see opportunities to increase revenue and improve user experience.
