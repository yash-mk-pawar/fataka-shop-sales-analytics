# 🎇 Fataka Shop Sales & Inventory Analytics Pipeline (5-Year Hybrid Data System)

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Engineering-orange.svg)](https://pandas.pydata.org/)
[![SQLite](https://img.shields.io/badge/SQLite-Relational%20DB-lightgrey.svg)](https://www.sqlite.org/)
[![Power BI](https://img.shields.io/badge/Power%20BI-Executive%20Dashboard-yellow.svg)](https://powerbi.microsoft.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

---

## 📌 Project Overview
An end-to-end data engineering, exploratory data analysis (EDA), and predictive inventory optimization system built for a seasonal firecracker (Fataka) retail business. 

The project simulates a highly realistic business challenge: handling a **5-year data lifecycle** where the shop owner operated using manual paper logbooks for the first 3 years (stored in CSV files) and transitioned to a modern relational database management system for the subsequent 2 years (stored in an SQLite database). 

This repository houses a modular Python pipeline that unites these hybrid data streams, uncovers seasonal buying velocity curves relative to Diwali ($D-Day$), performs ABC inventory segmentation, and generates an automated stock optimization action plan for future festival planning.

---

## 🏗️ Project Architecture & Directory Structure

```text
Fataka Sales/
│
├── Dataset/
│   ├── diwali_sales_year_1.csv         # Year 1 Manual Logbook (CSV)
│   ├── diwali_sales_year_2.csv         # Year 2 Manual Logbook (CSV)
│   ├── diwali_sales_year_3.csv         # Year 3 Manual Logbook (CSV)
│   ├── fataka_sales.db                 # SQLite Database (Years 4 & 5 Tables)
│   ├── master_fataka_sales.csv         # Unified 5-Year Master Output
│   ├── inventory_action_plan.csv       # Predictive Stock Optimization Matrix
│   ├── revenue_by_category.png         # EDA Visualization Chart
│   └── diwali_demand_velocity.png      # Pre-Diwali Demand Surge Curve Chart
│
├── Notebooks/                          # Modular Jupyter Notebooks
│   ├── 01_ETL_Pipeline.ipynb           # Ingestion, Database connection & Union Layer
│   ├── 02_EDA_Analysis.ipynb           # Statistical metrics, ABC analysis & visual charts
│   └── 03_Inventory_Forecast.ipynb     # Predictive demand modeling & stock recommendations
│
└── README.md                           # Project Documentation
```

---

## ⚙️ Key Technical Features

### 1. Hybrid ETL Data Pipeline (`01_ETL_Pipeline.ipynb`)
* **Multi-Source Ingestion:** Simultaneously ingests semi-structured historical CSV logbooks and queries relational SQLite tables (`transactions_year_4`, `transactions_year_5`).
* **Schema Normalization & Union:** Standardizes column headers, handles data types, cleans missing values, and merges 20,000 transaction records into a single cohesive time-series dataset.

### 2. Exploratory Data Analysis & Segmentation (`02_EDA_Analysis.ipynb`)
* **Macro Metrics Tracking:** Analyzes total 5-year cumulative revenue (~₹3.08 Crores) and sales velocity across 21 distinct firecracker products.
* **ABC Product Segmentation:** Applies the Pareto Principle (70/20/10 rule) to segment inventory into Hero Items (Class A), Moderate Sellers (Class B), and Low-Velocity Laggards (Class C).
* **Festive Velocity Mapping:** Tracks sales curves relative to **Days to Diwali ($D-Day$)**, proving that over 65% of festival revenue concentrates in the final 7-to-10-day pre-festival window.

### 3. Predictive Inventory Optimization Model (`03_Inventory_Forecast.ipynb`)
* **YoY Trend Projection:** Evaluates Year-over-Year growth rates across recent operating cycles.
* **Stock Recommendation Matrix:** Automatically assigns prescriptive operational actions (`Increase Stock (+15%)`, `Maintain Stock`, or `Reduce Stock (-15%)`) based on demand velocity.
* **Capital Allocation:** Estimates required wholesale procurement budgets (assuming wholesale cost is 60% of retail price) inclusive of a 10% safety buffer stock.

---

## 📊 Power BI Dashboard Integration
The generated outputs (`master_fataka_sales.csv` and `inventory_action_plan.csv`) connect directly into Power BI structured around a **Star Schema**:
* **Page 1: Executive Overview** — High-level KPI cards (Total Revenue, Units Sold) and annual growth trends.
* **Page 2: Product & Seasonality Deep Dive** — Category performance breakdowns and pre-Diwali demand surge curves.
* **Page 3: Operational Stock Action Plan** — Interactive matrix table guiding the shop owner on exact reorder quantities and capital investments for next year.

---

## 🚀 Getting Started & Replication

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yash-mk-pawar/fataka-shop-sales-analytics.git
   cd fataka-shop-sales-analytics
   ```

2. **Install dependencies:**
   ```bash
   pip install pandas numpy matplotlib seaborn sqlite3
   ```

3. **Run the Notebooks:**
   Open the notebooks in your preferred environment (`Jupyter Lab`, `VS Code Jupyter extension`, etc.) and run them sequentially (`01` -> `02` -> `03`) to process the raw datasets and generate analytical charts and action plans.

---

## 👤 Author
**Yash MK Pawar**
* GitHub: [@yash-mk-pawar](https://github.com/yash-mk-pawar)