
# 🎇 Diwali Sales Analysis 
*SQL & Power BI Project*

## 📌 Project Overview

This project analyzes Diwali festive season sales using SQL and Power BI to uncover insights about **customer behavior**, **top-selling products**, and **regional performance**.
The goal is to transform raw data into **actionable business insights** that can help optimize marketing, inventory, and sales strategies for future festive seasons.

---

# 📑 Table of Contents

1. [Project Overview](#-project-overview)
2. [Objective / Problem Statement](#-objective--problem-statement)
3. [About the Data](#-about-the-data)
4. [Tech Stack](#-tech-stack)
5. [KPIs](#-kpis)
6. [SQL Syntax & KPI Queries](#-sql-syntax--kpi-queries)
7. [Project Structure](#-project-structure)
8. [Dashboard Preview](#-dashboard-preview)

---

# 🎯 Objective / Problem Statement

Businesses experience a huge rise in sales during Diwali, but not all customers, regions, or product categories behave the same.

This project focuses on answering:

* Who spends the most during Diwali?
* Which product categories generate maximum sales?
* How does gender, age group, and marital status affect spending?
* Which states/zones contribute the most revenue?
* Which categories drive festive performance?

These insights can help improve:
- Customer targeting
- Inventory planning
- Marketing strategy
-  Sales forecasting

# 📂 About the Data

The dataset contains:

* Gender, age, age group, marital status
* State & zone
* Occupation
* Orders & amount spent
* Product category
* User ID, Product ID, Order ID

The data was raw and required cleaning:
- Removing null values
- Standardizing demographics
- Formatting states/categories
-  Creating analysis-ready fields

# 🛠 Tech Stack

| Tool            | Purpose                         |
| --------------- | ------------------------------- |
| **SQL (MySQL)** | Data cleaning & analysis        |
| **Power BI**    | Interactive dashboard           |
| **Excel / CSV** | Initial dataset                 |
| **GitHub**      | Documentation & version control |


# 🧩 SQL Syntax & KPI Queries

Below are the SQL queries used throughout the project for KPI calculation and analysis.


## 📊 **Key Performance Indicators (KPIs)**

### 🔹 **Sales Overview**

#### **Q1. Total Revenue**

```sql
SELECT SUM(Amount) AS Total_Revenue 
FROM Diwali_Sales;
```

#### **Q2. Total Orders**

```sql
SELECT COUNT(Orders) AS Total_Orders 
FROM Diwali_Sales;
```

#### **Q3. Average Order Value (AOV)**

```sql
SELECT AVG(Amount) AS Avg_Order_Value 
FROM Diwali_Sales;
```

#### **Q4. State with Highest Revenue**

```sql
SELECT State, SUM(Amount) AS Revenue
FROM Diwali_Sales
GROUP BY State
ORDER BY Revenue DESC
LIMIT 1;
```

---

## 👥 **Customer Insights**

#### **Q5. Gender-wise Sales Contribution**

```sql
SELECT Gender, SUM(Amount) AS Total_Revenue
FROM Diwali_Sales
GROUP BY Gender;
```

#### **Q6. Age Group-wise Average Spending**

```sql
SELECT Age_group, AVG(Amount) AS Average_Spending
FROM Diwali_Sales
GROUP BY Age_group
ORDER BY Age_group;
```

#### **Q7. Marital Status vs Average Spending**

```sql
SELECT Marital_status, AVG(Amount) AS Average_Spending
FROM Diwali_Sales
GROUP BY Marital_status;
```

---

## 🛍️ **Product & Category Analysis**

#### **Q8. Top 5 Product Categories by Revenue**

```sql
SELECT Product_Category, SUM(Amount) AS Total_Revenue
FROM Diwali_Sales
GROUP BY Product_Category
ORDER BY Total_Revenue DESC
LIMIT 5;
```

---

## 🌍 **Regional Performance**

#### **Q9. Top 5 States by Revenue**

```sql
SELECT State, SUM(Amount) AS Total_State_Spending
FROM Diwali_Sales
GROUP BY State
ORDER BY Total_State_Spending DESC
LIMIT 5;
```

#### **Q10. Zone-wise Revenue**

```sql
SELECT Zone, SUM(Amount) AS Total_Zone_Spending
FROM Diwali_Sales
GROUP BY Zone;
```

---

# 📁 Project Structure

```
Diwali-Sales-Analysis/
│
├── data/
│   └── Diwali_Sales_Data.csv
│
├── dashboard/
│   └── Diwali_Sales_Dashboard.pbix
│
├── sql/
│   └── diwali_sales_queries.sql
│
└── README.md
```

---

# 📊 Dashboard Preview

The Power BI dashboard includes:
* KPI Cards (Revenue, Orders, AOV)
* Gender & Age group breakdown
* Top product categories
* State-wise revenue map
* Zone performance charts

 <img width="1166" height="655" alt="image" src="https://github.com/user-attachments/assets/a599fc16-97d0-4d4e-9808-1425ccb13713" />

