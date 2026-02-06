# 🛒 Zepto E-Commerce SQL Data Analyst Portfolio Project

This is a **real-world SQL Data Analyst portfolio project** based on an e-commerce inventory dataset scraped from **Zepto**, one of India’s fastest-growing quick-commerce startups.  
The project simulates **end-to-end data analyst workflows**, starting from raw data exploration to business-driven SQL analysis.

---

## 📌 Project Overview

The objective of this project is to replicate how **data analysts in e-commerce and retail industries** work with messy, real-world data using **SQL** to generate actionable business insights.

In this project, SQL is used to:
- Build and manage an e-commerce inventory database
- Perform **Exploratory Data Analysis (EDA)**
- Clean and standardize raw data
- Write **business-focused SQL queries** to analyze pricing, discounts, inventory, and revenue

---

## 📁 Dataset Overview

- **Source:** Kaggle  
- **Original Data:** Scraped from Zepto’s official product listings  
- **Structure:** Each row represents a unique **SKU (Stock Keeping Unit)**

Duplicate product names exist because the same product can appear in multiple variations (different weights, quantities, discounts, or categories), which closely reflects **real-world e-commerce catalog data**.

---

## 🧾 Dataset Columns

| Column Name | Description |
|------------|------------|
| `sku_id` | Unique identifier for each product (Synthetic Primary Key) |
| `name` | Product name as listed on the app |
| `category` | Product category (Fruits, Snacks, Beverages, etc.) |
| `mrp` | Maximum Retail Price (converted from paise to ₹) |
| `discountPercent` | Discount applied on MRP |
| `discountedSellingPrice` | Final selling price after discount (₹) |
| `availableQuantity` | Units available in inventory |
| `weightInGms` | Product weight in grams |
| `outOfStock` | Boolean flag for stock availability |
| `quantity` | Units per package (mixed with grams for loose produce) |

---

## 🔧 Project Workflow

### 1️⃣ Database & Table Creation

Created a SQL table with appropriate data types to simulate a real inventory system:

```sql
CREATE TABLE zepto (
  sku_id SERIAL PRIMARY KEY,
  category VARCHAR(120),
  name VARCHAR(150) NOT NULL,
  mrp NUMERIC(8,2),
  discountPercent NUMERIC(5,2),
  availableQuantity INTEGER,
  discountedSellingPrice NUMERIC(8,2),
  weightInGms INTEGER,
  outOfStock BOOLEAN,
  quantity INTEGER
);
```
---
## 2️⃣ Data Import

- Imported the dataset using **pgAdmin**
- Faced **UTF-8 encoding issues** during import
- Resolved the issue by saving the dataset in **CSV UTF-8 format**

---
## 3️⃣ Exploratory Data Analysis (EDA)

- Counted the total number of records in the dataset
- Reviewed sample rows to understand data structure and attributes
- Checked for null values across all columns
- Identified distinct product categories
- Compared in-stock vs out-of-stock products
- Detected duplicate product names representing multiple SKUs

---

## 4️⃣ Data Cleaning

- Identified and removed records with zero MRP or discounted selling price
- Converted pricing values from **paise to rupees** for consistency
- Standardized numeric fields for accurate calculations
- Prepared a clean dataset for business and analytical queries

---

## 5️⃣ Business Insights Using SQL

- Identified **top 10 best-value products** based on discount percentage
- Found **high-MRP products** that are currently out of stock
- Estimated **potential revenue by product category**
- Filtered **expensive products (MRP > ₹500)** with minimal discounts
- Ranked **top 5 categories** offering the highest average discounts
- Calculated **price per gram** to identify value-for-money products
- Grouped products into **Low, Medium, and Bulk** weight categories
- Measured **total inventory weight** per category


---

## 🛠️ Tools & Technologies Used

- SQL (PostgreSQL)  
- pgAdmin  
- Relational Database Design  
- Data Cleaning & Transformation  
- Exploratory Data Analysis (EDA)  
- Business & Inventory Analytics  

---

## 📈 Business Value

This analysis helps to:
- Identify profitable product categories  
- Optimize pricing and discount strategies  
- Detect inventory risks (out-of-stock high-value items)  
- Improve data-driven decision-making in e-commerce operations  

---
👤 Author

Suhail Ahmed Khan |
Aspiring Data Analyst | SQL | Data Analytics | Business Intelligence
