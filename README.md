# 📊 Retail Sales & Operational Insights: Superstore Analysis

## 📌 Project Overview
This project involves a comprehensive analysis of a retail dataset comprising **$2.29M in Sales** and **$286K in Profit**. The goal was to move beyond surface-level numbers to identify why the profit margin remains low at **12.4%** despite high sales volume.

---

## 🛠️ Step 1: Data Cleaning & Pre-processing
To ensure data integrity, the following steps were performed in Excel:
* **Date Standardization:** Converted date formats from "DMY" to "MDY" using the **Text to Columns** feature to match the dataset's native structure.
* **Logical Mapping:** Verified that `Product Name` and `Category` were strictly mapped to `Product ID`.
* **Customer Identification:** Ensured `Customer Name` was mapped correctly to `Customer ID`.

---

## 🧪 Step 2: Feature Engineering (The Technical Build)
We created custom columns to extract deeper business logic and actionable insights:

| Feature Name | Formula / Logic Used | Business Purpose |
| :--- | :--- | :--- |
| **Order Year** | `=YEAR([Order Date])` | To perform Year-on-Year (YoY) growth analysis. |
| **Order Month** | `=MONTH([Order Date])` | To identify seasonality and peak sales months. |
| **Shipping Delay** | `=[Ship Date] - [Order Date]` | To measure warehouse operational efficiency in days. |
| **Profit Margin %** | `=([Profit] / [Sales]) * 100` | To identify true profitability per transaction. |
| **Discount Category**| `=IF([Discount] > 0, "Discounted", "No")` | To A/B test the impact of discounts on quantity. |
| **Unique Orders** | `=IF(COUNTIF($B$2:B2, B2)=1, 1, 0)` | A helper column to count unique bills/checkouts. |

---

## 📊 Step 3: KPI Selection & Dashboard Interactivity
We implemented 5 core Key Performance Indicators (KPIs) and 7 Visual Charts to provide a 360-degree view of the business:

### **Core KPIs**
* **Total Revenue:** $2.29M - Fundamental top-line growth metric.
* **Total Profit:** $286K - The "sanity" check for actual earnings.
* **Avg Profit Margin:** 12.4% - Efficiency metric calculated via Calculated Fields.
* **Average Order Value (AOV):** $458 - Calculated as `Total Sales / Unique Orders`.

### **Dynamic Interactivity**
* **Slicers:** Added `Order_Year`, `Category`, `Region`, `Profit_Status`, and `Segment`.
* **Report Connections:** All slicers were cross-connected to multiple Pivot Tables for a fully dynamic dashboard experience.

---

## 💡 Step 4: Key Insights & "Storytelling"

### **1. The Discount Trap (Strategic Failure)**
* **The Data:** Average Quantity without discount is **3.80**, while with a discount, it remains stagnant at **3.77**.
* **The Insight:** Flat discounts are failing to drive bulk buying; they are simply reducing margins on existing demand.

### **2. The "Table Sinkhole" & Toxic Customers**
* **The Data:** 20% of customers are "Toxic," causing a **$71,000 loss**.
* **The Insight:** These customers abuse discounts to buy heavy Furniture (specifically **Tables**), which caused a **-$17,725 loss** due to high logistics costs.

### **3. Operational Bottlenecks**
* **The Data:** The **Central Region** is the slowest, with a 4.05-day average shipping delay.
* **The Insight:** Slow logistics risk losing our 98.5% loyal customer base to faster competitors.

---

## 🚀 Step 5: Final Strategic Recommendations
* **Volume-Based Bundling:** Replace flat discounts with "Buy 3, Get 15% Off" to encourage bulk purchases.
* **Regional Price Caps:** Limit maximum discounts to **15%** in high-loss cities and states like Texas and Illinois.
* **Furniture Shipping Fees:** Stop free shipping on bulky items (Tables/Bookcases) and apply weight-based fees.
* **Logistics Optimization:** Audit the Central region's supply chain to reduce shipping SLAs to a maximum of 3 days.

---

## ⚠️ Assumptions & Limitations
* **Gross Sales Focus:** Returns and cancellations data was unavailable; analysis is based on gross sales.
* **Delivery Tracking:** Actual delivery dates were missing; we assume all "shipped" orders were fulfilled.
* **External Factors:** Sales fluctuations are assumed to be organic as external factors like weather or competitor actions were not provided.

---
**Team Members:** Kalpesh Drakshe ![Uploading Screenshot 2026-03-06 143941.png…]()
