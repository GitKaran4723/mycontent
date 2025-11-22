

# **Performance of Locking**

Locking affects performance in the following ways:

---

## **1\. Factors Affecting Locking Performance**

### **a) Locking Overhead**

* Each lock requires **memory** to store information (lock table entries).

* Additional **CPU time** is required to request, check, grant, or deny locks.

* More locks → More overhead.

### **b) Lock Contention**

* Occurs when multiple transactions request the **same data item**.

* If one transaction holds a lock, others must wait → increases **waiting time**.

* High lock contention reduces concurrency.

### **c) Lock Granularity**

Granularity \= Size of data item on which lock is applied.

* **Fine-grained locks** (tuple-level, field-level)  
   ✔ High concurrency  
   ✘ More overhead (too many locks)

* **Coarse-grained locks** (table-level, page-level)  
   ✔ Low overhead  
   ✘ Low concurrency (more blocking)

Performance depends on choosing the right granularity.

---

## **2\. Locking Protocols & Their Performance**

### **a) Two-Phase Locking (2PL)**

* Guarantees serializability but creates more **waiting** and **deadlocks**.

* **Strict 2PL** increases holding time of locks → reduces performance.

### **b) Timestamp-based vs Lock-based**

* Locking has higher overhead compared to timestamp methods.

* Timestamp methods avoid deadlocks but may require rollbacks.

---

## **3\. Blocking and Waiting Time**

* Transactions often must **wait** until the required lock is released.

* More waiting \= Poor response time.

* Long chains of waiting transactions can form → **cascading delays**.

**Waiting time increases when:**

* Transactions are long-running.

* Locks are held for long duration.

* Higher degree of conflict between transactions.

---

## **4\. Deadlocks and Performance Impact**

Deadlock \= A cycle of transactions waiting for each other’s locks.

Effects on performance:

* System wastes time detecting deadlocks.

* Must abort (rollback) one of the transactions → more overhead.

* Reduced throughput due to blocked resources.

---

## **5\. Starvation**

* Some transactions might wait indefinitely due to continuous denial of their lock requests.

* Starvation reduces system fairness and performance.

* Priority-based scheduling may cause this problem.

---

## **6\. Concurrency vs Performance Trade-off**

* More locking ensures **correctness** but reduces **concurrency**.

* Less locking improves speed but risks **inconsistency**.

* A balance must be maintained through:

  * Proper lock granularity

  * Effective scheduling algorithms

  * Optimized locking protocols

---

## **7\. Techniques to Improve Locking Performance**

### **a) Lock Escalation**

Converting many fine-grained locks into one coarse lock to reduce overhead.

### **b) Lock Compression**

Reducing space used in lock tables.

### **c) Optimistic Concurrency Control**

Assumes less conflict; reduces locking overhead.

### **d) Multiversion Concurrency Control (MVCC)**

Readers don’t block writers → higher concurrency.

### **e) Deadlock Prevention & Detection Algorithms**

Minimize performance degradation.

---

