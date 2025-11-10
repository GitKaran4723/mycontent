

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

## ![][image1]**1️⃣ DDL – Data Definition Language**

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

[image1]: <data:image/png;base64,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>