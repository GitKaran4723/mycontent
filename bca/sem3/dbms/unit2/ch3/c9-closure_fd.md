Sure Tinu 😊 Here are **well-formatted theoretical notes** on **Closure of Functional Dependencies (FD Closure)** in DBMS. You can directly use these in your notebook or assignments.

---

## **Closure of Functional Dependencies in DBMS**

### **1\. Functional Dependency (FD)**

A **Functional Dependency (FD)** is a relationship between attributes in a relation (table).  
 If an attribute **X** uniquely determines another attribute **Y**, then it is written as:

X→Y

This means: *If two tuples have the same values for X, they must have the same values for Y.*

---

## **2\. Closure of Functional Dependencies (F+)**

The **Closure of Functional Dependencies (F⁺)** is the **complete set** of all Functional Dependencies that can be **logically implied** from the given set of FDs **F**.

F+={All FDs that can be derived from F}

It helps in:

* **Checking if a decomposition is lossless**

* **Checking if a relation is in Normal Form**

* **Finding candidate keys**

---

## **3\. Closure of Attribute Set (X⁺)**

The **closure of an attribute set X**, written as **X⁺**, is the set of **all attributes that can be functionally determined** by X using the given FDs.

X+={All attributes determined by X}

### **Steps to Find Attribute Closure (X⁺):**

1. Start with **X⁺ \= X**

2. For each FD **A → B** in F:

   * If **A** ⊆ X⁺, then add **B** to X⁺

3. Repeat until no more attributes can be added.

---

## **4\. Armstrong’s Axioms (Inference Rules)**

Used to derive more FDs from given FDs.

| Rule | Name | Explanation |
| ----- | ----- | ----- |
| 1 | **Reflexivity** | If Y ⊆ X, then X → Y |
| 2 | **Augmentation** | If X → Y, then XZ → YZ |
| 3 | **Transitivity** | If X → Y and Y → Z, then X → Z |

### **Additional Rules Derived**

| Rule | Name | Example |
| ----- | ----- | ----- |
| Union | If X → Y and X → Z, then X → YZ |  |
| Decomposition | X → YZ implies X → Y and X → Z |  |
| Pseudotransitivity | If X → Y and YZ → W, then XZ → W |  |

---

## **5\. Example of Attribute Closure (X⁺)**

### **Given:**

Relation: **R(A, B, C, D)**  
 FDs:

1. A → B

2. B → C

3. C → D

### **Find: A⁺**

| Step | Reason | Closure |
| ----- | ----- | ----- |
| Start with A⁺ \= {A} | Initial | {A} |
| A → B | Add B | {A, B} |
| B → C | Add C | {A, B, C} |
| C → D | Add D | {A, B, C, D} |

### **Final Answer:**

A+={A,B,C,D}

Since A⁺ contains **all attributes**, **A is a Candidate Key**.

---

## **6\. Importance of Closure**

| Purpose | Explanation |
| ----- | ----- |
| **To find candidate keys** | If X⁺ \= all attributes, then X is a key |
| **To test equivalence of FD sets** | Check if FDs produce same closure |
| **For normalization** | Used in BCNF and 3NF tests |
| **For decomposition** | To verify lossless join and dependency preservation |

---

## **7\. Summary**

* **F⁺** \= All FDs derived from F.

* **X⁺ (attribute closure)** is used to check if **X is a key**.

* Armstrong’s axioms help derive new FDs.

