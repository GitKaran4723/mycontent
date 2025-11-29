# **Table Constraints in DBMS**

Constraints are vital rules implemented on table columns within a database. Their purpose is to guarantee data integrity, prevent invalid entries, and uphold accuracy and consistency.

### **1.PRIMARY KEY Constraint**

* Uniquely identifies each record within a table.  
* Cannot contain NULL values.  
* Each table can have only one primary key.

**SQL Example:**

> CREATE TABLE Student 
(  
RollNo INT PRIMARY KEY,  
Name VARCHAR(100)  
);

### **2.FOREIGN KEY Constraint**

* Establishes a relationship between two tables.  
* Enforces referential integrity, ensuring data consistency between related tables.  
* Values in the foreign key column must match a primary key in the referenced table.

**SQL Example:**

> CREATE TABLE Enrollment (  
StudentID INT,  
CourseID INT,  
FOREIGN KEY (StudentID) REFERENCES Student(RollNo)  
);

### **3. NOT NULL Constraint**

* Prevents NULL values from being entered into a specific column.  
* Guarantees that the field must always contain a value.

**SQL Example:**

> CREATE TABLE Product (  
ProductID INT,  
ProductName VARCHAR(100) NOT NULL  
);

### **4. UNIQUE Constraint**

* Ensures that all values in a specified column are distinct.  
* Allows for a single NULL value (unlike the Primary Key, which forbids any NULLs).


**SQL Example:**

> CREATE TABLE Users (  
UserID INT,  
Email VARCHAR(100) UNIQUE  
);

### **5. CHECK Constraint**

* Ensures that values in a column meet a predefined condition.  
* Validates data input before it is stored in the database.

**SQL Example:**

> CREATE TABLE Account (  
AccNo INT,  
Balance DECIMAL CHECK (Balance \>= 0\)  
);

This example prevents the insertion of a negative balance.  
