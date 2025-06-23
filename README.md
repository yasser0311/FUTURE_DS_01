# 📊 Superstore Sales Dashboard - Power BI Project

## 📁 Project Overview

This project presents an interactive **Business Sales Dashboard from E-commerce Data** built using Microsoft Power BI. The dashboard is designed for a fictional Superstore dataset and provides valuable insights for business decision-makers on:

- 🏆 Top-performing products
- 📈 Monthly sales trends
- 🌍 Regional performance
- 🗂️ Category-wise analysis
- 📊 Key performance metrics

---

## 📦 Dataset

- **Source**: [Superstore Dataset - Kaggle](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)
- **Format**: Excel (.xls / .xlsx)
- **Contents**: Order-level data including fields like:
  - Order Date, Ship Date
  - Category, Sub-Category
  - Sales, Profit, Quantity, Discount
  - Customer Segment, Region, State, City

---

## 🔧 Tools & Technologies Used

- **Power BI Desktop**
- **Microsoft Excel (for initial exploration)**
- **DAX (Data Analysis Expressions)** for KPIs
- Optional: Power Query Editor (for data transformation)

---

## 🧹 Data Cleaning & Transformation

Performed in Power BI Power Query:
- Removed unnecessary columns (e.g., Postal Code)
- Converted `Order Date` & `Ship Date` to Date format
- Created new columns: `Year`, `Month`, `Month-Year`
- Removed duplicates and null values
- Verified data types for all columns

---

## 🧮 DAX Measures Used

```dax
-- Average Order Value
Avg Order Value = SUM('Orders'[Sales]) / DISTINCTCOUNT('Orders'[Order ID])

-- Profit Margin %
Profit Margin % = DIVIDE(SUM('Orders'[Profit]), SUM('Orders'[Sales])) * 100

-- Top Product Sales Contribution %
Product Sales % = DIVIDE(SUM('Orders'[Sales]), CALCULATE(SUM('Orders'[Sales]), ALL('Orders'[Product Name]))) * 100
