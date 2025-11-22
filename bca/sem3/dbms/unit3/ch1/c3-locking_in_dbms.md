# **Locking in DBMS**

Locking is a commonly used concurrency control technique to regulate how transactions access data.

## **How Locking Works**

A transaction must acquire a lock before reading or modifying data.  
 Until the lock is released, other transactions cannot access that data, ensuring isolation and preserving database integrity.

---

## **Types of Locks**

### **1\. Shared Lock (S-Lock)**

Allows multiple transactions to read the same data simultaneously.  
 However, no transaction can modify the data while shared locks are held.

Example:  
 Multiple users checking their account balances.

---

### **2\. Exclusive Lock (X-Lock)**

Allows a single transaction to both read and write a data item.  
 No other transaction can access the same data while an exclusive lock is held.

Example:  
 A user updating their bank balance.

---

## **Lock Compatibility Matrix**

| Lock Type | Shared (S) | Exclusive (X) |
| ----- | ----- | ----- |
| Shared (S) | Compatible | Not Compatible |
| Exclusive (X) | Not Compatible | Not Compatible |

Compatible means the locks can coexist; not compatible means one transaction must wait.

---

## **Key Points**

* Locking ensures safe concurrent execution.

* Used in lock-based concurrency control and Two-Phase Locking (2PL).

* Prevents anomalies such as dirty read and lost update.

* If not managed properly, locks may lead to deadlocks, where two or more transactions wait indefinitely for each other’s locks.

