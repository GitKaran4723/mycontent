## **Index Structures**

An **index** is a data structure that enhances the speed of data retrieval in a database table.  
 It acts like the index of a book, allowing the system to locate data records **without scanning the entire file**.

### **Common Index Structures**

---

### **a. Single-Level Index**

* Simple structure containing a **list of key values** and associated **pointers to actual records**.

* Works similarly to a traditional directory or phone book.

* Suitable for moderately sized datasets.

---

### **b. Multi-Level Index**

* Introduces additional levels of indexing when the primary index becomes too large.

* The top-level index points to lower-level index blocks, which eventually point to data blocks.

* Improves lookup time for large datasets by reducing disk accesses.

---

### **c. B+ Tree Index**

* The most widely used index structure in databases.

* A balanced tree where internal nodes store search keys, and leaf nodes contain actual pointers to records.

* Supports **equality searches**, **range queries**, and **sorted traversals** efficiently.

* Maintains balanced height, ensuring predictable performance.

---

### **d. Hash Index**

* Uses a hash function to map key values to bucket locations.

* Provides extremely fast access for **exact-match queries**.

* Not suitable for range searches due to loss of order.

---

### **e. Bitmap Index**

* Uses bitmaps to represent the presence or absence of a value.

* Highly efficient for attributes with **low cardinality** (few distinct values), such as gender or status fields.

* Commonly used in data warehouses for analytical queries.

---

