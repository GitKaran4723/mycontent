# **Database Design – Keys**

In database design, **keys** are essential to:

* **Uniquely identify rows (records)** in a table.  
* **Define relationships** between tables.  
* **Maintain data integrity**, **eliminate redundancy**, and **enforce uniqueness**.

**🔑 Types of Keys in DBMS**

1. Primary Key  
2. Candidate Key  
3. Super Key  
4. Foreign Key  
5. Composite Key  
6. Alternate Key  
7. Unique Key  
8. Surrogate Key

### **1\. Primary Key**
---

✅ **Definition:** A **Primary Key** is a column or a group of columns that **uniquely identifies each row** in a table.

* Cannot be **NULL**  
* Must be **unique**

📌 **Rules:**

* Only **one primary key per table**  
* No **duplicate** or **NULL** values allowed

📊 **Example:**

STUDENT Table

| StudentID | Name | Age |
| ----- | ----- | ----- |
|        101 | Rohan | 20 |
| 102 | Meena | 21 |

Primary Key: StudentID

### **2\. Candidate Key**
---

✅ **Definition:** A **Candidate Key** is any column or set of columns that can **uniquely identify rows** in a table.

* One candidate key is selected as the **primary key**.

📌 **Characteristics:**

* All **primary keys** are candidate keys.  
* A table can have **multiple candidate keys**.  
* **Minimal**: No extra attribute is included.

📊 **Example:**

EMPLOYEE Table

| EmpID | Email | Mobile |
| ----- | ----- | ----- |
| E001 | john@example.com | 9876543210 |
| E002 | jane@example.com | 9876543222 |

Candidate Keys: EmpID, Email, Mobile

### **3\. Super Key**
---

✅ **Definition:** A **Super Key** is any set of attributes that can **uniquely identify a row**. It may include **extra attributes** not required for uniqueness.

📌 **Key Difference:**

* **Super Key \= Candidate Key \+ Extra Attributes**  
* **Candidate Key** is the **minimal super key**

**Example:**

EMPLOYEE Table

Super Keys: {EmpID}, {Email}, {EmpID, Name}

Candidate Keys: {EmpID}, {Email}

### **4\. Foreign Key**
---

✅ **Definition:** A **Foreign Key** is a column (or columns) in one table that **refers to the primary key** of another table.

📌 **Purpose:**

* **Establishes relationships** between tables  
* Ensures **referential integrity**

📊 **Example:**

DEPARTMENT Table

| DeptID | DeptName |
| ----- | :---: |
|                                   1 | IT |
| 2 | HR |

EMPLOYEE Table

| EmpID | Name | DeptID |
| ----- | :---: | :---: |
|                       101 | John | 1 |
| 102 | Alia | 2 |

Foreign Key: DeptID in EMPLOYEE references DeptID in DEPARTMENT

### **5\. Composite Key**
---

✅ **Definition:** A **Composite Key** is a **primary key made up of two or more columns**. Individually, the columns are **not unique**, but together they are.

📊 **Example:**

ENROLLMENT Table

| StudentID | CourseID | Grade |
| :---- | :---- | :---- |
| 101 | C101 | A |
| 101 | C102 | B |
| 102 | C101 | A+ |

Composite Key: (StudentID, CourseID)

# **🔑 Extended Key Types**

### **6\. Alternate Key**
---

✅ **Definition:** An **Alternate Key** is any **Candidate Key** that was **not chosen** as the primary key.

📊 **Example:**

STUDENT Table

| RollNo | Email | Phone |
| :---- | :---- | :---- |
| 101 | john@example.com | 9876543210 |
| 102 | jane@example.com | 9876543222 |

Primary Key: RollNo

Alternate Key: Email

### **7\. Unique Key**
---

✅ **Definition:** A **Unique Key** ensures all values in a column (or set of columns) are **unique**.

* **Allows one NULL value**  
* Can be applied to **multiple columns**

📊 **Example (SQL):**

CREATE TABLE Employee (

    EmpID INT PRIMARY KEY,

    Email VARCHAR(100) UNIQUE

);

* Email must be unique but can have one NULL.

### **8\. Surrogate Key**
---

✅ **Definition:** A **Surrogate Key** is a **system-generated identifier** (usually auto-incremented) used as a **primary key**.

* Not derived from application data  
* Has **no business meaning**

📊 **Example:**

EMPLOYEE Table

| EmpID | Name | NationalID |
| :---- | :---- | :---- |
| 1 | Raj | IN123456 |
| 2 | Meera | IN654321 |

EmpID is the surrogate key (auto-incremented)