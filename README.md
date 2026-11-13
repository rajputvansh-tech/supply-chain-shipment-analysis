# Global Health Supply Chain Shipment Analysis (SQL)

A beginner-friendly SQL data analysis project exploring shipment costs, vendor distributions, and freight efficiency across global health supply chain data.

## 📌 Project Overview
The goal of this project is to practice core SQL querying techniques by answering practical logistics and supply chain questions using MySQL. Rather than jumping straight into complex transformations, this analysis focuses on writing clean, readable queries to extract baseline business metrics from raw shipment records.

## 🛠️ Tools & Concepts Used
* *Database:* MySQL (MySQL Workbench)
* *SQL Concepts:* SELECT, Aggregate Functions (SUM), Aliases (AS), Calculated Fields, and GROUP BY


## 🔍 Key Questions & Queries

### 1. Total Freight Cost by Product Group
Calculated the total shipping spend across different medical product categories (HRDT, ARV, ACT, MRDT, ANTM) to identify where the highest logistics costs are concentrated.
```sql
SELECT Product group,
       SUM(Freight Cost (USD)) AS total_freight
FROM raw_data
GROUP BY Product Group;


2. Vendor-wise Freight Expense
​Analyzed total freight costs broken down by pharmaceutical vendors (such as Aurobindo Pharma, Cipla, and Trinity Biotech) to see how shipping expenses are distributed across suppliers.
SELECT Vendor,
       SUM(Freight Cost (USD)) AS total_freight
FROM raw_data
GROUP BY Vendor;


3. Shipping Cost Efficiency (Cost per Kilogram)
​Created an aggregate ratio dividing total freight cost by total shipment weight to evaluate which product groups are the most or least cost-efficient to ship per kilogram.

SELECT Product group,
       SUM(Freight Cost (USD)) / SUM(Weight (Kilograms)) AS cost_per_kg
FROM raw_data
GROUP BY Product Group;


💡 What I Learned
​Structuring Aggregations: Using GROUP BY effectively to summarize large tables of raw shipment logs into readable summaries.
​Metric Creation: Combining multiple aggregate functions (SUM() / SUM()) to compute weighted ratios like cost per kilogram rather than averaging pre-calculated rows.
​Handling Real-World Column Names: Working with spaces and special characters in raw dataset headers using backticks in MySQL.


​🚀 Future Improvements
​As I continue building my SQL skills, I plan to expand this repository with:
​ORDER BY and LIMIT clauses to rank top vendors and highest-cost routes.
​CASE statements to categorize shipments by weight tiers or cost brackets.
​Data cleaning queries to handle missing or non-numeric entries in freight and weight columns.
