# **TCL Commands:**

### **1\. Create Savepoint**

**Query:**  
> START TRANSACTION;  
UPDATE Supplier SET phone \= 9999990000 WHERE SID \= 200001;  
SAVEPOINT sp1;

**Output:**  
Query OK, 1 row affected  
Query OK, 0 rows affected

---

### **2\. Rollback to Savepoint**

**Query:**  
> ROLLBACK TO SAVEPOINT sp1;

**Output:**  
Query OK, 0 rows affected

---

### **3\. Commit (save the changes)**

**Query:**  
> COMMIT;

**Output:**  
Query OK, 0 rows affected

---
