**Consider the following Schema**   
Supplier(SID, Sname, branch, city, phone)   
Part(PID, Pname, color, price)   
Supplies(SID, PID, qty, date\_supplied)

**Create a database:**

> CREATE DATABASE porter;  
USE porter;

**DDL Commands** 

**1\. Create the above tables**

i) Supplier:

> CREATE TABLE Supplier  
(  
  SID INT PRIMARY KEY,  
  Sname VARCHAR(100) NOT NULL,  
  branch VARCHAR(50),  
  city VARCHAR(100),  
  phone VARCHAR(20)  
);  

   ---
ii) Part

> CREATE TABLE Part   
(  
  PID INT PRIMARY KEY,  
  Pname VARCHAR(100),  
  color VARCHAR(30),  
  price DECIMAL(10,2)   
);

---

iii) Supplies

> CREATE TABLE Supplies   
(  
  SID INT,  
  PID INT,  
  qty INT CHECK,  
  date\_supplied DATE,  
  PRIMARY KEY (SID, PID),  
  FOREIGN KEY (SID) REFERENCES Supplier(SID) ,  
  FOREIGN KEY (PID) REFERENCES Part(PID)   
);



**2.Add a new attribute state in supplier table** 

> ALTER TABLE Supplier  
ADD COLUMN state VARCHAR(50);

Output:   
> DESC Supplier;

| Field | Data Type | Nullable | Key | Default Value | Extra |
| ----- | ----- | ----- | ----- | ----- | ----- |
| SID | int | NO | PRI (Primary Key) | NULL |  |
| Sname | varchar(100) | YES |  | NULL |  |
| branch | varchar(50) | YES |  | NULL |  |
| city | varchar(100) | YES |  | NULL |  |
| phone | varchar(20) | YES |  | NULL |  |
| state | varchar(50) | YES |  | NULL |  |
---


**3\.  Remove attribute `city` from Supplier table**  
   
**Query:**

> ALTER TABLE Supplier  
DROP COLUMN city;

**OUTPUT :** 

DESC Supplier;

| Field | Type | Null | Key | Default | Extra |
| ----- | ----- | ----- | ----- | ----- | ----- |
| SID | int | NO | PRI | NULL |  |
| Sname | varchar(100) | YES |  | NULL |  |
| branch | varchar(50) | YES |  | NULL |  |
| phone | varchar(20) | YES |  | NULL |  |
| state | varchar(50) | YES |  | NULL |  |

---

**4\. Modify the data type of phone attribute**

**Query:**

> ALTER TABLE Supplier  
MODIFY phone BIGINT;

**OUTPUT** :  DESC Supplier;

| Field | Type | Null | Key | Default | Extra |
| ----- | ----- | ----- | ----- | ----- | ----- |
| SID | int | NO | PRI | NULL |  |
| Sname | varchar(100) | YES |  | NULL |  |
| branch | varchar(50) | YES |  | NULL |  |
| phone | bigint | YES |  | NULL |  |
| state | varchar(50) | YES |  | NULL |  |

---

**5\. Change the name of attribute `city` to `address`**

**Query:** 

> ALTER TABLE Supplier  
CHANGE COLUMN city address VARCHAR(100);

**OUTPUT:**     DESC Supplier;

| Field | Type | Null | Key | Default | Extra |
| ----- | ----- | ----- | ----- | ----- | ----- |
| SID | int | NO | PRI | NULL |  |
| Sname | varchar(100) | YES |  | NULL |  |
| branch | varchar(50) | YES |  | NULL |  |
| address | varchar(100) | YES |  | NULL |  |
| phone | bigint | YES |  | NULL |  |
| state | varchar(50) | YES |  | NULL |  |

---

**6\. Change the table name Supplier → sup**

**Query:**

> ALTER TABLE Supplier  
RENAME TO sup;

**OUTPUT:** SHOW TABLES;

| Porter |
| ----- |
| sup |
| Supplies |
| Part |
---

**7\.  Use TRUNCATE to delete contents of Supplies table**

**Query:** 

> TRUNCATE TABLE Supplies;

**OUTPUT :** SELECT \* FROM Supplies;

Empty set (0.00 sec)

---

**8\.  Remove the Part table from database**

> DROP TABLE Part;

**OUTPUT :**

| Porter |
| :---: |
| Supplies |
| sup |

---
