# 🛍️ Myntra Sales Analytics Dashboard — Power BI

![Power BI](https://img.shields.io/badge/PowerBI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Calculations-blue?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-Data%20Processing-green?style=for-the-badge)
![Data](https://img.shields.io/badge/Dataset-50K%20Records-orange?style=for-the-badge)

---

## 📌 Project Overview

An end-to-end **Sales Analytics Dashboard** built on 50,000 Myntra 
orders (Jan 2024 – Oct 2025) using Power BI.
The dashboard provides deep insights into revenue trends, brand 
performance, customer segmentation, product analysis, 
and Month-Over-Month (MOM) growth tracking.

---



---

## 📊 Key KPIs Tracked

| KPI | Value |
|-----|-------|
| 💰 Total Revenue | ₹ 4,58,97,715 |
| 🏷️ Total Discount | ₹ 2,93,29,400 (63.90%) |
| 💎 Value Retained | 61.16% |
| 👥 Total Customers | 30K |
| 👨 Total Mens | 14K |
| 👩 Total Womens | 11K |
| 🧑 Total Others | 5K |
| ⭐ Average Rating | 4.33 |

---

## 📈 Dashboard Features

### 1️⃣ KPI Cards
- Total Revenue with **MOM % change**
- Total Discount Amount & Discount %
- Value Retained % (Revenue after discount)
- Customer count split by Gender

### 2️⃣ Brand Performance
- Top brands by Revenue — Nike (10.7M), Levis (9.3M), Zara (9.2M)
- Total Reviews by Brand
- Average Rating per Brand

### 3️⃣ Product Analysis
- Top 10 products by Revenue
- Air Zoom Pegasus 39 leading at ₹3.0M

### 4️⃣ Category by Gender
- Men: 46.28% | Women: 35.72% | Unisex: 18.06%

### 5️⃣ Time Intelligence
- Month-Over-Month (MOM) Trend Line Chart
- Year & Month Slicers (2024 / 2025)
- MOM % Growth on all KPI cards

---

##  DAX Measures Used
```dax
-- Total Revenue
Total Revenue = SUM(MYNTRA_DATEA[SalePrice])

-- Last Month Revenue (MOM Fix without Date Table)
Last Month Revenue =
CALCULATE(
    [Total Revenue],
    FILTER(
        ALL(MYNTRA_DATEA),
        YEAR(MYNTRA_DATEA[OrderDate]) = 
            YEAR(EDATE(MAX(MYNTRA_DATEA[OrderDate]), -1))
        &&
        MONTH(MYNTRA_DATEA[OrderDate]) = 
            MONTH(EDATE(MAX(MYNTRA_DATEA[OrderDate]), -1))
    )
)

-- MOM % Revenue
MOM % Revenue =
DIVIDE(
    [Total Revenue] - [Last Month Revenue],
    [Last Month Revenue], 0
) * 100
```

---

##  Dataset Details

| Field | Description |
|-------|-------------|
| OrderID | Unique Order Identifier |
| BrandName | Brand (Nike, Zara, Levis, etc.) |
| ProductName | Product Name |
| Category | Men / Women / Unisex |
| OriginalPrice | MRP in ₹ |
| SalePrice | Discounted Price in ₹ |
| DiscountPercent | % Discount Applied |
| Size | Product Size |
| Color | Product Color |
| Rating | Customer Rating (1–5) |
| NoOfReviews | Number of Reviews |
| OrderDate | Date of Order (Jan 2024 – Oct 2025) |

---

## 🛠️ Tools & Technologies

| Tool | Usage |
|------|-------|
| **Power BI Desktop** | Dashboard & Visualizations |
| **DAX** | KPI Measures & Time Intelligence |
| **Python (Pandas)** | Data Preprocessing & MOM Excel Export |
| **Excel** | MOM Analysis Output |
| **CSV (50K rows)** | Raw Dataset |

---

## 📁 Project Structure
```
📦 Myntra-Sales-Dashboard
 ┣ 📂 Dataset
 ┃ ┗ 📜 myntra_sale_products_50k.csv
 ┣ 📂 PowerBI
 ┃ ┗ 📜 Myntra_Dashboard.pbix
 ┣ 📂 Excel
 ┃ ┗ 📜 Myntra_MOM_Analysis.xlsx
 ┣ 📂 Screenshots
 ┃ ┗ 📜 dashboard_preview.png
 ┣ 📜 README.md
```

---

##  How to Run

1. Clone this repository
```bash
   git clone https://github.com/yourusername/Myntra-Sales-Dashboard.git
```
2. Open `Myntra_Dashboard.pbix` in **Power BI Desktop**
3. Update the data source path to your local CSV file
4. Refresh the data — all visuals will load automatically ✅

---

## 💡 Key Insights

-  **Revenue grew 252%** from Jan 2024 to Sep 2025
- **Nike** is the top brand with ₹10.7M in revenue
-  **Women's category** is the fastest growing segment
-  **Air Zoom Pegasus 39** is the best-selling product
-  Average customer rating is consistently **4.33/5**
-  **MOM growth peaked in Mar 2024** at +29%

---

##  Author

> Made with  using Power BI & Python

---

## ⭐ If you found this useful, give it a Star!
