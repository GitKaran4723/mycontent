

# **Database Storage and Indexing: Data on External Storage**

When we think about databases, we usually imagine tables filled with rows and columns. But internally, the database must store all this information physically somewhere. This physical place is usually **external storage** such as hard disks, SSDs, flash drives, or cloud-based storage.

Understanding how data is stored and indexed on external storage helps explain why some database operations are fast while others are slow.

---

# **1\. What is External Storage?**

External storage refers to permanent, non-volatile memory devices that keep data even when the system is turned off.  
 Examples include HDDs, SSDs, and cloud storage.

Since RAM is limited and temporary, databases use external storage to keep large amounts of data safely and permanently.

---

# **2\. How Data is Stored on Disks**

Disks store data in a structured and hierarchical manner. Key components include:

### **a) Blocks (Pages)**

* Smallest unit of data transfer between disk and main memory.

* Common sizes are 4KB, 8KB, 16KB.

* Databases always read or write entire blocks, not individual rows.

### **b) Files**

* A file is a collection of blocks.

* Tables, indexes, and logs are stored as files.

### **c) Records**

* Actual rows stored inside a block.

Since disk access is slow compared to memory, databases try to reduce the number of block reads and writes to improve performance.

---

# **3\. Why Disk Access is Slow**

External storage is slower than main memory because:

* Traditional hard disks have mechanical components that need to move physically.

* Even SSDs have higher latency than RAM.

* Data may be scattered across several blocks, increasing access time.

This is why effective data organization is important.

---

# **4\. File Organization Methods**

Databases use different file structures to arrange records efficiently:

### **1\. Heap (Unordered) Files**

* Records are stored in no specific order.

* Fast for inserting new records.

* Slow for searching since the system must scan the file.

### **2\. Sorted (Sequential) Files**

* Records are stored in sorted order.

* Good for range queries.

* Inserting and deleting becomes slower due to the need to maintain order.

### **3\. Hashed Files**

* Uses a hash function to determine the block where data will be stored.

* Very fast for equality searches (example: WHERE id \= 50).

* Not suitable for range-based queries.

---

# **5\. Need for Indexing**

Searching without an index means scanning every block of the table, which is slow.  
 An **index** works like the index of a book. It tells the database exactly where to find the required data so the system doesn’t have to read the entire file.

Indexes significantly reduce disk I/O and improve query performance.

---

# **6\. Types of Indexes**

### **a) B-Tree Index**

* Most widely used index structure.

* Keeps data in a balanced tree.

* Efficient for searching, inserting, deleting, and sorting.

* Supports range queries.

### **b) Hash Index**

* Uses hashing.

* Excellent for exact match queries.

* Cannot handle range queries well since hashing breaks order.

### **c) Clustered Index**

* Table data is physically arranged according to the index key.

* Only one clustered index is allowed per table.

### **d) Non-Clustered Index**

* Stored separately from the table data.

* Works like a reference pointer to the actual data.

* Multiple non-clustered indexes are allowed.

---

# **7\. Trade-offs of Indexing**

Indexes improve read performance but come with some costs:

* Insert, update, and delete operations become slower because indexes must also be updated.

* Indexes take additional storage space.

Choosing which columns to index requires careful planning.

---

# **8\. Ensuring Data Safety on External Storage**

Databases use various mechanisms to ensure data integrity:

* **Buffer Manager:** Stores frequently accessed data in RAM to reduce disk reads.

* **Log Files:** Record every change so that the system can recover after a crash.

* **Recovery Manager:** Uses logs to restore the database to a consistent state.

These systems ensure reliability even when failures occur.

---

# **Summary**

* External storage is where most of the database data is stored permanently.

* Disk access is slower than memory access, so data is organized efficiently in blocks and files.

* Different file organization methods affect performance.

* Indexing is used to speed up data retrieval by minimizing disk access.

* Proper indexing and storage strategies improve overall database performance.

