# **Crash Recovery in DBMS**

## **What is Crash Recovery?**

Crash recovery in a DBMS is the process of **restoring the database to a consistent and correct state** after an unexpected failure.  
 Failures can occur due to:

* System crash (power failure, OS crash, hardware failure)

* Transaction failure (logical errors, deadlocks)

* Media failure (disk crash, file corruption)

* Application/process failure

**Goal:**  
 To ensure that the database still satisfies **ACID properties** even after a crash.

---

## **Types of Failures Requiring Recovery**

### **1\. Transaction Failure**

* A single transaction fails due to logical errors, invalid operations, or deadlocks.

* **Recovery:** Roll back only the failed transaction.

* Database remains consistent for other transactions.

---

### **2\. System Crash**

* Volatile memory (RAM) content is lost, but disk data remains safe.

* Example: sudden shutdown, power loss, OS crash.

* Incomplete transactions may remain in uncertain states.

**Recovery:**

* Use logs to:

  * **Undo** uncommitted transactions

  * **Redo** committed transactions that were not written to disk yet

---

### **3\. Disk Failure / Media Failure**

* Permanent loss of stored data due to disk crash, file corruption, or hardware damage.

* This is more severe than a system crash.

**Recovery:**

* Restore the database from the **latest backup**.

* **Redo** committed transactions using log records to bring the database up to date.

---

### **4\. Application / Process Failure**

* A program or process accessing the DB crashes unexpectedly.

* Leaves partial or incomplete updates.

**Recovery:**

* Roll back the incomplete operations from that process.

---

