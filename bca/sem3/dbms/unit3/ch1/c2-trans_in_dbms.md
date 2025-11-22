# **Transaction in DBMS**

A transaction is a sequence of operations (such as reading, writing, updating, and deleting data) executed as a single logical unit of work.  
 A transaction must fully complete or be fully undone to maintain the stability and integrity of the database.

**Principle:**  
 Either all the operations in a transaction are committed, or the database rolls back to the state before the transaction began.

### **Example: Online Banking**

When transferring money from Account A to Account B:

1. The system reads the balance of Account A.

2. The amount is deducted from A’s balance.

3. The amount is added to B’s balance.

If any of these steps fail, the entire process is cancelled and no partial update is allowed.

---

## **Operations in a Transaction**

### **1\. Read(X)**

Reads the value of a data item X from the database and temporarily stores it in main memory.  
 Example: Reading the balance of an account before modifying it.

### **2\. Write(X)**

Writes the updated value of a data item X from main memory back into the database.  
 Example: Writing the new balance after deduction or addition.

### **3\. Commit**

Makes all changes performed by the transaction permanent. After commit, the system guarantees that the results will survive even in case of system failure.

### **4\. Rollback**

Cancels all operations of the transaction and restores the database to the most recent consistent state before the transaction began. Usually executed when errors or failures occur during a transaction.

---

# **Transaction Schedules**

A schedule is the exact sequence in which operations from multiple transactions are executed. Schedules determine how transactions interact with one another when running concurrently.

### **1\. Serial Schedule**

Transactions are executed one after another, with no interleaving of operations.  
 This ensures maximum consistency but leads to poor performance due to lack of concurrency.

Example:  
 Transaction T1 completes all of its operations before T2 begins.

### **2\. Non-Serial Schedule**

Operations of multiple transactions are interleaved.  
 This improves performance and increases system throughput but requires concurrency control to avoid conflicts and ensure correctness.

Example:  
 T1 and T2 operate on different or even the same data items, but their operations are interwoven to utilize system resources efficiently.

# **Concurrency in DBMS**

## **Definition**

Concurrency refers to the ability of a DBMS to allow multiple transactions to access and manipulate data at the same time without interfering with each other.

The goal of concurrency control is to ensure that even though several operations occur simultaneously, the database remains correct, consistent, and reliable.

### **Objectives:**

1. Preserve database consistency.

2. Avoid conflicts between concurrent transactions.

3. Improve overall system performance and resource utilization.

4. Ensure that the effect of concurrent transactions is equivalent to some serial execution order.

---

# **Concurrency Problems (Anomalies)**

When transactions run concurrently without proper control, several problems may arise:

### **1\. Dirty Read**

Occurs when one transaction reads data that has been written by another transaction which has not yet committed. If the other transaction rolls back, the read data becomes invalid.

Example:  
 T2 reads a value updated by T1, but T1 later rolls back, causing T2 to have read incorrect data.

---

### **2\. Lost Update**

Occurs when two transactions read the same data and both update it based on the original value. One update overwrites the other, resulting in the loss of one transaction’s effect.

Example:  
 If two transactions modify the same balance simultaneously, the update from one may overwrite the other’s work.

---

### **3\. Inconsistent Read (Non-repeatable Read)**

Occurs when a transaction reads the same data item multiple times and sees different values because another transaction updated the data between the two reads.

Example:  
 T1 reads a product price, then T2 updates it, and T1 reads it again and finds a different value.

---

# **Concurrency Control Methods**

To prevent such anomalies, DBMS employs several techniques, such as:

* Lock-based protocols (shared and exclusive locks)

* Timestamp ordering

* Optimistic concurrency control

* Two-Phase Locking (2PL)

---

## 

