# ☕ Monday Coffee — City Expansion Analysis

> **An end-to-end SQL project to identify the top 3 Indian cities for Monday Coffee's first physical store expansion — driven entirely by data.**

---

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/95bb072b-52db-49d2-87c5-6a7653bf5567" />



## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Business Problem](#-business-problem)
- [Dataset Description](#-dataset-description)
- [Database Schema](#-database-schema)
- [Business Questions Answered](#-business-questions-answered)
- [Key Insights](#-key-insights)
- [Final Recommendations](#-final-recommendations)
- [Tools & Technologies](#️-tools--technologies)
- [Project Structure](#-project-structure)
- [How to Run](#-how-to-run)
- [Connect With Me](#-connect-with-me)

---

## 📖 Project Overview

Monday Coffee is an online coffee retailer that has been selling its products across India since **January 2023**.

As part of their growth strategy, the leadership team wants to open **physical coffee shop locations** in Indian cities. This project uses **SQL-based analysis** on 12+ months of sales data to evaluate cities across multiple business dimensions and recommend the best markets for expansion.

---

## 🧩 Business Problem

> *"Which 3 Indian cities should Monday Coffee open their first physical stores in?"*

To answer this, we analyzed:
- Where coffee consumers are concentrated
- Which cities generate the most revenue
- How sales per customer compare across cities
- How rent costs weigh against revenue potential
- Which products perform best in each market

---

## 🗃️ Dataset Description

The dataset covers Monday Coffee's online sales from **January 2023 to December 2023** and consists of **4 tables**:

| Table | Description |
|---|---|
| `city` | City names, population, and estimated rent |
| `customers` | Customer IDs and their associated city |
| `products` | Product names and pricing |
| `sales` | Transaction-level data — customer, product, sale amount, date |

---

## 🧱 Database Schema

```
city
├── city_id (PK)
├── city_name
├── population
└── estimated_rent

customers
├── customer_id (PK)
├── customer_name
└── city_id (FK → city)

products
├── product_id (PK)
├── product_name
└── price

sales
├── sale_id (PK)
├── sale_date
├── product_id (FK → products)
├── customer_id (FK → customers)
└── total
```

---

## ❓ Business Questions Answered

| # | Question |
|---|---|
| 1 | How many people in each city are estimated to consume coffee? (25% of population) |
| 2 | What is the total revenue from coffee sales in Q4 2023? |
| 3 | How many units of each product have been sold? |
| 4 | What is the average sales amount per customer in each city? |
| 5 | Which cities have existing Monday Coffee customers, and how many? |
| 6 | What is the average monthly sales revenue per city? |
| 7 | What are the top 3 selling products in each city? |
| 8 | How many unique customers purchased in each city in Q4 2023? |
| 9 | Which city has the highest average monthly sales growth? |
| 10 | What is the average sale amount per customer vs. average rent per customer in each city? |

---

## 🔍 Key Insights

- **Pune** generates the highest total revenue among all cities, with a low average rent per customer — making it highly cost-efficient.
- **Delhi** has the largest estimated coffee consumer base (~7.7 million), and the highest customer headcount across the platform.
- **Jaipur** shows the best rent-to-revenue balance — very low average rent (₹156/customer) combined with strong average sales per customer (₹11.6K).
- Top-performing products vary by city, indicating localized demand worth targeting in physical menus.
- Monthly revenue trend shows consistent growth throughout 2023, validating physical expansion as a viable next step.

---

## ✅ Final Recommendations

Based on consumer size, revenue performance, average sales per customer, and rent costs:

### 🥇 1. Pune
- Highest total revenue in the dataset
- Low average rent per customer
- High average sales per customer
- **Best overall ROI potential**

### 🥈 2. Delhi
- Largest coffee consumer base (7.7M estimated)
- Highest total number of customers on the platform
- Rent per customer still under ₹500 — manageable at scale
- **Best for market volume and brand visibility**

### 🥉 3. Jaipur
- Highest customer count in city-level data (69 customers)
- Lowest average rent per customer (₹156)
- Strong average sales per customer (₹11.6K)
- **Best for lean, high-margin operations**

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **PostgreSQL** | Database management and query execution |
| **SQL** | Data extraction, transformation, and analysis |
| **pgAdmin / DBeaver** | Query interface and result visualization |

---

## 📁 Project Structure

```
monday-coffee-expansion-sql/
│
├── README.md                         ← You are here
├── schema.sql                        ← Table definitions & relationships
│
├── data/
│   ├── city.csv
│   ├── customers.csv
│   ├── products.csv
│   └── sales.csv
│
├── queries/
│   ├── 01_coffee_consumers_by_city.sql
│   ├── 02_total_revenue_q4_2023.sql
│   ├── 03_sales_count_per_product.sql
│   ├── 04_avg_sales_per_customer.sql
│   ├── 05_city_customer_count.sql
│   ├── 06_monthly_sales_by_city.sql
│   ├── 07_top_products_by_city.sql
│   ├── 08_unique_customers_q4.sql
│   ├── 09_monthly_sales_growth.sql
│   └── 10_rent_vs_revenue_analysis.sql
│
└── assets/
    └── erd_diagram.png               ← Entity Relationship Diagram
```

---

## 🚀 How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/monday-coffee-expansion-sql.git
   cd monday-coffee-expansion-sql
   ```

2. **Set up the database**
   - Open PostgreSQL (pgAdmin or psql)
   - Run `schema.sql` to create all tables

3. **Load the data**
   - Import each `.csv` from the `/data` folder into its respective table

4. **Run the queries**
   - Execute files in `/queries/` in numbered order
   - Each file is self-contained and answers one business question

---

## 🔗 Connect With Me

If you found this project helpful or want to discuss data analytics, feel free to reach out!

- 💼 [LinkedIn](www.linkedin.com/in/ajay-yadav-457610332)
- 📧 sy4573924@gmail.com

- 🐙 [GitHub](https://github.com/Ajay92146)

---

*If you liked this project, consider giving it a ⭐ — it helps a lot!*
