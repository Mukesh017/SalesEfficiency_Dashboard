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
---

### 7️⃣📸 Reports Preview

Below are the visuals from all dashboard pages.

Below are the visuals from all report pages included in the Power BI dashboard.

📄 Page 1
<img width="1918" height="840" alt="ReportPage 1" src="https://github.com/user-attachments/assets/39bbc03f-02be-42d7-8ca2-f46f8419406c" />

📄 Page 2   
<img width="1919" height="840" alt="ReportPage 2" src="https://github.com/user-attachments/assets/c3e0845b-acbf-4af0-8f10-3dc7d1b8aed3" />

📄 Page 3   
<img width="1919" height="843" alt="ReportPage 3" src="https://github.com/user-attachments/assets/8b3ea2e9-7386-44de-baed-5d95948a5127" />

📄 Page 4
<img width="1919" height="841" alt="ReportPage 4" src="https://github.com/user-attachments/assets/a2c053ac-4f8b-41aa-988f-11be0f76dbc3" />

📄 Page 5
<img width="1919" height="845" alt="ReportPage 5" src="https://github.com/user-attachments/assets/68cbde3a-8779-465f-8b4e-9130334098aa" />

📄 Page 6
<img width="1919" height="841" alt="ReportPage 6" src="https://github.com/user-attachments/assets/1098d3d2-7af0-4dee-88c0-432ec24952cc" />

📄 Page 7
<img width="1919" height="844" alt="ReportPage 7" src="https://github.com/user-attachments/assets/613ee07e-b76b-47b3-9cf8-d3b906e2abde" />

📄 Page 8
<img width="1919" height="842" alt="ReportPage 8" src="https://github.com/user-attachments/assets/66e7fcbe-3890-40df-9bd1-36023242e797" />
