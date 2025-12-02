# SalesEfficiency_Dashboard
Power BI Data Analytics Project | End-to-End Workflow — Data Cleaning, EDA, SQL Modelling, DAX Measures, and Interactive Dashboard


# Power BI Sales Analytics Dashboard  
End-to-end Data Analytics Project using Python, SQL, DAX & Power BI

---

## 📊 Project Overview
This project demonstrates a complete analytics pipeline—from raw data to an interactive business dashboard.  
The goal is to help business teams monitor **sales performance, revenue trends, returns, customer behavior**, and **profitability across cities, categories, regions, and seasons**.

The dashboard is built using real-world workflow steps: Data Cleaning → EDA → SQL Modelling → DAX → Power BI Reporting.

---

## 🚀 Key Features
- Interactive Power BI Dashboard (4 pages)
- Auto-rotating KPI visual (Profit per City)
- Fully cleaned dataset using Python
- SQL-based transformations & data modelling
- DAX measures for KPIs and advanced calculations
- Slicers with custom UI (rounded tiles)
- Trend analysis, category-level performance & return analysis
- Scatter plots for price–profit & quantity–profit patterns

---

## 🧱 Tech Stack
- **Python** (pandas, numpy, matplotlib, seaborn)
- **SQL** (MySQL / PostgreSQL)
- **Power BI Desktop & Power BI Service**
- **DAX**
- **Jupyter Notebook**

---

## 🗂️ Workflow & Steps

### 1️⃣ Data Collection  
Datasets were imported into Jupyter Notebook for initial exploration and cleaning.

### 2️⃣ Data Cleaning & Preparation (Python)
Performed using pandas:
- Handling missing values  
- Converting datatypes  
- Outlier Winsorization  
- Feature extraction (Season, Month, Year)  
- Removing duplicates  
- Standardizing categorical fields  

Final cleaned dataset stored under  
`/data/cleaned/`

---

### 3️⃣ Exploratory Data Analysis (EDA)
EDA Notebook: `notebooks/eda.ipynb`

Key insights:
- Sales trend by month  
- Category-level contribution  
- High-return products  
- Profitability distribution  
- Outlier behavior & skewness  
- Seasonality patterns  

Visuals generated using Matplotlib & Seaborn.

---

### 4️⃣ SQL Analysis & Modelling  
File: `sql/analysis_queries.sql`

Included:
- Fact & Dimension model creation  
- Joins for category-region mapping  
- Aggregations by city, category, season  
- Business-level calculated tables  

---

### 5️⃣ Power BI Data Modelling
Model consists of:
- **FactSales table**
- **DimCity**
- **DimCategory**
- **DimProduct**
- **DimDate**
- **DimRegion**

Relationships built using Star Schema.

---

### 6️⃣ DAX Measures (partial list)
File: `DAX/measures.txt`

Examples:
```DAX
Total Sales = SUM(FactSales[Sales])
Total Profit = SUM(FactSales[Profit])
AOV = [Total Sales] / DISTINCTCOUNT(FactSales[OrderID])

Profit Per City Dynamic = 
VAR SelStep = SELECTEDVALUE(CityRotation[Step])
VAR SelectedCity =
    SWITCH(
        SelStep,
        1, "Chennai",
        2, "Bangalore",
        3, "Delhi",
        4, "Mumbai"
    )
RETURN
CALCULATE([Total Profit], DimCity[City] = SelectedCity)
