

# **📘 SQL Commands**

SQL (Structured Query Language) is a standard language used to interact with databases. It allows users to create, manipulate, query, and control databases and their objects.

**SQL commands are classified into five main categories:**

| Category | Full Form | Purpose |
| ----- | ----- | ----- |
| DDL | Data Definition Language | Define, alter, or remove database objects (tables, indexes, schemas) |
| DML | Data Manipulation Language | Manipulate data stored in tables (insert, update, delete) |
| DQL | Data Query Language | Retrieve data from the database (`SELECT`) |
| DCL | Data Control Language | Control access to data (`GRANT`, `REVOKE`) |
| TCL | Transaction Control Language | Manage database transactions (`COMMIT`, `ROLLBACK`) |

---

![Image 2](https://lh3.googleusercontent.com/d/1-KKL73jnhiRgUxgaA_OVn50YIUfYDdFB)

**1️⃣ DDL – Data Definition Language**

## **Definition:**
  DDL commands are used to **define, modify, or remove database structures** such as tables, indexes, schemas, or views. They deal with **database schema** rather than actual data.

## **Common DDL Commands:**

| Command | Description | Syntax | Example |
| ----- | ----- | ----- | ----- |
| CREATE | Create database objects (tables, indexes, views, procedures) | `CREATE TABLE table_name (col1 datatype, col2 datatype, ...);` | `CREATE TABLE employees (employee_id INT PRIMARY KEY, first_name VARCHAR(50), last_name VARCHAR(50), hire_date DATE);` |
| DROP | Delete objects from the database | `DROP TABLE table_name;` | `DROP TABLE employees;` |
| ALTER | Modify structure of a table | `ALTER TABLE table_name ADD COLUMN column_name datatype;` | `ALTER TABLE employees ADD COLUMN department VARCHAR(50);` |
| TRUNCATE | Remove all records from a table | `TRUNCATE TABLE table_name;` | `TRUNCATE TABLE employees;` |
| COMMENT | Add comments to a table | `COMMENT 'text' ON TABLE table_name;` | `COMMENT 'Employee Table' ON TABLE employees;` |
| RENAME | Rename an object | `RENAME TABLE old_name TO new_name;` | `RENAME TABLE employees TO staff;` |

### **✅ Advantages of DDL**

* Helps define and modify database structure easily. 
* Maintains database integrity. 
* Useful for creating, altering, or deleting database objects. 

### **❌ Disadvantages of DDL**

* Cannot manipulate or query actual data. 
* Changes are structural; accidental alteration may affect data. 
* Cannot control access or transactions. 

## **2️⃣ DML – Data Manipulation Language**

## **Definition:**  
DML commands **manipulate data** in existing tables — insert, update, delete, or call procedures.



## **Common DML Commands:**

| Command | Description | Syntax | Example |
| ----- | ----- | ----- | ----- |
| INSERT | Add new records | `INSERT INTO table_name (col1, col2, ...) VALUES (val1, val2, ...);` | `INSERT INTO employees (first_name, last_name, department) VALUES ('Jane', 'Smith', 'HR');` |
| UPDATE | Modify existing records | `UPDATE table_name SET column1=value1 WHERE condition;` | `UPDATE students SET due_fees=20000 WHERE stu_name='Mini';` |
| DELETE | Delete records | `DELETE FROM table_name WHERE condition;` | `DELETE FROM students WHERE stu_id='001';` |
| LOCK | Control table concurrency | `LOCK TABLE table_name IN lock_mode;` | `LOCK TABLE employees IN EXCLUSIVE MODE;` |
| CALL | Call a procedure | `CALL procedure_name(arguments);` | `CALL update_salary(101, 60000);` |
| EXPLAIN PLAN | Show data access path | `EXPLAIN PLAN FOR SELECT * FROM table_name;` | `EXPLAIN PLAN FOR SELECT * FROM employees;` |

### **✅ Advantages of DML**

* Allows manipulation of stored data. 
* Provides interactive control over data access. 
*  Users can retrieve or modify specific data. 
* Supports a variety of operations across different databases. 

### **❌ Disadvantages of DML**

* Cannot change database structure. 

* Cannot hide or reveal specific columns (limited view control). 

* Cannot create or delete database objects. 

* Cannot access data outside existing tables. 


## **3️⃣ DQL – Data Query Language**

### **Definition:**  
DQL commands are used to **query and retrieve data** from a database. The primary command is `SELECT`.



## **Common DQL Commands:**

| Command | Description | Syntax | Example |
| ----- | ----- | ----- | ----- |
| SELECT | Retrieve data from tables | `SELECT column1, column2 FROM table_name WHERE condition;` | `SELECT first_name, department FROM employees WHERE department='HR';` |
| DISTINCT | Retrieve unique values | `SELECT DISTINCT column_name FROM table_name;` | `SELECT DISTINCT department FROM employees;` |
| WHERE | Filter records based on condition | `SELECT * FROM table_name WHERE condition;` | `SELECT * FROM students WHERE due_fees>10000;` |
| ORDER BY | Sort data | \`SELECT \* FROM table\_name ORDER BY column\_name ASC | DESC;\` |
| GROUP BY | Group records for aggregate functions | `SELECT column, COUNT(*) FROM table_name GROUP BY column;` | `SELECT department, COUNT(*) FROM employees GROUP BY department;` |
| HAVING | Filter groups after aggregation | `SELECT column, SUM(col2) FROM table_name GROUP BY column HAVING SUM(col2)>10000;` | `SELECT department, SUM(salary) FROM employees GROUP BY department HAVING SUM(salary)>50000;` |

### **✅ Advantages of DQL**

* Retrieves data efficiently. 
* Allows filtering, sorting, grouping, and aggregation. 
* Helps in analyzing and summarizing data. 

### **❌ Disadvantages of DQL**

* Cannot modify or delete data. 
* Cannot create or alter database structures. 

* Only reads data; does not control access or transactions. 



## **4️⃣ DCL – Data Control Language**

## **Definition:**  
DCL commands are used to **control access and permissions** on database objects.

### **Common DCL Commands:**

| Command | Description | Syntax | Example |
| ----- | ----- | ----- | ----- |
| GRANT | Provide privileges to users | `GRANT privilege_name ON table_name TO user;` | `GRANT SELECT, INSERT ON employees TO user1;` |
| REVOKE | Remove privileges from users | `REVOKE privilege_name ON table_name FROM user;` | `REVOKE INSERT ON employees FROM user1;` |

### **✅ Advantages of DCL**

* Secures database objects. 
* Controls user access to data. 
* Prevents unauthorized operations. 

### **❌ Disadvantages of DCL**

* Cannot manipulate data or database structure. 
*  Only controls permissions.
*  Privileges must be carefully managed; errors may lock users out. 


## **5️⃣ TCL – Transaction Control Language**

### **Definition:** 
 TCL commands are used to **manage transactions** in the database. They ensure **data consistency** and integrity.


### **Common TCL Commands:**

| Command | Description | Syntax | Example |
| ----- | ----- | ----- | ----- |
| COMMIT | Save transaction permanently | `COMMIT;` | `COMMIT;` |
| ROLLBACK | Undo changes in a transaction | `ROLLBACK;` | `ROLLBACK;` |
| SAVEPOINT | Set a point to rollback to | `SAVEPOINT savepoint_name;` | `SAVEPOINT sp1;` |
| SET TRANSACTION | Set transaction properties | `SET TRANSACTION property;` | `SET TRANSACTION READ ONLY;` |

### **✅ Advantages of TCL**

* Ensures data consistency (ACID properties). 
* Allows rollback in case of errors. 
*  Controls transaction flow effectively. 

### **❌ Disadvantages of TCL**

*  Cannot create, delete, or modify tables. 
* Cannot control user access or permissions. 
* Only manages transactions, not data or schema directly.

