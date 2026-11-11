# Zepto E-commerce Product Analysis | PostgreSQL

## Project Overview
This project analyzes product-level data from a quick-commerce/e-commerce inventory dataset using PostgreSQL. It explores product categories, pricing, discounts, stock availability, and inventory weight to answer practical business questions.

The SQL script includes data exploration, data cleaning, and analytical queries.

## Objectives
- Explore the structure and quality of product data.
- Identify duplicate product names and missing values.
- Clean invalid price records and convert prices from paise to rupees.
- Analyze discounts, product availability, category-level inventory, and price per gram.
- Practice SQL techniques commonly used in data analyst workflows.

## Tools & Technologies
- **Database:** PostgreSQL
- **Language:** SQL

## Dataset & Table
The project uses a table named `zepto` with product-level fields:

| Column | Description |
|---|---|
| `sku_id` | Unique SKU identifier (primary key) |
| `category` | Product category |
| `name` | Product name |
| `mrp` | Maximum retail price |
| `discountPercent` | Discount percentage |
| `availableQuantity` | Available inventory quantity |
| `discountedSellingPrice` | Discounted selling price |
| `weightInGms` | Product weight in grams |
| `outOfStock` | Stock availability flag |
| `quantity` | Quantity field in the dataset |

> **Dataset source:** https://www.kaggle.com/datasets/palvinder2006/zepto-inventory-dataset/data?select=zepto_v2.csv

## Project Workflow

### 1. Data Exploration
- Count the records in the table.
- Preview sample rows.
- Check for NULL values in important columns.
- List distinct product categories.
- Compare in-stock and out-of-stock product counts.
- Find product names appearing across multiple SKUs.

### 2. Data Cleaning
- Identify records with zero MRP or discounted selling price.
- Delete records where MRP is zero.
- Convert MRP and discounted selling price from paise to rupees.

> Note: The script identifies zero discounted selling prices, but the deletion step removes only rows with `mrp = 0`.

### 3. Business Analysis
The project answers these questions:

1. **Top 10 best-value products:** Which products have the highest discount percentage?
2. **High-MRP products out of stock:** Which out-of-stock products have an MRP above ₹300?
3. **Estimated category revenue:** What is the estimated value by category using discounted selling price × available quantity?
4. **High-MRP, low-discount products:** Which products have MRP above ₹500 and discounts below 10%?
5. **Top categories by average discount:** Which five categories have the highest average discount percentage?
6. **Price per gram:** Which products weighing at least 100 g offer the lowest price per gram?
7. **Weight classification:** How can products be grouped into Low, Medium, and Bulk weight categories?
8. **Category inventory weight:** What is the total inventory weight for each category?

## SQL Skills Demonstrated
- `SELECT`, `DISTINCT`, `WHERE`, `ORDER BY`, `LIMIT`
- `GROUP BY` and `HAVING`
- Aggregate functions: `COUNT()`, `SUM()`, `AVG()`
- `CASE WHEN` conditional expressions
- Data quality checks for NULLs and duplicates
- `DELETE` and `UPDATE`
- Numeric calculations and `ROUND()`
- Boolean filtering

## Repository Structure

```text
E-commerce-Product-Analysis/
├── E_commerce_project.sql
└── README.md
```

## How to Run
1. Install PostgreSQL and open pgAdmin or another PostgreSQL client.
2. Create or select a database.
3. Load the dataset into a table named `zepto` using the column structure in the SQL script.
4. Open `E_commerce_project.sql`.
5. Execute the script in order.

> The SQL script creates the table structure, but the dataset itself must be imported separately before the analysis queries return meaningful results.


## Conclusion
This project demonstrates how PostgreSQL can be used to inspect, clean, and analyze product and inventory data, then translate the results into pricing, discount, and stock-related business questions.

---

## Author
**Sambit Dash**
