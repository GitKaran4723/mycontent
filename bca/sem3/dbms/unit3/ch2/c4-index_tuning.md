##  **Index Tuning**

Index tuning refers to the process of **optimizing the selection, creation, and maintenance** of indexes to improve database performance.  
 Proper index tuning balances query performance with storage costs and update overhead.

### **Activities in Index Tuning**

---

### **a. Choosing Appropriate Indexes**

* Index attributes frequently used in **WHERE**, **JOIN**, **GROUP BY**, and **ORDER BY** clauses.

* Helps speed up query execution dramatically.

---

### **b. Dropping Unused or Redundant Indexes**

* Excessive indexing can degrade write performance because every insert/update/delete must update its corresponding indexes.

* Regularly remove indexes that queries no longer use.

---

### **c. Balancing Read and Write Performance**

* Read-intensive systems benefit from more indexes.

* Write-intensive systems perform better with fewer indexes.

---

### **d. Monitoring Query Performance**

* Use query optimizers, execution plans, and performance tools to assess whether indexes are being used effectively.

---

### **e. Index Maintenance**

* Reorganizing or rebuilding fragmented indexes improves efficiency.

* Essential in high-update environments to prevent performance degradation.

---

