# eda-vendor-performance-analysis-sql-python-powerbi
<h1 align="center"> Vendor Performance & Inventory Analysis EDA 📊 </h1>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" />
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white" />
  <img src="https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black" />
</p>

<p align="center">
  <b>A comprehensive data analysis project aimed at optimizing product pricing, improving vendor selection, and enhancing inventory efficiency.</b>
</p>

---

## 📑 Table of Contents
- [Project Overview](#-project-overview)
- [Objectives](#-objectives)
- [Dashboard](#-dashboard)
- [Data Pipeline & Architecture](#-data-pipeline--architecture)
- [Key Performance Indicators (KPIs)](#-key-performance-indicators-kpis)
- [Key Insights & Findings](#-key-insights--findings)
- [Recommendations](#-recommendations)
- [How to Run the Project](#-how-to-run-the-project)
- [Contacts](#-contacts)

---

## 📝 Project Overview
This project focuses on Exploratory Data Analysis (EDA) of vendor performance, inventory management, and sales transactions. By aggregating fragmented data across purchase, sales, and invoice systems, the analysis uncovers insights into supply chain risks, inventory turnover inefficiencies, and margin optimization opportunities.

## 🎯 Objectives
* **Vendor Selection for Profitability:** Identify top and low-performing vendors to restructure partnerships and minimize supply chain risks.
* **Product Pricing Optimization:** Discover brands with high margins but low sales volume that could benefit from promotional pricing.
* **Inventory Efficiency:** Identify slow-moving inventory and the financial impact of unsold stock.

---

## 🖥️ Dashboard
*(Insert your Power BI or visualization dashboard screenshot below)*

![Dashboard Screenshot](replace-this-with-your-dashboard-image-link-or-path.png)

---

## 🗄️ Data Pipeline & Architecture
The project utilizes a local SQLite database (`inventory.db`) to store and aggregate data efficiently. 
1. **Raw Data Ingestion (`ingestion_db.py`):** Reads raw CSV files (inventories, purchases, sales, invoices) and loads them into the SQLite database.
2. **Data Aggregation & Cleaning (`get_vendor_summary.py`):** Executes complex SQL joins to merge `purchases`, `sales`, `purchase_prices`, and `vendor_invoice` tables. It calculates key business metrics and handles missing/inconsistent data.
3. **Exploratory Analysis (`Exploratory Data Analysis.ipynb`):** Jupyter Notebook used for initial data exploration, table profiling, and validation of the data merging logic.
4. **Dashboarding (Power BI):** The final cleaned dataset (`vendor_sales_summary.csv`) is imported into Power BI for visual reporting.

---

## 📊 Key Performance Indicators (KPIs)
To enhance the reliability of the insights, inconsistent data records (e.g., negative profit margins, zero sales quantities) were filtered out. The following metrics were engineered for deeper analysis:
* **Gross Profit:** `TotalSalesDollars - TotalPurchaseDollars`
* **Profit Margin (%):** `(GrossProfit / TotalSalesDollars) * 100`
* **Stock Turnover:** `TotalSalesQuantity / TotalPurchaseQuantity`
* **Sales to Purchase Ratio:** `TotalSalesDollars / TotalPurchaseDollars`

---

## 💡 Key Insights & Findings

### 1. Brands for Promotional or Pricing Adjustments
* **Insight:** 198 brands exhibit low sales but maintain exceptionally high profit margins (e.g., *Santa Rita Organic Svgn Bl*, *Crown Royal Apple*).
* **Impact:** These products are prime candidates for targeted marketing, promotions, or price optimizations to drive volume without compromising overall profitability.

### 2. Supply Chain Risk: Vendor Over-reliance
* **Insight:** The top 10 vendors (led by *Diageo North America* and *Martignetti Companies*) contribute **65.69%** of total purchases, while the remaining vendors make up only 34.31%.
* **Impact:** This heavy reliance on a few key suppliers introduces significant supply chain vulnerability if disruptions occur.

### 3. The Power of Bulk Purchasing
* **Insight:** Vendors buying in large quantities receive a **72% lower unit cost** ($10.78 per unit vs $39.
