## **1. Introduction to Sets**

A **set** is a well-defined collection of distinct objects, called **elements** or **members**.

* **Well-defined** means that there is no ambiguity about whether an object belongs to the set or not.
* Objects in a set are **unique** — no repetitions.

**Notation:**
We usually denote sets using **capital letters** (A, B, C, …) and elements using **lowercase letters** (a, b, x, y, …).

If $x$ is an element of set $A$, we write:

$$
x \in A
$$

If $x$ is not in $A$, we write:

$$
x \notin A
$$

---

## **2. Ways of Representing Sets**

### **2.1 Roster (Tabular) Form**

List all elements explicitly inside curly braces `{ }`, separated by commas.
**Example:**

$$
A = \\{2, 4, 6, 8\\}
$$

Here, $A$ is the set of first four even numbers.

⚠ **Order doesn’t matter**: $\\{2, 4, 6, 8\\} = \\{8, 6, 4, 2\\}$
⚠ **No repetition**: $\\{1, 2, 2, 3\\} = \\{1, 2, 3\\}$

---

### **2.2 Set-Builder Form**

Describe the property that elements must satisfy.
**General form:**

$$
\\{ x \ | \ \text{property of } x \\}
$$

The vertical bar “$|$” (or colon “:”) means “such that”.

**Example:**

$
B = \\{ x \ | \ x \text{ is an even natural number < 10} \\}
$

This means $B = \\{2, 4, 6, 8\\}$.

---

### **2.3 Interval Notation** (for Real Numbers)

Used to represent **continuous** sets of numbers.

* **(a, b)** — open interval: $a < x < b$
* **\[a, b]** — closed interval: $a \le x \le b$
* **(a, b]** — half-open interval: $a < x \le b$
* **\[a, b)** — half-open interval: $a \le x < b$
* **$(-\infty, b)$** or **$(a, \infty)$** — unbounded intervals

**Example:**

$$
[0, 5] = \\{ x \in \mathbb{R} \ | \ 0 \le x \le 5 \\}
$$

---

## **3. Standard Sets and Their Symbols**

| Symbol         | Name              | Meaning                                                   |
|----------------|-------------------|-----------------------------------------------------------|
| $\mathbb{N}$   | Natural numbers   | $\\{\,1,2,3,\dots\,\\}$ (sometimes includes $0$)           |
| $\mathbb{Z}$   | Integers          | $\\{\dots,-2,-1,0,1,2,\dots\\}$                            |
| $\mathbb{Z}^+$ | Positive integers | $\\{\,1,2,3,\dots\,\\}$                                    |
| $\mathbb{Z}^-$ | Negative integers | $\\{\dots,-3,-2,-1\\}$                                     |
| $\mathbb{Q}$   | Rational numbers  | $\\{\,\frac{p}{q}\mid p,q\in\mathbb{Z},\ q\ne 0\,\\}$      |
| $\mathbb{R}$   | Real numbers      | All rationals and irrationals                            |
| $\mathbb{C}$   | Complex numbers   | $\\{\,a+bi\mid a,b\in\mathbb{R}\,\\}$                      |
| $\mathbb{E}$   | Even integers     | $\\{\dots,-4,-2,0,2,4,\dots\\}$                            |
| $\mathbb{O}$   | Odd integers      | $\\{\dots,-3,-1,1,3,\dots\\}$                              |
| $\varnothing$  | Empty set         | Set with no elements                                     |

---

## **4. Important Notation Variations**

### **4.1 Membership**

* $x \in A$: “x is an element of A”
* $x \notin A$: “x is not an element of A”

### **4.2 Subsets**

* $A \subseteq B$: All elements of A are in B
* $A \subset B$: A is a **proper subset** of B (A ≠ B)
* $A \nsubseteq B$: A is **not** a subset of B

### **4.3 Universal Set**

* Denoted $U$ — the set containing all elements under consideration in a given context.
  **Example:** In discussing positive integers less than 20, $U = \\{1, 2, \dots, 19\\}$.

### **4.4 Cardinality**

* Number of elements in a set $A$: $n(A)$ or $|A|$.
  Example: If $A = \\{2, 4, 6, 8\\}$, then $|A| = 4$.

---

## **5. Special Types of Sets & Their Notations**

* **Singleton set**: $\\{a\\}$ — has exactly one element.
* **Finite set**: $|A|$ is finite.
* **Infinite set**: $|A|$ is infinite (e.g., $\mathbb{N}$).
* **Equal sets**: $A = B$ if every element of A is in B and vice versa.
* **Disjoint sets**: $A \cap B = \emptyset$.

---

## **6. Example Practice**

1. Roster form: $C = \\{1, 4, 9, 16, 25\\}$
   Set-builder form: $C = \\{x \ | \ x = n^2, n \in \mathbb{N}, 1 \le n \le 5\\}$

2. If $U = \mathbb{N}$ and $A = \\{x \ | \ x \le 10, x \text{ is odd}\\}$,
   then $A = \\{1, 3, 5, 7, 9\\}$.

---

## **7. Key Takeaways**

* Sets are always enclosed in `{ }`.
* Use **roster form** when elements are few and known.
* Use **set-builder form** when elements follow a rule or are too many to list.
* Know standard symbols ($\mathbb{N}, \mathbb{Z}, \mathbb{Q}, \mathbb{R}, \mathbb{C}$).
* Be precise with membership and subset symbols.

---
