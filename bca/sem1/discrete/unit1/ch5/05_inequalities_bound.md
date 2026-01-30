# Inequalities & Bounds via Induction

Mathematical induction is not only used to prove equalities but is also widely applied to prove **inequalities** and **bounds** involving natural numbers. These proofs show that a given expression is **always greater than, less than, or bounded by** another expression for all ( n ) beyond a certain value.

Such proofs are common in:

* Algorithm analysis
* Number theory
* Series and sequences
* Discrete structures

---

## What Are Inequalities and Bounds?

### Inequality

An inequality is a mathematical statement comparing two expressions using symbols such as:
$
<,\ >,\ \le,\ \ge
$

Example:
$
2^n \ge n+1 \quad \text{for all } n \ge 0
$

---

### Bound

A **bound** restricts the value of an expression.

* **Upper bound:**
  $
  f(n) \le g(n)
  $
* **Lower bound:**
  $
  f(n) \ge g(n)
  $

Bounds are used to estimate the **growth** of functions.

---

## General Method for Proving Inequalities by Induction

To prove an inequality using induction, follow these steps:

1. **Base Case:**
   Verify the inequality for the smallest value of $ n $.

2. **Induction Hypothesis:**
   Assume the inequality holds for $ n = k $.

3. **Induction Step:**
   Use the assumption to prove the inequality for $ n = k+1 $.

4. **Conclusion:**
   Conclude that the inequality holds for all $ n \ge n_0 $.

---

### Example 1: Simple Inequality

### Statement

Prove that:
$
n^2 \ge n \quad \text{for all } n \ge 1
$

---

### Base Case

For ( n = 1 ):
$
1^2 = 1 \ge 1
$

True.

---

### Induction Hypothesis

Assume:
$
k^2 \ge k
$

---

### Induction Step

We must prove:
$
(k+1)^2 \ge k+1
$

Expand:
$
k^2 + 2k + 1
$

Using the hypothesis $ k^2 \ge k $:
$
k^2 + 2k + 1 \ge k + 2k + 1 = 3k + 1
$

Since $ 3k + 1 \ge k + 1 $ for all $ k \ge 1 $,
$
(k+1)^2 \ge k+1
$

Proved.

---



---

### Example 2: Proving a Lower Bound

### Statement

Prove that:
$
n! \ge 2^{n-1} \quad \text{for all } n \ge 1
$

---

### Base Case

For ( n = 1 ):
$
1! = 1 \ge 2^0 = 1
$

True.

---

### Induction Hypothesis

Assume:
$
k! \ge 2^{k-1}
$

---

### Induction Step

$
(k+1)! = (k+1)k!
$

Using the hypothesis:
$
\ge (k+1)2^{k-1}
$

Since $ k+1 \ge 2 $ for $ k \ge 1 $:
$
(k+1)2^{k-1} \ge 2 \cdot 2^{k-1} = 2^k
$

Hence proved.

---

### Example 5: Bounding a Sequence

### Statement

Prove that:
$
a_n = 3n + 2 \le 4n \quad \text{for all } n \ge 2
$

---

### Base Case

For ( n = 2 ):
$
a_2 = 8 \le 8
$

True.

---

### Induction Hypothesis

Assume:
$
a_k \le 4k
$

---

### Induction Step

$
a_{k+1} = 3(k+1) + 2 = 3k + 5
$

Using hypothesis:
$
3k + 5 \le 4k + 1 \le 4(k+1)
$

Proved.

---

## Techniques Commonly Used in Inequality Proofs

* Adding the same term to both sides
* Using known inequalities $e.g., ( k+1 \ge 2 )$
* Replacing expressions using the induction hypothesis
* Comparing growth rates (linear vs exponential)

---


## Applications of Inequalities & Bounds

* Algorithm time complexity
* Proofs of convergence
* Bounding recursive sequences
* Estimating sums and products

---

## Final Summary

* Induction is a powerful tool for proving inequalities and bounds.
* The induction hypothesis helps control expressions at the next step.
* Careful algebra and logical reasoning are essential.
* These proofs are foundational in discrete mathematics and computer science.

