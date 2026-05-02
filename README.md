# 🏦 UK Bank Customer Analysis Dashboard

> ⚠️ Disclaimer: This project uses a simulated dataset for demonstration purposes.

---

## 📌 Project Overview

This project analyzes bank customer data to uncover demographic patterns, financial behavior, and segmentation opportunities that support targeted marketing and product strategies.

The dashboard provides insights into:
- Customer distribution
- Financial behavior (balances)
- Demographic segmentation
- Potential high-value customer groups

---

## 🎯 Business Problem

Banks need to understand their customers to:

- Identify high-value customer segments  
- Personalize financial products  
- Improve customer retention  
- Increase profitability  

Without proper analysis, marketing and product strategies remain inefficient.

---

## 📊 Dataset Description

| Column       | Description |
|-------------|------------|
| Customer_ID | Unique identifier |
| Age         | Customer age |
| Gender      | Male/Female |
| Occupation  | Job category |
| Balance     | Account balance |

---

## 🧠 Data Preparation

Data was cleaned and structured to ensure:

- No missing demographic values  
- Consistent data types  
- Valid numerical balance values  

---

## 🧮 SQL Analysis (Exploration Layer)

SQL was used to explore customer patterns before visualization.

---

### 📌 Total Customers

```sql
SELECT COUNT(*) AS total_customers
FROM customers;
````

### Average Balance
```sql
SELECT AVG(Balance) AS avg_balance
FROM customers;
````

### Customers by gender
```sql
SELECT Gender, COUNT(*) AS total
FROM customers
GROUP BY Gender;
````

### Customers by occupation
```sql
SELECT Occupation, COUNT(*) AS total
FROM customers
GROUP BY Occupation
ORDER BY total DESC;
````

### Age segmentation
```sql
SELECT 
    CASE 
        WHEN Age < 30 THEN 'Under 30'
        WHEN Age BETWEEN 30 AND 50 THEN '30-50'
        ELSE '50+'
    END AS age_group,
    COUNT(*) AS total
FROM customers
GROUP BY age_group;
````
---

## 📊 DAX Measures (Power BI Layer)

DAX was used to build dynamic KPIs.
### Total Customers
```DAX
Total Customers = COUNT('Customers'[Customer_ID])
````

### Average Balance
```DAX
Avg Balance = AVERAGE('Customers'[Balance])
````

### 📌 Customer Segmentation
```DAX
Customer Segment =
SWITCH(
    TRUE(),
    'Customers'[Balance] > 7000, "High Value",
    'Customers'[Balance] > 4000, "Medium Value",
    "Low Value"
)
````

### Customers by Age Group
```DAX
Customers Age Group = COUNT('Customers'[Customer_ID])
````

---

## 📊 Dashboard Features

The Power BI dashboard includes:

- KPI Cards (Total Customers, Avg Balance)
- Bar Charts (Occupation distribution)
- Pie Chart (Gender split)
- Age segmentation analysis
- Customer balance insights

---

## 📸 Dashboard Preview

<p align="center"> <img src="images/uk_bank.png" width="48%" /> <img src="images/dashboard_1b.png" width="48%" /> </p> <p align="center"><em>Figure: Customer Demographics & Financial Distribution Dashboard</em></p>

---

## 🔍 Key Insights
- 👥 Majority of customers fall within the 31–50 age group
- ⚖️ Gender distribution is relatively balanced
- 💼 White-collar occupations dominate the customer base
- 💰 A small segment holds significantly higher balances

---

## 💡 Business Recommendations
- Target mid-age professionals (31–50) with premium banking products
- Develop youth-focused financial products for long-term acquisition
- Personalize offers for high-value customers
- Introduce loyalty programs to improve retention

---

## 🛠 Tools & Technologies
- Power BI (Visualization)
- SQL (Data exploration)
- DAX (KPI calculations)

---

## 📌 Project Outcome

This project demonstrates the ability to:

- Analyze customer demographics and financial behavior
- Use SQL for data exploration
- Build interactive dashboards
- Translate insights into business strategy

---

## 👤 Author

Emmanuel Adusu
Data Analyst | Power BI | SQL | Business Intelligence

📧 Email: adusue191@gmail.com

🌐 Portfolio: https://emmanuel-adusu.github.io/

