# BANK-ANALYSIS

---

# 🔷 🏦 PROJECT 3 — BANK ANALYSIS (UPGRADED)


# 🏦 UK Bank Customer Analysis

> ⚠️ Simulated dataset.

---

## 📌 Overview

Customer segmentation analysis to support targeted banking strategies.

---

## 🎯 Business Problem

Banks need to:
- Understand customer demographics  
- Improve product targeting  
- Increase retention  

---

## 📊 Dataset

| Column      | Description |
|-------------|------------|
| Customer_ID | Unique ID |
| Age         | Customer age |
| Gender      | Gender |
| Occupation  | Job type |
| Balance     | Account balance |

---

## 🧮 SQL Analysis

### Total Customers
```sql
SELECT COUNT(*) FROM customers;
````

### Average Balance
```sql
SELECT AVG(Balance) FROM customers;
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

## 📊 KPIs & DAX Measures

### Total Customers
```DAX
Total Customers = COUNT('Customers'[Customer_ID])
````

### Average Balance
```DAX
Avg Balance = AVERAGE('Customers'[Balance])
````

### Customers by Age Group
```DAX
Customers Age Group = COUNT('Customers'[Customer_ID])
````

---

## 📊 Visuals
- Pie Chart (Gender Distribution)
- Bar Chart (Age Groups)
- Table (Customer Details)

---

 📸 Dashboard


---

## 🔍 Insights
- Majority of customers aged 31–50
- Balanced gender distribution
- White-collar segment dominates

---

## 💡 Recommendations
- Target mid-age professionals
- Develop youth-focused products
- Personalize offerings

---

## 🛠 Tools

Power BI



