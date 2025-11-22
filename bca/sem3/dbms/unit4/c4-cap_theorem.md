---

# **CAP Theorem (Brewer’s Theorem)**

The **CAP Theorem**, proposed by **Eric Brewer in 2000** and formally proven by **Gilbert and Lynch in 2002**, is a fundamental principle in distributed database systems.  
 It states that **a distributed system can guarantee only two out of the following three properties at the same time**:

---

## **1\. Consistency (C)**

Consistency means that **every read operation returns the most recent write** or an error.  
 All nodes in the system must always display the same version of data.

### **Characteristics**

* Guarantees up-to-date, correct data on all nodes

* Prevents stale or outdated reads

* Similar to behavior in traditional RDBMS

### **Example:**

In a banking application, if you transfer **₹1000**, the updated balance must appear immediately on all servers and devices.

---

## **2\. Availability (A)**

Availability ensures that the system **always returns a response** to every request, regardless of the state of individual nodes.

### **Characteristics**

* System remains operational at all times

* Responses may contain older (not the latest) values

* Prioritizes uptime over accuracy

### **Example:**

A social media feed always loads, even if one of the servers is temporarily not updated.

---

## **3\. Partition Tolerance (P)**

Partition Tolerance means the system continues to function **even when communication between nodes is lost** or interrupted due to network failure.

### **Characteristics**

* System must operate despite node or network failures

* Ensures distributed systems remain resilient

* **Unavoidable in real-world networks**, so P is considered essential

---

# **Why Only Two Out of Three?**

In distributed systems, network failures (partitions) are unavoidable.  
 Thus, when a partition occurs, the system must **choose between:**

* **Consistency** (return only the latest data)

* **Availability** (always respond)

It cannot provide both simultaneously during a partition.

### **Explanation**

* **C \+ A (Consistency \+ Availability)** → Only possible if there is *no* partition.

* **C \+ P (Consistency \+ Partition Tolerance)** → Some requests may be rejected to maintain consistency.

* **A \+ P (Availability \+ Partition Tolerance)** → System keeps running but may return stale data.

---

# **CAP Theorem Combinations**

## **1\. CA – Consistency \+ Availability**

* Does *not* tolerate partitions

* Works only when the network is perfect

* Usually applies to **single-node or tightly coupled systems**

**Example:**  
 Traditional RDBMS like Oracle, MySQL (in single-server mode)

---

## **2\. CP – Consistency \+ Partition Tolerance**

* Availability is sacrificed

* During network failures, the system may refuse requests to ensure consistent data

**Examples:**  
 MongoDB, HBase, Redis (when configured for strong consistency)

---

## **3\. AP – Availability \+ Partition Tolerance**

* Consistency may be temporarily sacrificed

* System continues running and responding, even during partitions

* Data may be eventually consistent

**Examples:**  
 Cassandra, DynamoDB, Couchbase

---

# **Real-World Analogy: ATM Network**

Think of how ATMs work:

* **Consistency** → Every ATM shows the same, correct account balance

* **Availability** → You can withdraw cash anytime

* **Partition Tolerance** → ATMs still work even when some servers are disconnected

You **cannot** have all three at the same time:

* If ATM stays *available* during a network issue, it may show old balance → **AP**

* If ATM enforces *consistency*, it may stop service until connection recovers → **CP**

---

