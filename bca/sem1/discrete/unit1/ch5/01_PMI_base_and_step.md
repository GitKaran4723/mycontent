# Principle of Mathematical Induction (PMI)

The **Principle of Mathematical Induction** is a powerful proof technique used to prove that a given statement is true for **all natural numbers** (or integers starting from a fixed value, usually 1).

It is especially useful for proving:

* Algebraic identities
* Inequalities
* Divisibility statements
* Summation formulas
* Properties defined recursively

PMI works like a **domino effect**: if the first domino falls and each domino knocks down the next one, then all dominoes will fall.

---

## Structure of Mathematical Induction

The principle consists of **two essential steps**:

1. **Base Step (Base Case)**
2. **Induction Step (Inductive Step)**

Only when **both steps are satisfied** can we conclude that the statement is true for all natural numbers.

---

## 1. Base Step (Base Case)

### Definition

The **base step** is used to verify that the given statement is true for the **smallest value** of the variable usually ( n = 1 ), sometimes ( n = 0 ).

### Purpose

* It provides the **starting point** for induction.
* Without a true base case, induction cannot proceed.

### Example

**Statement:**
Prove that
$
1 + 2 + 3 + \dots + n = \frac{n(n+1)}{2}
$

**Base Case:**
Let ( n = 1 )

LHS:
$
1
$

RHS:

$
\frac{1(1+1)}{2} = \frac{2}{2} = 1
$

Since LHS = RHS, the statement is **true for ( n = 1 )**.


---

## 2. Induction Step (Inductive Step)

### Definition

In the induction step, we **assume** that the statement is true for some arbitrary natural number ( k ), and then **prove** that it is true for ( k+1 ).

This step has two parts:

1. **Induction Hypothesis**
2. **Inductive Proof**

---

### (a) Induction Hypothesis

We assume the statement is true for ( n = k ).

For the example above, assume:

$
1 + 2 + 3 + \dots + k = \frac{k(k+1)}{2}
$

This assumption is called the **induction hypothesis**.

 Note:
We do **not** prove this step — we **assume** it is true.

---

### (b) Inductive Proof

Now we prove that the statement is true for ( n = k+1 ).

We need to show:
$
1 + 2 + 3 + \dots + k + (k+1) = \frac{(k+1)(k+2)}{2}
$

Start with the LHS:
$
(1 + 2 + 3 + \dots + k) + (k+1)
$

Using the induction hypothesis:

$
\frac{k(k+1)}{2} + (k+1)
$

Factor out ( (k+1) ):
$
(k+1)\left(\frac{k}{2} + 1\right)
$

$
= (k+1)\left(\frac{k+2}{2}\right)
$

$
= \frac{(k+1)(k+2)}{2}
$

This matches the RHS.

Therefore, the statement is true for ( n = k+1 ).

---

## Final Conclusion

Since:

* The statement is **true for the base case** ( n = 1 ), and
* The truth of the statement for ( n = k ) implies its truth for ( n = k+1 ),

By the **Principle of Mathematical Induction**, the statement is **true for all natural numbers ( n )**.

---

## General Format of PMI Proof (Exam-Ready)

1. **Statement:** Clearly state what is to be proved.
2. **Base Case:** Verify the statement for the smallest value of ( n ).
3. **Induction Hypothesis:** Assume the statement is true for ( n = k ).
4. **Induction Step:** Prove it is true for ( n = k+1 ).
5. **Conclusion:** Hence, by PMI, the statement is true for all $ n \in \mathbb{N} $.

---

