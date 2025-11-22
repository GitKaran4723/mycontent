## **Guidelines for Index Selection**

When designing index strategies, the following guidelines help determine which indexes are beneficial:

---

### **1\. Index Primary and Foreign Keys**

* These columns are frequently involved in joins and equality searches.

---

### **2\. Index Columns Used in WHERE Clauses**

* Particularly useful when columns have **high selectivity** (many distinct values).

---

### **3\. Use Composite Indexes for Multi-Column Queries**

* If queries often filter on multiple columns simultaneously, combined indexes can significantly improve performance.

---

### **4\. Avoid Indexing Columns with Low Selectivity**

* Columns with few distinct values (e.g., boolean fields) provide little benefit when indexed.

---

### **5\. Index Columns Used in ORDER BY or GROUP BY**

* Helps the optimizer avoid sorting operations, improving query speed.

---

### **6\. Balance Read and Write Requirements**

* Systems with frequent write operations should limit the number of indexes to reduce overhead.

* Analytical or reporting systems can use more indexes to support fast retrieval.

---

### **7\. Periodically Review and Tune Indexes**

* Query patterns change over time; unused indexes should be removed and effective ones should be optimized.

