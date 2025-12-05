# **Basic Operators in Relational Algebra**

Relational algebra comprises various basic operators that help us fetch and manipulate data from relational tables in the database to perform specific operations on relational data. These fundamental operations include:

* **Selection (σ)**
* **Projection (π)**  
* **Union (U)**  
* **Set difference (−)**
* **Cartesian product (×)** 
* **Rename (ρ)**


![Image 1](https://lh3.googleusercontent.com/d/1UWOyWqjOJ_AVi_z3kEmS_dbydn_dWLA8)


## **🔹 1\. Selection (σ)**

### **🔸 Definition:**

The Selection operation (σ) in relational algebra is used to select a subset of tuples (rows) from a relation that satisfy a specific condition.  
 It filters the rows of a relation based on a predicate (logical condition) but does not alter the structure of the table.

> **🔸 Notation:**  σ\_{condition}(R)  where *R* is a relation and *condition* is the filtering criterion.

### **🔸 Example:**

Consider a relation STUDENT with attributes:

| ID | Name | Marks |
| ----- | ----- | ----- |
| 1 | Ram | 85 |
| 2 | Sita | 72 |
| 3 | Ravi | 90 |
| 4 | Meena | 60 |

To select students who scored more than 75 marks:

 σ\_{Marks \> 75}(STUDENT)

**Result:**

| ID | Name | Marks |
| ----- | ----- | ----- |
| 1 | Ram | 85 |
| 3 | Ravi | 90  |

### **🔸 Explanation:**

The selection operation returns only those tuples that satisfy the condition `Marks > 75`.  
 It works horizontally on the relation (i.e., filters rows).

### **🔸 SQL Equivalent:**

> SELECT \* FROM STUDENT WHERE Marks \> 75;

---

## **🔹 2\. Projection (π)**

### **🔸 Definition:**

The Projection operation (π) is used to select specific attributes (columns) from a relation.  
 It removes all other attributes and by default eliminates duplicate tuples in the result.

### **🔸 Notation:**

###  **π{attribute\_list}(R)**  

### **🔸 Example:**

Consider the same relation STUDENT:

| ID | Name | Marks |
| ----- | ----- | ----- |
| 1 | Ram | 85 |
| 2 | Sita | 72 |
| 3 | Ravi | 90 |

**To display only the Name and Marks of students:**

 π\_{Name, Marks}(STUDENT)

**Result:**

| Name | Marks |
| ----- | ----- |
| Ram | 85 |
| Sita | 72 |
| Ravi | 90 |

### **🔸 Explanation:**

The projection operation works vertically by selecting only specified columns.  
 It helps in focusing on the relevant attributes needed for a query.

### **🔸 SQL Equivalent:**

SELECT DISTINCT Name, Marks FROM STUDENT;

---

## **🔹 3\. Union (∪)**

### **🔸 Definition:**

The Union operation (∪) is used to combine tuples from two relations and remove duplicates.  
 Both relations must be union-compatible, meaning they must have:

1. The same number of attributes.

2. The same data types for corresponding attributes.

> ### **🔸 Notation:**  R\_1 ∪ R\_2
### **🔸 Example:**

Consider two relations FRENCH and GERMAN that represent students studying those languages:

**FRENCH**

| Student\_Name | Roll\_No |
| ----- | ----- |
| Ram | 01 |
| Mohan | 02 |
| Vivek | 13 |

**GERMAN**

| Student\_Name | Roll\_No |
| ----- | ----- |
| Vivek | 13 |
| Geeta | 17 |
| Shyam | 21 |

**Union of both relations gives:**  
 π{Student\_Name}(FRENCH) ∪ π{Student\_Name}(GERMAN)

**Result:**

| Student\_Name |
| ----- |
| Ram |
| Mohan |
| Vivek |
| Geeta |
| Shyam |

### **🔸 Explanation:**

The Union operation merges data from both relations and removes duplicates automatically.

### **🔸 SQL Equivalent:**

> SELECT Student\_Name FROM FRENCH  
UNION  
SELECT Student\_Name FROM GERMAN;

---

## **🔹 4\. Intersection (∩)**

### **🔸 Definition:**

The Intersection operation (∩) is used to retrieve only those tuples that are present in both relations.  
 It also requires the two relations to be union-compatible.

### **🔸 Notation:**

> **R\_1 ∩ R\_2**

### **🔸 Example:**

**Using the same relations FRENCH and GERMAN:**

**FRENCH**

| Student\_Name | Roll\_No |
| ----- | ----- |
| Ram | 01 |
| Mohan | 02 |
| Vivek | 13 |
| Geeta | 17 |

**GERMAN**

| Student\_Name | Roll\_No |
| ----- | ----- |
| Vivek | 13 |
| Geeta | 17 |
| Shyam | 21 |

**Intersection of both relations:**  
 **π\_{Student\_Name}(FRENCH) ∩ π\_{Student\_Name}(GERMAN)**  
 

**Result:**

| Student\_Name |
| ----- |
| **Vivek** |
| **Geeta** |

### **🔸 Explanation:**

The intersection returns only those student names that appear in both FRENCH and GERMAN relations.

### **🔸 SQL Equivalent:**

> SELECT Student\_Name FROM FRENCH  
INTERSECT  
SELECT Student\_Name FROM GERMAN;

---

## **🔹 5\. Set Difference (−)**

### **🔸 Definition:**

The Set Difference operation (−) is used to find all tuples that are present in one relation but not in another.  
 It also requires both relations to be union-compatible.

### **🔸 Notation:**  **R\_1 − R\_2**

###   **🔸 Example:**

**Using the same relations:**

FRENCH

| Student\_Name | Roll\_No |
| ----- | ----- |
| Ram | 01 |
| Mohan | 02 |
| Vivek | 13 |
| Geeta | 17 |

**GERMAN**

| Student\_Name | Roll\_No |
| ----- | ----- |
| Vivek | 13 |
| Geeta | 17 |
| Shyam | 21 |

**To find students who study only FRENCH but not GERMAN:**  
 π\_{Student\_Name}(FRENCH) − π\_{Student\_Name}(GERMAN)  
 

**Result:**

| Student\_Name |
| ----- |
| Ram |
| Mohan |

### 

### **🔸 Explanation:**

The set difference operation removes all tuples that are common in both relations, leaving only the unique tuples of the first relation.

### **🔸 SQL Equivalent:**

> SELECT Student\_Name FROM FRENCH  
EXCEPT  
SELECT Student\_Name FROM GERMAN;

## **🔹 6\. Rename (ρ)**

### **🔸 Definition:**

The Rename operation (ρ) is used to assign a temporary name to a relation or to its attributes.  
 It is a unary operation (works on a single relation) and is mainly used to:

* Avoid ambiguity in expressions involving multiple relations with similar attribute names.

* Improve readability and clarity of relational expressions.

### **🔸 Notation:**

> ρ\_{new\_relation\_name}(R)  **or**  ρ\_{(new\_relation\_name(new\_attribute\_list))}(R)  

**This means: rename relation *R* or its attributes temporarily.**

### 

### 

### 

### 

### **🔸 Example:**

Consider a relation R:

| A | B | C |
| ----- | ----- | ----- |
|  |  |  |
| 1 | 2 | 4 |
| 2 | 2 | 3 |
| 3 | 2 | 3 |
| 4 | 3 | 4 |

**If we want to rename the attribute B to D, we use:**  
 ρ\_{(D/B)}(R)  
 

**Output:**

| A | D | C |
| ----- | ----- | ----- |
| **1** | **2** | **4** |
| **2** | **2** | **3** |
| **3** | **2** | **3** |
| **4** | **3** | **4** |

### **🔸 Explanation:**

The rename operator does not modify the actual data of the relation.  
 It only changes the names of attributes or relation temporarily for use within a query expression.

### **🔸 SQL Equivalent:**

**SELECT A, B AS D, C FROM R;**

**In SQL, the keyword AS performs the renaming of columns or tables.**

---

## **🔹 7\. Cartesian Product (×)**

### **🔸 Definition:**

The Cartesian Product (×), also known as the Cross Product, combines every tuple of one relation with every tuple of another relation.  
 It returns all possible combinations of tuples between the two relations.

This operation forms the basis of join operations in relational algebra.

### **🔸 Notation:**  
> **R × S**  

where *R* and *S* are two relations.

### **🔸 Example:**

**Relation A:**

| Name | Age | Sex |
| ----- | ----- | ----- |
| Ram | 14 | M |
| Sona | 15 | F |
| Kim | 20 | M |

**Relation B:**

| ID | Course |
| ----- | ----- |
| 1 | DS |
| 2 | DBMS |

**The Cartesian Product is written as:**  
 **A × B**  
 

**Output:**

| Name | Age | Sex | ID | Course |
| ----- | ----- | ----- | ----- | ----- |
| **Ram** | **14** | **M** | **1** | **DS** |
| **Ram** | **14** | **M** | **2** | **DBMS** |
| **Sona** | **15** | **F** | **1** | **DS** |
| **Sona** | **15** | **F** | **2** | **DBMS** |
| **Kim** | **20** | **M** | **1** | **DS** |
| **Kim** | **20** | **M** | **2** | **DBMS** |

### **🔸 Explanation:**

If Relation A has *n* tuples and Relation B has *m* tuples, then:  
 A × B \= n × m    
 Each tuple from A is paired with every tuple from B.

This operation is often used as a preliminary step to perform joins (like natural joins or theta joins).

### **🔸 SQL Equivalent:**

> SELECT \* FROM A CROSS JOIN B;

Both produce the Cartesian product of the two tables.

---


## **🧾 Summary Table**

| Operation | Symbol | Works On | SQL Equivalent | Function |
| ----- | ----- | ----- | ----- | ----- |
| Selection | σ | Rows | `WHERE` | Filters tuples based on a condition |
| Projection | π | Columns | `SELECT DISTINCT` | Selects specific attributes |
| Union | ∪ | Two Relations | `UNION` | Combines tuples from both tables |
| Intersection | ∩ | Two Relations | `INTERSECT` | Returns common tuples |
| Set Difference | − | Two Relations | `EXCEPT` | Returns tuples in one relation but not in the other  |
| Rename | ρ | Unary | `AS` | Assigns a temporary name to relation or attributes |
| Cartesian Product | × | Binary | `CROSS JOIN` | Combines every tuple from one relation with every tuple from another |

