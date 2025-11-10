# **Basic Operators in Relational Algebra**

Relational algebra comprises various basic operators that help us fetch and manipulate data from relational tables in the database to perform specific operations on relational data. These fundamental operations include:

* **Selection (σ)**
* **Projection (π)**  
* **Union (U)**  
* **Set difference (−)**
* **Cartesian product (×)** 
* **Rename (ρ)**

![][image1]

## **🔹 1\. Selection (σ)**

### **🔸 Definition:**

The Selection operation (σ) in relational algebra is used to select a subset of tuples (rows) from a relation that satisfy a specific condition.  
 It filters the rows of a relation based on a predicate (logical condition) but does not alter the structure of the table.

### **🔸 Notation:**  **σ\_{condition}(R)**  **where *R* is a relation and *condition* is the filtering criterion.**

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

SELECT \* FROM STUDENT WHERE Marks \> 75;

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

### **🔸 Notation:**  **R\_1 ∪ R\_2**  

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

SELECT Student\_Name FROM FRENCH  
UNION  
SELECT Student\_Name FROM GERMAN;

---

## **🔹 4\. Intersection (∩)**

### **🔸 Definition:**

The Intersection operation (∩) is used to retrieve only those tuples that are present in both relations.  
 It also requires the two relations to be union-compatible.

### **🔸 Notation:**

### **R\_1 ∩ R\_2**

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

SELECT Student\_Name FROM FRENCH  
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

SELECT Student\_Name FROM FRENCH  
EXCEPT  
SELECT Student\_Name FROM GERMAN;

## **🔹 6\. Rename (ρ)**

### **🔸 Definition:**

The Rename operation (ρ) is used to assign a temporary name to a relation or to its attributes.  
 It is a unary operation (works on a single relation) and is mainly used to:

* Avoid ambiguity in expressions involving multiple relations with similar attribute names.

* Improve readability and clarity of relational expressions.

### **🔸 Notation:**

### **ρ\_{new\_relation\_name}(R)**   **or**  **ρ\_{(new\_relation\_name(new\_attribute\_list))}(R)**  

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

### **🔸 Notation:**  **R × S**  

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

SELECT \* FROM A CROSS JOIN B;

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

[image1]: <data:image/png;base64,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>