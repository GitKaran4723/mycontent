# **🌟 Functional Dependencies in DBMS**

---

## **🔹 What is a Functional Dependency?**

A **Functional Dependency (FD)** is a fundamental concept in relational database theory that describes the **relationship between attributes** in a relation (table). It specifies how the value of one attribute (or a group of attributes) uniquely determines the value of another attribute.

In simple terms, a functional dependency exists when **one attribute depends on another** for its value. It helps in maintaining **data consistency**, **integrity**, and plays a key role in **normalization** (removing redundancy).

---

### **🧠 Formal Definition:**

Let **R** be a relation that contains attributes **A** and **B**.  
 We say **A functionally determines B** (written as **A → B**)  
 if and only if for every pair of tuples (rows) in **R**,  
 whenever the value of **A** is the same, the value of **B** is also the same.

That is:

If t₁\[A\] \= t₂\[A\], then t₁\[B\] \= t₂\[B\]

This means that **A uniquely identifies B** in the relation.

---

### **🧾 Example:**

| Roll\_No | Name | Department |
| ----- | ----- | ----- |
| 101 | Alice | CSE |
| 102 | Bob | ECE |
| 103 | Alice | CSE |

From the above table:

* **Roll\_No → Name**  
   Each roll number corresponds to a single name.

* **Roll\_No → Department**  
   Each roll number also belongs to only one department.

* **Name → Roll\_No** ❌  
   This is **not true**, because “Alice” appears more than once with different roll numbers.

Hence, **Roll\_No** uniquely determines both **Name** and **Department**.

---

## **⚙️ Importance of Functional Dependencies**

Functional dependencies are crucial because they:

1. **Define Relationships** – They specify how attributes are related within a relation.

2. **Ensure Data Consistency** – Prevents data anomalies (like redundancy and inconsistency).

3. **Guide Normalization** – Used to decompose relations into smaller ones to achieve higher normal forms.

4. **Help Identify Keys** – Assist in finding **candidate keys**, **primary keys**, and **super keys**.

5. **Reduce Redundancy** – Help in removing duplicate or unnecessary data in relational tables.


## **🧩 Types of Functional Dependencies**



### **1️⃣ Trivial Functional Dependency**

#### **📘 Definition:**

A functional dependency is said to be **trivial** when the dependent (right-hand side) attribute is **already included** in the determinant (left-hand side).

Formally, if **X → Y** and **Y ⊆ X**, then it is called a **Trivial Functional Dependency**.

#### **💡 Explanation:**

Trivial dependencies are always true for any relation because the right-hand attribute is already part of the left-hand side. They don’t provide new information about the relation.

#### **🧾 Example:**

* A → A

* AB → A

* ABC → AB

All the above are trivial dependencies because the right-hand attributes are subsets of the left-hand attributes.

---

### **2️⃣ Non-Trivial Functional Dependency**

#### **📘 Definition:**

A **Non-Trivial Functional Dependency** exists when the dependent (right-hand side) attribute is **not included** in the determinant (left-hand side).

Formally, if **X → Y** and **Y ⊄ X**, then it is **Non-Trivial**.

#### **💡 Explanation:**

These dependencies are meaningful because they provide actual relationships between different attributes in a table.

#### **🧾 Example:**

* Roll\_No → Name

* Emp\_ID → Department

Here, the right-hand sides (Name and Department) are not part of the left-hand side attributes, making them non-trivial dependencies.

---

### **3️⃣ Full Functional Dependency**

#### **📘 Definition:**

A **Full Functional Dependency** occurs when an attribute is functionally dependent on a set of attributes, and it **cannot be determined** by any **proper subset** of that set.

Formally, a dependency **A, B → C** is a **full dependency** if:

* A and B together determine C, but

* Neither A → C nor B → C holds individually.

#### **💡 Explanation:**

It ensures that all attributes on the left-hand side are necessary to determine the right-hand attribute.  
 If any one of them is removed and the dependency no longer holds, it is fully dependent.

#### **🧾 Example:**

Let’s say a student’s **grade** depends on both **StudentID** and **CourseCode**:

* (StudentID, CourseCode) → Grade  
   Here, Grade depends on both StudentID and CourseCode.  
   Neither StudentID alone nor CourseCode alone can determine Grade.  
   So it is a **full functional dependency**.

---

### **4️⃣ Partial Functional Dependency**

#### **📘 Definition:**

A **Partial Functional Dependency** exists when a **non-prime attribute** (an attribute that is not part of any candidate key) is functionally dependent on **part of a composite primary key**.

#### **💡 Explanation:**

This means the dependency can be determined by only a part (subset) of the primary key instead of the full key.  
 Partial dependencies are removed in **Second Normal Form (2NF)**.

#### **🧾 Example:**

If the primary key is (RollNo, SubjectCode):

* (RollNo, SubjectCode) → Marks

* RollNo → StudentName

Here, **StudentName** depends only on RollNo (part of the key), not on the entire composite key.  
 Hence, this is a **Partial Dependency**.

---

### **5️⃣ Transitive Functional Dependency**

#### **📘 Definition:**

A **Transitive Dependency** occurs when there is an **indirect relationship** between attributes.  
 If attribute **A** determines **B**, and **B** determines **C**, then **A** indirectly determines **C**.

Formally, if:

* A → B

* B → C  
   Then **A → C** is a **Transitive Dependency**.

#### **💡 Explanation:**

This type of dependency often leads to data redundancy and is removed in **Third Normal Form (3NF)**.

#### **🧾 Example:**

* Emp\_ID → Dept\_ID

* Dept\_ID → Dept\_Name  
   Therefore, Emp\_ID → Dept\_Name (Transitive dependency)

---

### **6️⃣ Multivalued Dependency (MVD)**

#### **📘 Definition:**

A **Multivalued Dependency** exists when, for a single value of an attribute, there are **multiple independent values** of another attribute.

It is represented as **X →→ Y**, which means Y is **multivalued dependent** on X.

#### **💡 Explanation:**

This occurs when two or more attributes are independent of each other but depend on the same key attribute.  
 It appears in **Fourth Normal Form (4NF)**.

#### **🧾 Example:**

For a person:

* A person can have multiple **phone numbers** and multiple **email addresses**.  
   Therefore:  
   **Person →→ Phone** and **Person →→ Email**

---

### 

### 

### 

### **7️⃣ Join Dependency**

#### **📘 Definition:**

A **Join Dependency** occurs when a relation can be **decomposed into two or more relations** and can be perfectly **reconstructed by joining them back** without any loss of information.

#### **💡 Explanation:**

It generalizes multivalued dependency and occurs in **Fifth Normal Form (5NF)** or **Project-Join Normal Form**.

#### **🧾 Example:**

If we have a relation R(A, B, C), and it can be divided into two relations R1(A, B) and R2(B, C),  
 and if the original relation R can be obtained back by joining R1 and R2,  
 then there exists a **Join Dependency**.

---

## **🧮 Armstrong’s Axioms (Rules for Functional Dependencies)**

**Armstrong’s Axioms** are a set of rules that are **sound and complete**, meaning:

* They **only derive correct** functional dependencies.  
* They can **derive all possible** correct FDs (closure).

They are used for:  
 * Testing FD implications  
 * Computing **attribute closure**  
 * Deriving **canonical covers**  
 * Aiding **normalization**  

![Image 3](https://lh3.googleusercontent.com/d/1EGstV2Qdm43QyhqWH5CVykY7XNDFN0hX)

* **Axiom of Reflexivity:** If A is a set of attributes and B is a subset of A, then A holds B. If B⊆A then A**→**B. This property is trivial property.  

* **Axiom of Augmentation:** If **A→B **holds and Y is the attribute set, then **AY→BY** also holds. That is adding attributes to dependencies, does not change the basic dependencies. If **A→B**, then **AC→BC** for any C.  

* **Axiom of Transitivity:** Same as the transitive rule in algebra, if **A→B** holds and **B→C** holds, then** A→C** also holds. **A→B** is called A functionally which determines B. If **X→Y** and** Y→Z**, then **X→Z.**

1. **Reflexivity**: Since any set of attributes determines its subset, we can immediately infer the following:

* **{A} → {A}** (A set always determines itself).  
* **{B} → {B}**.  
* **{A, C} → {A}**.

2. **Augmentation**: If we know that **{A} → {B}**, we can add the same attribute (or set of attributes) to both sides:

* From **{A} → {B}**, we can augment both sides with **{C}**: **{A, C} → {B, C}**.  
* From **{B} → {C}**, we can augment both sides with **{A}**: **{A, B} → {C, B}**.

3. **Transitivity**: If we know **{A} → {B}** and **{B} → {C}**, we can infer that:

* **{A} → {C}** (Using transitivity: **{A} → {B}** and **{B} → {C}**).

Although Armstrong's axioms are sound and complete, there are additional rules for functional dependencies that are derived from them. These rules are introduced to simplify operations and make the process easier.

## **🔁 Derived (Secondary) Rules**

1. **Union Rule:**  
    If X → Y and X → Z, then X → YZ.

2. **Decomposition Rule:**  
    If X → YZ, then X → Y and X → Z.

3. **Composition Rule:**  
    If X → Y and A → B, then XA → YB.

4. **Pseudo Transitivity Rule:**  
    If X → Y and YZ → W, then XZ → W.


## **Properties of Functional Dependencies**

* Define **keys and relationships** among attributes.
* Aid in **database normalization**.
* Help **remove redundancy** and maintain **data integrity**.
* Assist in **schema refinement** to design efficient databases.

---

