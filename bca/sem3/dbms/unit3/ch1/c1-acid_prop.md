# **UNIT – III: Transaction Management** 

---

## **ACID Properties**

In Database Management Systems (DBMS), ACID properties ensure reliable processing of transactions and protect the database from inconsistencies, especially when multiple transactions run simultaneously or when failures occur.

---

### **1\. Atomicity**

**Definition:**  
 Atomicity ensures that a transaction is executed completely or not executed at all. It treats a transaction as a single, indivisible unit of work.

If any one operation within the transaction fails, the entire transaction is rolled back, and the database returns to its previous consistent state.

**Example:**  
 During a fund transfer of ₹1000 from Account A to Account B, both the debit from A and the credit to B must occur. If the debit operation fails, the credit operation should not be applied.

---

### **2\. Consistency**

**Definition:**  
 Consistency ensures that a transaction transforms the database from one valid state to another valid state, maintaining all predefined rules, constraints, and integrity conditions.

**Example:**  
 If the total balance across two accounts is ₹3000 before a transfer, it should remain ₹3000 after the transaction, regardless of how the individual amounts change.

---

### **3\. Isolation**

**Definition:**  
 Isolation ensures that each transaction executes independently of other concurrent transactions. The intermediate states of one transaction must not be visible to others.

**Example:**  
 If two users attempt to book the last available ticket, proper isolation ensures that only one succeeds. Similarly, if two users perform balance operations simultaneously, each transaction should execute as though it were the only one running.

---

### **4\. Durability**

**Definition:**  
 Durability ensures that once a transaction has been committed, its effects are permanently recorded in the database, even in the case of a system crash or power failure.

---

# 

