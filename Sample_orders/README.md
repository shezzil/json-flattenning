#  E-Commerce Orders JSON Flattening Project

##  Overview

This project demonstrates how to parse and flatten a complex **nested JSON structure containing customer orders, product details, and customer information** into clean, separate, analysis-ready tables using Python and pandas.

It mimics real-world e-commerce data workflows where transaction logs must be structured into fact and dimension tables for reporting, analytics, or warehousing.

>  Built with real data transformation logic you'd use in actual ETL pipelines and dimensional modeling for BI or data warehouses.

---

##  Project Workflow

The original `assignment_orders.json` contains nested JSON with customer-level objects, each having a list of orders, and each order containing a list of products.

This project flattens and extracts:

| Table         | Description                                             |
|---------------|---------------------------------------------------------|
| `df_orders`   | Fact table with order-level transactions per product    |
| `df_ProductDim` | Dimension table with unique product attributes         |
| `df_customer` | Dimension table with customer info                      |

---

##  Technologies Used

- **Python 3.10+**
- `pandas` – DataFrame creation, transformation, deduplication  
- `json` – File reading and nested JSON parsing  

---

##  Skills Demonstrated

✅ Parsing deeply nested JSON  
✅ Fact-Dimension modeling from semi-structured data  
✅ Deduplicating product dimension using `sort` + `drop_duplicates`  
✅ Safe data transformation using loops and `.append()`  
✅ Column pruning and renaming for analytics readiness

---

##  Output Tables Preview

###  Orders Table (`df_orders`)
| order_id | customer_id | product_id | quantity | total_amount |
|----------|-------------|------------|----------|---------------|
| 1001     | C001        | P01        | 2        | 250.00        |

###  Product Dimension (`df_ProductDim`)
| product_id | name           | category    | price |
|------------|----------------|-------------|-------|
| P01        | Wireless Mouse | Electronics | 25.00 |

###  Customer Dimension (`df_customer`)
| customer_id | cust_name  | email_id          | address           |
|-------------|------------|-------------------|-------------------|
| C001        | Alice Wong | alice@example.com | 123 Queen St, TO  |

---

##  How It Works

- Read the nested JSON file
- Iterate through customers → orders → products
- Extract rows for:
  - Transactions (`df_orders`)
  - Product attributes (`df_ProductDim`)
  - Customer info (`df_customer`)
- Deduplicate product dimension using product_id and most recent order

---

##  Use Cases

-  Sales analytics per customer or product  
-  Building a star schema (fact + dimension)  
-  Feeding BI dashboards or data warehouses  
-  Data quality checks for e-commerce platforms

---

##  How to Run

1. Clone the repository  
2. Install dependencies:  
   ```bash
   pip install pandas
   ```
3. Place `file_name.json` in your working directory  
4. Run the Python script to generate flattened tables

---


