

---

# **Transaction Support in SQL** 

Transaction support in SQL enables a database to execute multiple operations as a **single, consistent, and reliable unit of work**. This ensures that even if errors, system failures, or interruptions occur, the database remains consistent.

A transaction may include several SQL statements such as INSERT, UPDATE, and DELETE, but they are treated as **one atomic action**.

---

# **1\. Purpose of Transaction Support**

SQL provides transaction support to:

* Maintain **data integrity**

* Prevent **partial updates**

* Handle **errors** safely

* Support **concurrent access** by multiple users

* Ensure the ACID properties of transactions

Without transaction control, even a small failure during a multi-step operation could lead to **data inconsistency**.

---

# **2\. Transaction Control Commands (TCL)**

SQL offers specific commands to manage the beginning, progress, and end of a transaction.

## **a) COMMIT**

* Permanently saves all the changes made in the current transaction.

* Once committed, the changes cannot be undone.

* Used when the user is confident the operations are correct.

**Concept:**  
 Commit marks the **successful completion** of a transaction.

---

## **b) ROLLBACK**

* Reverses all changes made during the current transaction.

* Used when errors occur, rules are violated, or the user wants to cancel the operation.

**Concept:**  
 Rollback ensures **error recovery** and prevents invalid data from entering the system.

---

## **c) SAVEPOINT**

* Creates a **checkpoint** inside a transaction.

* Allows the user to revert partially instead of rolling back the entire transaction.

**Concept:**  
 Savepoints provide **fine-grained control** within large transactions.

Example actions:

* Create SAVEPOINT → Perform more operations → Rollback only recent part if needed.

---

## **d) ROLLBACK TO SAVEPOINT**

* Reverts changes only up to a specific savepoint.

* Earlier changes remain untouched.

**Concept:**  
 Used to undo only a **specific portion** of a transaction.

---

## **e) SET TRANSACTION**

This command is used to define conditions or characteristics for a transaction.

It can specify:

* **Read or write mode**

* **Isolation level** (how independent a transaction is from others)

* **Access mode** (serializable, read committed, etc.)

**Concept:**  
 SET TRANSACTION controls the **behavior** and **safety level** of the transaction.

---

# **3\. How SQL Processes a Transaction**

A transaction generally follows these steps:

1. **Start transaction**  
    (explicitly using `START TRANSACTION;` or implicitly when SQL statements begin)

2. Perform multiple SQL operations

3. Check for correctness

4. If correct → **COMMIT**

5. If an error occurs → **ROLLBACK**

**Conceptually:**  
 A transaction is like a complete story—either fully accepted or completely erased.

---

# **4\. Autocommit Mode**

In systems like MySQL:

* Autocommit is ON by default.

* Each statement is automatically committed.

To control transactions manually, autocommit must be turned off.

**Concept:**  
 Autocommit forces each statement to act as an independent transaction unless disabled.

---

# **5\. Why Transaction Support Is Important**

Transaction support in SQL ensures:

* **Consistency:** Only valid data is stored

* **Recovery:** Errors do not damage data

* **Isolation:** Multiple users can work simultaneously

* **Reliability:** Operations complete safely

* **Atomicity:** All-or-nothing execution

Transactions are essential in banking, online shopping, ticket booking, and any system with multi-step operations.

---

