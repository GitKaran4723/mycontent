# **🧠 Predicates in SQL**

A **predicate** is a logical condition used in SQL statements (especially in `WHERE`, `HAVING`, or `JOIN` clauses) that returns **TRUE**, **FALSE**, or **UNKNOWN** for each row.  
 They are essential for filtering, searching, and defining rules in queries.

---

## **🔍 1️⃣ LIKE Predicate**

Used to find rows where a column matches a pattern using **wildcards**:

* `%` → any sequence of characters

* `_` → a single character

 **Example:**

> SELECT emp\_name, emp\_city  
FROM Employee  
WHERE emp\_name LIKE 'A%';

✅ **Output:**

| emp\_name | emp\_city |
| ----- | ----- |
| Asha | Allahabad |

📝 **Explanation:**  
 Finds all employee names starting with **‘A’**.

---

### **Example 2:**

>SELECT emp\_name FROM Employee WHERE emp\_name LIKE '%a';

✅ **Output:**

| emp\_name |
| ----- |
| Meena |
| Priya |

📝 **Explanation:**  
 Finds names **ending with ‘a’**.

---

### **Example 3:**

>SELECT emp\_name FROM Employee WHERE emp\_name LIKE '\_a%';

✅ **Output:**

| emp\_name |
| ----- |
| Rahul |
| Asha |

📝 **Explanation:**  
 The **second character** in their names is **‘a’**.

---

## **📊 2️⃣ BETWEEN Predicate**

Used to select values within a range — **inclusive** of both ends.

### **Example:**

SELECT emp\_name, emp\_salary  
FROM Employee  
WHERE emp\_salary BETWEEN 40000 AND 50000;

✅ **Output:**

| emp\_name | emp\_salary |
| ----- | ----- |
| Rahul | 42000 |
| Priya | 45000 |

📝 **Explanation:**  
 Shows employees whose salary is between **₹40,000 and ₹50,000**.

---

## **🧩 3️⃣ DISTINCT Predicate**

Removes duplicate values in the result set.

### **Example 1:**

>SELECT DISTINCT emp\_country FROM Employee;

✅ **Output:**

| emp\_country |
| ----- |
| India |
| UK |

📝 **Explanation:**  
 Only **unique countries** appear.

---

### **Example 2:**

>SELECT DISTINCT emp\_country, emp\_city FROM Employee;

✅ **Output:**

| emp\_country | emp\_city |
| ----- | ----- |
| India | Allahabad |
| India | Patna |
| India | Varanasi |
| UK | London |
| India | Pune |

📝 **Explanation:**  
 Even if the country repeats, the **city combination** makes rows distinct.

---

## **🏷 4️⃣ ALIAS (as helper for readability)**

Temporary name for columns or tables to make results clearer.

### **Example 1 – Column Alias:**

> SELECT emp\_name AS "Employee Name", emp\_salary AS "Monthly Salary"  
FROM Employee;

✅ **Output:**

| Employee Name | Monthly Salary |
| ----- | ----- |
| Asha | 35000 |
| Rahul | 42000 |
| Meena | 39000 |
| John | 55000 |
| Priya | 45000 |

---

### **Example 2 – Table Alias:**

> SELECT e.emp\_name, e.emp\_country  
FROM Employee AS e;

✅ **Output:**  
 (Same as original but query looks cleaner)

---

## **🧮 5️⃣ GROUP BY**

Groups rows that have the same values in a column — often used with aggregate functions.

### **Example:**

> SELECT emp\_country, COUNT(\*) AS TotalEmployees  
FROM Employee  
GROUP BY emp\_country;

✅ **Output:**

| emp\_country | TotalEmployees |
| ----- | ----- |
| India | 4 |
| UK | 1 |

📝 **Explanation:**  
 Groups all employees by country and counts each.

---

## **⚙️ 6️⃣ HAVING**

Filters results **after grouping** (unlike WHERE which filters before).

### 

### 

### **Example:**

> SELECT emp\_country, SUM(emp\_salary) AS TotalSalary  
FROM Employee  
GROUP BY emp\_country  
HAVING SUM(emp\_salary) \> 150000;

✅ **Output:**

| emp\_country | TotalSalary |
| ----- | ----- |
| India | 161000 |

📝 **Explanation:**  
 Only countries whose total salary exceeds ₹150,000 appear.

---

## **🔢 7️⃣ ORDER BY**

Used to **sort results** (ASC \= ascending by default, DESC \= descending).

### **Example:**
> SELECT emp\_name, emp\_salary  
FROM Employee  
ORDER BY emp\_salary DESC;

✅ **Output:**

| emp\_name | emp\_salary |
| ----- | ----- |
| John | 55000 |
| Priya | 45000 |
| Rahul | 42000 |
| Meena | 39000 |
| Asha | 35000 |

📝 **Explanation:**  
 Sorted by salary, **highest to lowest**.

---

## **⏳ 8️⃣ LIMIT / TOP**

Used to restrict how many rows appear.

### **Example (MySQL):**
> SELECT emp\_name, emp\_salary  
FROM Employee  
ORDER BY emp\_salary DESC  
LIMIT 3;

✅ **Output:**

| emp\_name | emp\_salary |
| ----- | ----- |
| John | 55000 |
| Priya | 45000 |
| Rahul | 42000 |

📝 **Explanation:**  
 Displays **only the top 3 highest-paid** employees.

## **✅ Summary:**

| Predicate | Purpose | Example | Result Type |
| ----- | ----- | ----- | ----- |
| LIKE | Pattern match | `LIKE 'A%'` | Rows matching pattern |
| BETWEEN | Range filter | `BETWEEN 30000 AND 50000` | Rows in range |
| DISTINCT | Removes duplicates | `SELECT DISTINCT country` | Unique rows |
| ALIAS | Temporary name | `AS "Name"` | Renamed column/table |
| GROUP BY | Grouping rows | `GROUP BY country` | Aggregate results |
| HAVING | Group filter | `HAVING SUM(salary)>100000` | Filtered groups |
| ORDER BY | Sorting | `ORDER BY salary DESC` | Sorted output |
| LIMIT | Row restriction | `LIMIT 5` | Restricted output |

---

