# **Lock Management**

## **Definition**

Lock management is the internal DBMS component responsible for **coordinating the acquisition, maintenance, and release** of locks.  
 Its purpose is to ensure that multiple transactions can access data concurrently while maintaining consistency and preventing conflicts.

Lock management is fundamental in concurrency control and ensures that serializability and isolation are upheld.

---

# **Types of Locks**

## **1\. Shared Lock (S)**

* Allows a transaction to **read** a data item.

* Multiple transactions may hold a shared lock simultaneously on the same item.

* Prevents any transaction from writing to the data while shared locks exist.

---

## **2\. Exclusive Lock (X)**

* Allows a transaction to **both read and write** a data item.

* Only one transaction can hold an exclusive lock on a given item at any time.

* Prevents both read and write access by others until the lock is released.

---

## **3\. Intention Locks**

Intention locks are used in **multi-granularity locking**, where locks are applied at different levels such as tables, pages, and rows.  
 They allow the DBMS to manage locks at higher and lower granularities without conflict.

### **Types:**

### **a. IS (Intention Shared)**

Indicates that the transaction intends to acquire **shared locks** on lower-level data items.

### **b. IX (Intention Exclusive)**

Indicates that the transaction intends to acquire **exclusive locks** at a finer granularity.

### **c. SIX (Shared with Intention Exclusive)**

Indicates that the transaction holds a **shared lock** on the entire object (e.g., table) but intends to acquire **exclusive locks** on some of the lower-level items (e.g., rows).