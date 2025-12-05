
# **Normal Forms in DBMS**

## **1\. What is Normalization in DBMS?**

Normalization is a **systematic approach to organize data** in a database to:

* **Reduce redundancy** (avoid storing duplicate data)
* **Eliminate anomalies** such as **insertion, update, and deletion anomalies**

It involves:

* Breaking large tables into **smaller, well-structured tables**
* Defining **relationships** between tables

**Benefits:**

* Reduces duplicate data
* Improves data integrity
* Makes database design simpler
* Optimizes database performance


## **2\. Importance of Normalization**

1. **Reduces Data Redundancy:**  
    Saves disk space and avoids inconsistencies by storing data efficiently.

2. **Improves Data Integrity:**  
    Ensures accuracy and consistency by organizing data properly.

3. **Simplifies Database Design:**  
    Easier to maintain, update, and extend.

4. **Optimizes Performance:**  
    Reduces anomalies and improves efficiency in database operations.

---

![Image 4](https://lh3.googleusercontent.com/d/1WsA0SOKEyR27pMavTZv6jJLUXDAuwrS)

Absolutely, Tinu\! Here’s a **well-formatted and elaborated version** of your text for **notes and exam preparation**. I’ve added headings, subpoints, examples, and simplified explanations to make it clear and easy to memorize.

## **1. First Normal Form (1NF): Eliminating Duplicate Records**  
A table is in [1NF ](https://www.geeksforgeeks.org/dbms/first-normal-form-1nf/)if it satisfies the following conditions:

* All columns contain atomic values (i.e., indivisible values).  
* Each row is unique (i.e., no duplicate rows).  
* Each column has a unique name.  
* The order in which data is stored does not matter.

**Example of 1NF Violation: **If a table has a column "**Phone Numbers**" that stores multiple phone numbers in a single cell, it violates 1NF. To bring it into 1NF, you need to separate phone numbers into individual rows.  
 **Example 2:** **Violation Example (Not in 1NF):**

| Student | Courses |
| :---- | :---- |
| **Raj** | **DBMS, OS** |

**In 1NF:**

| Student | Course |
| :---- | :---- |
| **Raj** | **DBMS** |
| **Raj** | **OS** |

## **2. Second Normal Form (2NF): Eliminating Partial Dependency**

**Definition:**  
A relation is in **2NF** if:

1. It is **already in 1NF**, and  
2. **No partial dependency** exists (i.e., no non-prime attribute depends on a part of a composite primary key).

**Applies only when the primary key is composite.**  
**Example:**  
Before 2NF:

| StudentID | CourseCode | StudentName |
| :---- | :---- | :---- |
| 1 | DB101 | Aditi |
| 1 | OS102 | Aditi |

Here, StudentID \+ CourseCode is the composite key, but StudentName depends only on StudentID, so it's a **partial dependency**.  
**After 2NF (decompose):**

* Student(StudentID, StudentName)  
* Enrollment(StudentID, CourseCode)

## **3. Third Normal Form (3NF): Eliminating Transitive Dependency**

**Definition:**  
A relation is in **3NF** if:

1. It is in **Second Normal Form (2NF)**  
2. **No transitive dependency** exists — i.e., every non-prime attribute is **only dependent on a candidate key**, not on another non-prime attribute.

**Formal Rule:**  
For any functional dependency **X → A**, at least one of the following must be true:

* A is a **prime attribute** (i.e., part of a candidate key)  
* X is a **super key**

 **Example:**

| EmpID | EmpName | DeptID | DeptName |
| :---- | :---- | :---- | :---- |
| 1 | Alice | 10 | CSE |
| 2 | Bob | 20 | ECE |

FDs:

* EmpID → EmpName, DeptID  
* DeptID → DeptName

🔸 EmpID is the **primary key**  
🔸 DeptName is **transitively dependent** on EmpID via DeptID  
So, this is **not in 3NF**  
**Convert to 3NF:**  
Split into two tables:  
**Employee Table**  
EmpID | EmpName | DeptID  
**Department Table**  
DeptID | DeptName  
Now each non-key attribute depends only on a **key**, and **no transitive dependencies** exist.

## **4. Boyce-Codd Normal Form (BCNF): The Strongest Form of 3NF**  
**Definition:**  
A relation is in **BCNF** if:

* For every non-trivial functional dependency **X → Y**, **X is a super key**

**Difference from 3NF:**  
BCNF is **stricter** than 3NF.  
3NF allows certain dependencies if the right side is a **prime attribute**, but BCNF does **not**.

   
**Example Where 3NF Holds but Not BCNF:**

| Student | Course | Instructor |
| :---- | :---- | :---- |
| **Alice** | **DBMS** | **Rao** |
| **Bob** | **DBMS** | **Rao** |

**FDs:**

* **Student, Course → Instructor**  
* **Instructor → Course Instructor is not a key**

 **Violates BCNF**

**Convert to BCNF:**  
**Instructor Table**  
Instructor → Course  
**Enrolment Table**  
Student, Instructor  
Now all FDs have **super keys on LHS**  


