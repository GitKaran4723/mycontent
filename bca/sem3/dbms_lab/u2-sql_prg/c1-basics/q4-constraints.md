# **Queries with Constraints**

 **1\. Create the Supplier table with Primary Key Constraint**

**Query:**  
> CREATE TABLE Supplier (  
  SID INT PRIMARY KEY,  
  Sname VARCHAR(100),  
  branch VARCHAR(50),  
  city VARCHAR(50),  
  phone VARCHAR(20)  
);

**Query:**  
> DESC Supplier;

**Output:**

| Field | Data Type | Null | Key Type | Default Value | (Extra) |
| ----- | ----- | ----- | ----- | ----- | ----- |
| **SID** | `int` | NO | PRIMARY | `NULL` |  |
| **Sname** | `varchar(100)` | YES |  | `NULL` |  |
| **branch** | `varchar(50)` | YES |  | `NULL` |  |
| **city** | `varchar(50)` | YES |  | `NULL` |  |
| **phone** | `varchar(20)` | YES |  | `NULL` |  |

---

**2\. Create Supplies table with Foreign Key Constraint**

**Query:**  
> CREATE TABLE Supplies (  
  SID INT,  
  PID INT,  
  qty INT,  
  date\_supplied DATE,  
  FOREIGN KEY (SID) REFERENCES Supplier(SID),  
  FOREIGN KEY (PID) REFERENCES Part(PID)  
);

**Query:**  
> DESC Supplies;

**Output:**  
 

| Field Name | Data Type | Null | Key | Default Value | Additional Info |
| ----- | ----- | ----- | ----- | ----- | ----- |
| SID | int | Yes | Multi | NULL |  |
| PID | int | Yes | Multi | NULL |  |
| qty | int | Yes |  | NULL |  |
| date\_supplied | date | Yes |  | NULL |  |

---

 **3\. Create Part table with UNIQUE Constraint**

**Query:**  
> CREATE TABLE Part (  
  PID INT PRIMARY KEY,  
  Pname VARCHAR(100) UNIQUE,  
  color VARCHAR(50),  
  price DECIMAL(10,2)  
);

**Query:**  
> DESC Part;

**Output:**

| Field | Type | Null | Key | Default | Extra |
| ----- | ----- | ----- | ----- | ----- | ----- |
| PID | int | NO | PRI | NULL |  |
| Pname | varchar(100) | YES | UNI | NULL |  |
| color | varchar(50) | YES |  | NULL |  |
| price | decimal(10,2) | YES |  | NULL |  |

---

 **4\. Create Supplier table with CHECK Constraint**

**Query:**  
> CREATE TABLE SupplierCheck (  
  SID INT PRIMARY KEY,  
  Sname VARCHAR(100),  
  city VARCHAR(50),  
  phone VARCHAR(20),  
  CHECK (CHAR\_LENGTH(phone) \>= 7\)  
);

**Query:**  
> DESC SupplierCheck;

**Output:**

| Field | Type | Null | Key | Default | Extra |
| ----- | ----- | ----- | ----- | ----- | ----- |
| SID | int | NO | PRI | NULL |  |
| Sname | varchar(100) | YES |  | NULL |  |
| city | varchar(50) | YES |  | NULL |  |
| phone | varchar(20) | YES |  | NULL |  |

---

**5\. Create Supplier table with DEFAULT Constraint**

**Query:**  
> CREATE TABLE SupplierDefault (  
  SID INT PRIMARY KEY,  
  Sname VARCHAR(100),  
  city VARCHAR(50) DEFAULT 'Bangalore',  
  phone VARCHAR(20)  
);

**Query:**  
> DESC SupplierDefault;

**Output:**

| Field | Type | Null | Key | Default | Extra |
| ----- | ----- | ----- | ----- | ----- | ----- |
| SID | int | NO | PRI | NULL |  |
| Sname | varchar(100) | YES |  | NULL |  |
| city | varchar(50) | YES |  | Bangalore |  |
| phone | varchar(20) | YES |  | NULL |  |

---

