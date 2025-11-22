

#  **Deadlocks**

## **Definition**

A deadlock in a DBMS occurs when two or more transactions are **waiting indefinitely** for resources (locks) held by each other.  
 Since each transaction is waiting for a lock that another transaction will not release, none of them can proceed, resulting in a standstill.

A simple analogy is two processes each holding one required resource and waiting for the other to release the second resource, which never happens.

---

## **Deadlock Example**

Consider two transactions:

* **T1** locks data item **A** and requests data item **B**.

* **T2** locks data item **B** and requests data item **A**.

Since T1 is waiting for a lock held by T2, and T2 is waiting for a lock held by T1, neither can continue.  
 This forms a circular wait and results in a deadlock.

---

# **Deadlock Handling Techniques**

Deadlocks must be managed to keep the system running efficiently. DBMS handles deadlocks using three major strategies:

---

## **1\. Deadlock Prevention**

The system is designed to ensure that deadlocks **do not occur** by eliminating at least one of the necessary conditions for deadlock, such as circular wait.

### **Methods:**

### **a. Wait-Die Scheme**

* Based on transaction timestamps.

* If an **older** transaction requests a lock held by a **younger** transaction, it is allowed to **wait**.

* If a **younger** transaction requests a lock held by an **older** transaction, it is **aborted** (“dies”) and restarted.

### **b. Wound-Wait Scheme**

* Also uses timestamps.

* If an **older** transaction requests a lock held by a **younger** transaction, it **preempts** (forces abort) the younger transaction.

* If a **younger** transaction requests a lock held by an **older** transaction, it must **wait**.

These methods avoid circular wait and therefore prevent deadlocks.

---

## **2\. Deadlock Detection**

This method allows deadlocks to form but periodically checks for them using a detection mechanism.

### **Technique: Wait-For Graph**

* Each transaction is represented as a node in a directed graph.

* A directed edge from T1 to T2 indicates that T1 is waiting for a resource held by T2.

* If the graph contains a **cycle**, a deadlock exists.

* After detecting a deadlock, the system resolves it by aborting one or more transactions involved in the cycle (usually the youngest or the least costly one).

---

## **3\. Deadlock Avoidance**

The system attempts to avoid entering a potentially deadlocked state by analyzing resource requests beforehand.

### **Technique: Banker’s Algorithm**

* Before granting a lock, the system checks whether fulfilling the request will keep the system in a **safe state**.

* A safe state guarantees that there exists some order in which all transactions can complete.

* If granting the lock may lead to an unsafe state, the request is delayed.

---

