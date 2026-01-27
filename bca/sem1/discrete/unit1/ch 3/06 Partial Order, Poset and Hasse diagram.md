

# **Partial Order**

A **partial order** is a relation (R) on a set (A) that satisfies **three properties**:

**Reflexive:**  
   ∀ a ∈ A, ( a, a ) ∈ R  
**Antisymmetric:**  
   ( a, b ) ∈ R and ( b, a ) ∈ R ⇒ a = b  
**Transitive:**  
   ( a, b ) ∈ R and ( b, c ) ∈ R ⇒ ( a, c ) ∈ R

A relation satisfying these properties is called a **partial ordering**.

### **Example of Partial Orders**

Consider the set P ={ 1, 2, 3 } with the relation ≤ defined as the usual numerical order:

* **Reflexivity:** 1 ≤ 1, 2 ≤ 2, 3 ≤ 3\.  
* **Antisymmetry:** If a ≤ b and b ≤ a, then a = b.  
* **Transitivity:** If 1 ≤ 2 and 2 ≤ 3, then 1 ≤ 3\.

---

# **Poset (Partially Ordered Set)**

A **poset** is a pair  (A,R)  
where:

* (A) is a non-empty set, and  
* (R) is a **partial order** on (A).

In simple words:  
A **poset** is a set together with a partial order defined on it.

**Example:  ( { 1, 2, 3 }, ≤ )**  is a poset.

## **Types of Elements in a Poset**

### **(a) Comparable Elements**

Two elements **a, b ∈ P** are **comparable** if

**a ≤ b or b ≤ a**

**Example:**  
 In ( N, ≤ ), 2 and 5 are comparable since 2 ≤ 5

---

### **(b) Incomparable Elements**

Two elements **a, b ∈ P** are **incomparable** if neither

**a ≤ b nor b ≤ a**

**Example:**  
 Let P = { a, b, c } with relations a ≤ c, b ≤ c

 Then a and b are incomparable

---

### **(c) Minimal Element**

An element m ∈ P is **minimal** if there is **no element smaller than it**

Formally,  
**m is minimal ⟺ ∄ x ∈ P  such that x < m**

---

**Example**

Consider the poset P = { a, b, c }  
with relations: a ≤ c, b ≤ c   
Here:

* There is no element smaller than (a)  
* There is no element smaller than (b)

So, (a) and (b) are minimal elements.

### **(d) Maximal Element**

An element M∈P is **maximal** if there is **no element greater than it**  
Formally,  
**m is maximal ⟺ ∄ x ∈ P such that m < x**

**Example**

Consider the poset P = { a, b, c }  
with relations: a ≤ c, b ≤ c  
Here:

* There is no element greater than c

So, c is a maximal element.

---

# **Hasse Diagram**

A **Hasse diagram** is a **graphical representation** of a finite poset.

**Construction rules:**

1. Each element of the set is represented by a point.  
2. If ( a < b ) and there is no element (c) such that ( a < c < b ), draw a line upward from (a) to (b).  
3. Reflexive and transitive relations are omitted.  
4. Larger elements are placed higher than smaller ones.

---

