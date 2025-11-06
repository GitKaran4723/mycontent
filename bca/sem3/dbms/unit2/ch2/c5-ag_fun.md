## ---

# **🧮 SQL Aggregate Functions**

### **Definition:**

## SQL Aggregate Functions are **used to perform calculations on a set of rows** and return a **single summarized value**.  They are often used with the **GROUP BY** clause to group rows that have the same values in specified columns, enabling aggregate calculations for each group.

## ---

## **🌟 Key Features of Aggregate Functions**

* ## **Operate on multiple rows** of a table and return one result per group. 

* ## **Ignore NULL values** (except for `COUNT(*)`). 

* ## **Used with `GROUP BY`** to group data for analysis. 

* ## **Can be combined** with clauses like `HAVING`, `ORDER BY`, and `WHERE`. 

## ---

## 

## 

## 

## 

## **📘 Common SQL Aggregate Functions**

| Function | Description | Syntax | Example | Result / Use |
| ----- | ----- | ----- | ----- | ----- |
| **COUNT()** | Counts the number of rows or non-NULL values in a column. | `COUNT(column_name)` | `SELECT COUNT(Salary) AS TotalEmployees FROM Employee;` | Returns total number of employees having salary value. |
| **SUM()** | Calculates the total sum of a numeric column. | `SUM(column_name)` | `SELECT SUM(Salary) AS TotalSalary FROM Employee;` | Returns total salary of all employees. |
| **AVG()** | Returns the average (mean) value of a numeric column. | `AVG(column_name)` | `SELECT AVG(Salary) AS AvgSalary FROM Employee;` | Returns average salary of employees. |
| **MIN()** | Returns the smallest value from a column. | `MIN(column_name)` | `SELECT MIN(Salary) AS LowestSalary FROM Employee;` | Returns the minimum salary. |
| **MAX()** | Returns the largest value from a column. | `MAX(column_name)` | `SELECT MAX(Salary) AS HighestSalary FROM Employee;` | Returns the maximum salary. |

## ---

## **🧠 Detailed Explanation with Examples**

### **1️⃣ COUNT()**

* ## **Purpose:** Counts rows in a table or non-NULL values in a column. 

* ## **Types:** 

  * ## `COUNT(*)` → Counts all rows, including NULLs. 

  * ## `COUNT(column_name)` → Counts only non-NULL values. 

  * ## `COUNT(DISTINCT column_name)` → Counts unique, non-NULL values. 

## **Example:**

## SELECT COUNT(\*) AS TotalEmployees FROM Employee;

## SELECT COUNT(Salary) AS NonNullSalaries FROM Employee;

## SELECT COUNT(DISTINCT Department) AS uniquedept FROM Employee;

## 

## ---

### 

### **2️⃣ SUM()**

* ## **Purpose:** Calculates the total of all numeric values in a column. 

* ## **Ignores** NULL values. 

## **Example:**

## SELECT SUM(Salary) AS TotalSalary FROM Employee;

## SELECT SUM(DISTINCT Salary) AS UniqueSalarySum FROM Employee;

## 

## ---

### **3️⃣ AVG()**

* ## **Purpose:** Returns the average of numeric values. 

* ## **Formula:** `AVG = SUM(column)/COUNT(column)` (excluding NULLs). 

## **Example:**

## SELECT AVG(Salary) AS AverageSalary FROM Employee;

## SELECT AVG(DISTINCT Salary) AS DistinctAvgSalary FROM Employee;

## 

## ---

### 

### 

### 

### 

### **4️⃣ MIN() and MAX()**

* ## **Purpose:** 

  * ## `MIN()` → Finds the smallest value. 

  * ## `MAX()` → Finds the largest value. 

## **Example:**

## SELECT MIN(Salary) AS LowestSalary FROM Employee;

## SELECT MAX(Salary) AS HighestSalary FROM Employee;

## 

## ---

## **🧩 Using Aggregate Functions with GROUP BY**

## **Example:**

## SELECT Department, COUNT(\*) AS EmpCount, AVG(Salary) AS AvgSalary

## FROM Employee

## GROUP BY Department;

## 

## 

## 

## 

## 

## 

## 

## **Output:**

| Department | EmpCount | AvgSalary |
| ----- | ----- | ----- |
| HR | 3 | 52000 |
| IT | 4 | 70000 |
| Sales | 2 | 60000 |

## ---

## **✅ Advantages of Aggregate Functions**

* ## Simplify **data analysis** by summarizing large datasets. 

* ## Enable **report generation** (e.g., total sales, average salary). 

* ## Improve **data-driven decision-making**. 

* ## Work efficiently with **GROUP BY** and **HAVING** clauses. 

## ---

## **❌ Disadvantages / Limitations**

* ## Cannot be used to return **individual row details**. 

* ## **NULL values** are ignored (except `COUNT(*)`), which may cause data inaccuracies. 

* ## Cannot be applied directly to **non-numeric columns** (except `COUNT()`). 

* ## When used with large datasets, may **impact performance**. 

## 