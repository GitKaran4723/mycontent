# **📚 UNIT II – Relational Algebra, SQL, and Database Design**



## **🔶 Relational Algebra and Calculus**

### **🔹 Introduction to Relational Algebra**

A procedural query language that uses operations on relations to produce new relations.

### **🔹 Operations in Relational Algebra**

* **Selection (σ)**: Filters rows based on a condition  
* **Projection (π)**: Selects specific columns  
* **Set Operations**: Union, Intersection, Difference  
* **Join Operations**: Combines tuples from two relations  
* **Division**: Finds tuples related to all tuples in another relation  
* **Tuple Relational Calculus (TRC)**: Non-procedural, uses tuple variables  
* **Domain Relational Calculus (DRC)**: Uses domain variables and logical formulas

---

## **🔶 Structured Query Language (SQL)**

### **🔹 SQL Basics**

* **DDL (Data Definition Language)**: `CREATE`, `ALTER`, `DROP`  
* **DML (Data Manipulation Language)**: `INSERT`, `UPDATE`, `DELETE`, `SELECT`

### **🔹 Aggregate Functions**

* `MIN()`, `MAX()`, `SUM()`, `AVG()`, `COUNT()`

### **🔹 Logical Operators**

* `AND`, `OR`, `NOT`

### **🔹 Predicates**

* `LIKE`, `BETWEEN`, `ALIAS`, `DISTINCT`

### **🔹 Clauses**

* `GROUP BY`, `HAVING`, `ORDER BY`, `TOP` / `LIMIT`

### **🔹 Join Types**

| Type | Description |
| ----- | ----- |
| **Inner Join** | Matches rows with common values in both tables |
| **Natural Join** | Automatically joins on columns with same name |
| **Full Outer Join** | Includes all rows from both tables |
| **Left Outer Join** | All rows from left \+ matched from right |
| **Right Outer Join** | All rows from right \+ matched from left |
| **Equi Join** | Join using equality condition |

---

## **🔶 Normalization and Database Design**

### **🔹 Functional Dependencies**

* **Definition**: X → Y means Y is functionally dependent on X  
* **Armstrong’s Axioms**:  
  * **Reflexivity**: If Y ⊆ X, then X → Y  
  * **Augmentation**: If X → Y, then XZ → YZ  
  * **Transitivity**: If X → Y and Y → Z, then X → Z

### **🔹 Types of Functional Dependencies**

| Type | Description |
| ----- | ----- |
| **Trivial** | Y ⊆ X in X → Y |
| **Non-Trivial** | Y ⊈ X in X → Y |
| **Partial** | Part of composite key determines attribute |
| **Full** | Entire key is required to determine attribute |

### **🔹 Closure of Functional Dependencies**

Set of all FDs that can be inferred from a given set using Armstrong’s Axioms.

### **🔹 Normal Forms**

| Normal Form | Description |
| ----- | ----- |
| **1NF** | Atomic values, no repeating groups |
| **2NF** | 1NF \+ no partial dependency on primary key |
| **3NF** | 2NF \+ no transitive dependency |
| **BCNF** | Every determinant is a candidate key |

### **🔹 Denormalization**

Process of combining tables to improve performance at the cost of redundancy.

