# **1. Two-Phase Locking (2PL)**

## **Definition**

Two-Phase Locking (2PL) is a concurrency control protocol used in DBMS to ensure **conflict serializability** of transactions.  
It controls how locks are acquired and released so that the resulting schedule behaves like a serial (non-interleaved) schedule.

The basic principle is that a transaction’s lifetime is divided into two distinct, non-overlapping phases:

## **Phases of 2PL**

### **1\. Growing Phase**

* The transaction is allowed to **acquire locks** (shared or exclusive).

* It is **not allowed to release** any locks during this phase.

### **2\. Shrinking Phase**

* The transaction can **release locks**.

* It **cannot acquire any new locks** after it begins releasing.

This lock discipline prevents circular wait patterns and ensures that the final schedule is serializable.

---

## **Types of Two-Phase Locking**

### **1\. Basic 2PL**

* Only requires adherence to the two phases: acquire in the growing phase and release in the shrinking phase.

* Guarantees conflict serializability but may still lead to deadlocks.

---

### **2\. Conservative (Static) 2PL**

* The transaction requests **all required locks at the beginning**, before execution starts.

* If all locks cannot be granted, the transaction waits.

* Prevents deadlocks completely, but reduces concurrency as transactions may hold locks longer than necessary.

---

### **3\. Strict 2PL**

* All **exclusive (write) locks** are held until the transaction either **commits or rolls back**.

* Ensures **recoverability** and prevents **cascading rollbacks**, because other transactions cannot read uncommitted data.

---

### **4\. Rigorous 2PL**

* The strongest form of 2PL.

* A transaction holds **all locks (shared and exclusive)** until the end of the transaction (commit or rollback).

* Ensures a very high level of isolation and simplifies recovery.

---

## **Example**

Consider two transactions:

* **T1:** Reads and updates data item A

* **T2:** Reads and updates data item B

Steps:

1. T1 acquires lock on A and updates it.

2. T2 acquires lock on B and updates it.

3. If T1 later needs B and T2 needs A, the 2PL protocol ensures that conflicts are resolved in a serializable order.  
    Their lock acquisition patterns will enforce an ordering such as T1 → T2 or T2 → T1.

---

# **2\. Serializability**

## **Definition**

Serializability is the concept used to determine whether a **concurrent schedule of transactions** is correct.  
 A schedule is considered serializable if its outcome is the **same as some serial schedule**, where transactions execute one after another without interleaving.

Serializability ensures consistency in concurrent environments and is the theoretical benchmark for correctness.

---

## **Types of Serializability**

### **1\. Conflict Serializability**

A schedule is conflict serializable if it can be transformed into a serial schedule by swapping non-conflicting operations.

Two operations conflict if:

* They belong to different transactions,

* They access the same data item, and

* At least one of them is a write operation.

Conflict serializability is typically checked using a **precedence graph (serialization graph)**:

* Each transaction is a node.

* A directed edge indicates a conflict ordering.

* If the graph has **no cycles**, the schedule is conflict serializable.

---

### **2\. View Serializability**

Two schedules are view equivalent (and thus view serializable) if:

1. They read the **same initial values**,

2. Each read operation reads the **same value written by the same transaction**, and

3. The **final write** on each data item is performed by the same transaction.

View serializability is **more general** than conflict serializability, meaning every conflict-serializable schedule is also view-serializable, but not vice versa.

---

## **Example**

Schedule:

* **T1:** Read(A), Write(A)

* **T2:** Read(A), Write(A)\*\*

If T1 writes A first and T2 overwrites it afterward, the result should reflect the serial order **T1 → T2**.  
 If the schedule produces the same final database state and the same read/write relationships as this serial order, it is serializable.

---

---

# **Recovery Techniques**

Crash recovery mainly depends on **log-based recovery**, following the **Write-Ahead Logging (WAL)** principle.

---

## **1\. Write-Ahead Logging (WAL)**

### **Definition**

Before any change is applied to the database, it must first be recorded in a **log file** on stable storage.

### **Purpose**

* Ensures **durability**: committed changes are never lost.

* Ensures **recoverability**: uncommitted changes can be undone.

### **Log Contains:**

* Transaction ID

* Data item modified

* Old value

* New value

### **During Recovery:**

* **Redo** all committed transactions

* **Undo** all incomplete (uncommitted) transactions

---

## **2\. Checkpoints (Optional but useful)**

### **Definition**

A checkpoint is a point where the DBMS saves the current state of the database and logs, so recovery does not need to scan the entire log from the beginning.

### **Recovery using Checkpoint:**

1. Find the most recent checkpoint.

2. Redo all committed transactions after it.

3. Undo all uncommitted transactions.

---

# **Summary Table**

| Failure Type | Cause | Effect | Recovery Action |
| ----- | ----- | ----- | ----- |
| Transaction Failure | Logical error, deadlock | One transaction fails | Rollback the transaction |
| System Crash | Power/OS failure | RAM data lost | Use logs to redo/undo |
| Disk Failure | Disk crash, corruption | Data permanently lost | Restore backup \+ redo |
| Application Failure | Program crash | Partial updates | Rollback incomplete operations |

---

