# Sales Performance Dashboard

**Dashboard Link:**  
https://app.powerbi.com/view?r=eyJrIjoiMjVjMjQxNTItMmRkMy00ZDEwLWJkZjktOGJlNjdlYTAzMjFkIiwidCI6IjZiNGQwNDQ4LTc5MGMtNGQ5MS1iZjY3LTg5ZDk1NmJlNDEwYSJ9

## Problem Statement

The objective of this dashboard is to provide actionable insights into sales performance, enabling businesses to:

- Identify **best** and **worst-performing** products.
- Analyze **sales trends** over multiple time periods (daily, monthly, quarterly, annually).
- Compare performance between any two **user-selected periods**.
- Understand the relationship between **sales** and **profit**.
- Track **discounts** and their effect on sales.
- Monitor **orders** and performance across cities, customers, and products.

This report provides both high-level KPIs and transaction-level drill-downs, making it suitable for **strategic** as well as **operational** decision-making.

---

## Business Requirements

1. **Top/Bottom 5 Products** by Sales, Profit, and Quantity Sold.
2. **Sales Trends** Over Time (daily, monthly, quarterly, annually).
3. **Sales vs Profit Relationship** (scatter plot).
4. **Period Comparison** – Sales/Profit/Quantity Sold between two user-selected periods.
5. **Average Discount** offered across discount categories.
6. **Total Orders** placed.
7. **Detailed Order View** – Sales, Profit, Discount, Net Sales, and other fields, filterable by:
   - Product
   - Date
   - Customer ID
   - Promotion Category
8. **City-Wise Sales Distribution**.

---

## Steps Followed

### 1. Data Preparation
- Loaded **raw sales dataset** into Power BI Desktop.
- Conducted **Data Profiling** in Power Query (checked column quality, null values, data distribution).
- Performed **Data Transformations**:
  - Removed duplicates and nulls.
  - Standardized column names.
  - Corrected data types.
  - Created **calculated fields** for better analysis.

### 2. Data Modeling
- Created **Star Schema** with Fact
# Sales Performance Dashboard

**Dashboard Link:**  
[Add Power BI Service link here]

## Problem Statement

The objective of this dashboard is to provide actionable insights into sales performance, enabling businesses to:

- Identify **best** and **worst-performing** products.
- Analyze **sales trends** over multiple time periods (daily, monthly, quarterly, annually).
- Compare performance between any two **user-selected periods**.
- Understand the relationship between **sales** and **profit**.
- Track **discounts** and their effect on sales.
- Monitor **orders** and performance across cities, customers, and products.

This report provides both high-level KPIs and transaction-level drill-downs, making it suitable for **strategic** as well as **operational** decision-making.

---

## Business Requirements

1. **Top/Bottom 5 Products** by Sales, Profit, and Quantity Sold.
2. **Sales Trends** Over Time (daily, monthly, quarterly, annually).
3. **Sales vs Profit Relationship** (scatter plot).
4. **Period Comparison** – Sales/Profit/Quantity Sold between two user-selected periods.
5. **Average Discount** offered across discount categories.
6. **Total Orders** placed.
7. **Detailed Order View** – Sales, Profit, Discount, Net Sales, and other fields, filterable by:
   - Product
   - Date
   - Customer ID
   - Promotion Category
8. **City-Wise Sales Distribution**.

---

## Steps Followed

### 1. Data Preparation
- Loaded **raw sales dataset** into Power BI Desktop.
- Conducted **Data Profiling** in Power Query (checked column quality, null values, data distribution).
- Performed **Data Transformations**:
  - Removed duplicates and nulls.
  - Standardized column names.
  - Corrected data types.
  - Created **calculated fields** for better analysis.

### 2. Data Modeling
- Created **Star Schema** with Fact and Dimension tables.
- Defined **Primary** and **Foreign Keys** for relationships.
- Managed **Cardinality** to ensure correct joins.
- Built **Date Table** for time intelligence.
- Created **two Date Tables** (Date Table 1 & Date Table 2) to allow period comparisons.

### 3. DAX Measures
Key measures created include:

- **Total Profit**:
    ```DAX
    Total Profit = 
    CALCULATE(
        SUM('Fact Table'[Net Sales]),
        ALL('Date Table 1'),
        USERELATIONSHIP('Date Table 2'[Date], 'Fact Table'[Date (dd/mm/yyyy)])
    )
    ```

- **Sum of Net Sales**:
    ```DAX
    Sum of Net Sales = 
    CALCULATE(
        SUM('Fact Table'[Net Sales]),
        ALL('Date Table 1'),
        USERELATIONSHIP('Date Table 2'[Date], 'Fact Table'[Date (dd/mm/yyyy)])
    )
    ```

- **Quantity Sold**:
    ```DAX
    Quantity Sold = 
    CALCULATE(
        SUM('Fact Table'[Units Sold]),
        ALL('Date Table 1'),
        USERELATIONSHIP('Date Table 2'[Date], 'Fact Table'[Date (dd/mm/yyyy)])
    )
    ```

Other supporting measures were created for:
- **Total Sales**
- **Total Orders**
- **Average Discount**

### 4. Visualizations Implemented
- **KPI Cards** → Total Orders, Sales, Profit, Quantity Sold.
- **Bar Charts** → Top/Bottom 5 Products by Sales, Profit, Quantity.
- **Line Chart** → Sales Trends (daily, monthly, quarterly, annually).
- **Scatter Plot** → Profit vs. Sales.
- **Comparison Visuals** → Sales/Profit/Quantity comparison between two user-selected periods.
- **Map Visual** → Sales distribution by city.
- **Table** → Order-level details with filters for product, customer, promotion, and date.
- **Slicers/Filters** → Product, Customer ID, Date Range, Promotion Category.

### 5. Report Design
- Applied **theme** and **formatting** for consistency.
- Used **Edit Interactions** to control slicer behavior.
- Changed **filter behavior** for dimension tables to maintain accuracy.
- Published final report to **Power BI Service** for sharing.

---

## Key Insights

- **Orders:** 3,510 total orders processed.
- **Top Products:** Certain products contributed heavily to sales and profit, while bottom products require strategy changes.
- **Sales Trends:** Seasonal patterns observed with visible peaks during specific periods.
- **Profitability:** Profit grows consistently with sales, confirming healthy margins.
- **Discounts:** Average discount tracked per category to evaluate impact.
- **Regional Sales:** City-level sales distribution highlights key revenue zones.
- **Period Comparison:** Business users can compare two time periods (e.g., Q1 vs Q2) for sales, profit, and quantity sold.

---

## Snapshots

Here are snapshots of the Power BI dashboard, showcasing different views and analyses:

1. **Dashboard-Overview**  
   ![Dashboard-Overview](https://raw.githubusercontent.com/ShouryaSrivastav/Power-Bi-Project-1/main/assets/1000004261.png)

2. **Top-Bottom-Products-Analysis**  
   ![Top-Bottom-Products-Analysis](https://raw.githubusercontent.com/ShouryaSrivastav/Power-Bi-Project-1/main/assets/1000004262.png)

3. **Sales/Profit/Quantity Between Time Period**  
   ![Sales/Profit/Quantity Between Time Period](https://raw.githubusercontent.com/ShouryaSrivastav/Power-Bi-Project-1/main/assets/1000004264.png)

4. **Sales and Performance Comparison Dashboard**  
   ![Sales and Performance Comparison Dashboard](https://raw.githubusercontent.com/ShouryaSrivastav/Power-Bi-Project-1/main/assets/1000004263.png)

5. **Order-Level Details (Table View)**  
   ![Order-Level Details (Table View)](https://raw.githubusercontent.com/ShouryaSrivastav/Power-Bi-Project-1/main/assets/1000004265.png)

---

## Conclusion

This **Sales Performance Dashboard** provides a 360° view of business performance with:

- Top/Bottom product insights.
- Sales trends and seasonality.
- Discount impact measurement.
- Regional and product-level drill-downs.
- Interactive period comparisons for trend validation.

It helps business leaders and analysts make data-driven decisions, optimize product strategies, and improve profitability.

---

