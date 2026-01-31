# **Induction on Sequences & Sums**

written in **clear paragraphs with worked examples**, exactly how it’s expected in **Discrete Mathematics / Engineering Maths**.

---

## Induction on Sequences & Sums

Mathematical induction is widely used to prove **formulas involving sequences and sums**. Many expressions in discrete mathematics—such as arithmetic series, geometric series, and recursively defined sequences—depend on the natural number ( n ). Induction provides a systematic way to verify that such formulas are valid for **all natural numbers**.

When applying induction to sequences and sums, the goal is to prove that a **closed-form formula** correctly represents the sum or term for every value of ( n ).

---

## General Method for Induction on Sums

To prove a summation formula using induction, we follow these steps:

1. **Base Case:** Verify the formula for the smallest value of ( n ).
2. **Induction Hypothesis:** Assume the formula is true for ( n = k ).
3. **Induction Step:** Use the assumption to prove the formula for ( n = k+1 ).
4. **Conclusion:** Conclude the formula holds for all natural numbers.

---

### Example 1: Sum of First ( n ) Natural Numbers

### Statement

Prove that:
$
1 + 2 + 3 + \dots + n = \frac{n(n+1)}{2}, \quad n \ge 1
$

---

### Base Case

For ( n = 1 ):

LHS:
$
1
$

RHS:

$
\frac{1(1+1)}{2} = 1
$

Thus, the statement is true for ( n = 1 ).

---

### Induction Hypothesis

Assume the statement is true for ( n = k ), i.e.,
$
1 + 2 + 3 + \dots + k = \frac{k(k+1)}{2}
$

---

### Induction Step

We prove the statement for ( n = k+1 ):

$
1 + 2 + \dots + k + (k+1)
$

Using the induction hypothesis:

$
\frac{k(k+1)}{2} + (k+1)
$

Factor out $ (k+1) $:

$
(k+1)\left(\frac{k}{2} + 1\right)
$

$
= \frac{(k+1)(k+2)}{2}
$

This is exactly the required RHS.

---

### Conclusion

By mathematical induction, the formula is true for all $ n \ge 1 $.

---

### Example 2: Sum of First ( n ) Odd Numbers

### Statement

Prove that:
$
1 + 3 + 5 + \dots + (2n - 1) = n^2
$

---

### Base Case

For ( n = 1 ):

LHS:
$
1
$

RHS:
$
1^2 = 1
$

Base case holds.

---

### Induction Hypothesis

Assume for ( n = k ):
$
1 + 3 + 5 + \dots + (2k - 1) = k^2
$

---

### Induction Step

For $ n = k+1 $:

$
1 + 3 + \dots + (2k - 1) + (2k + 1)
$

Substitute the induction hypothesis:
$
k^2 + (2k + 1)
$

$
= (k+1)^2
$

Hence, true for ( k+1 ).

---

### Conclusion

The statement holds for all $ n \ge 1 $.

---

### Example 3: Induction on Arithmetic Series

### Statement

Prove that:
$
\sum_{i=1}^{n} (2i - 1) = n^2
$

This is another form of the odd number sum and follows the same induction structure.

---

### Example 4: Induction on Geometric Series

### Statement

Prove that:
$
1 + 2 + 4 + 8 + \dots + 2^n = 2^{n+1} - 1
$

---

### Base Case

For ( n = 0 ):

LHS:
$
1
$

RHS:
$
2^{1} - 1 = 1
$

---

### Induction Hypothesis

Assume for ( n = k ):
$
1 + 2 + 4 + \dots + 2^k = 2^{k+1} - 1
$

---

### Induction Step

For $ n = k+1 $:

$
(2^{k+1} - 1) + 2^{k+1}
$

$
= 2 \cdot 2^{k+1} - 1
$

$
= 2^{k+2} - 1
$

Proved.

---

## Induction on Sequences

Induction is also used to prove formulas for **terms of sequences**, especially when sequences are defined recursively.

---

### Example 5: Induction on a Sequence Formula

### Given Sequence

$
a_1 = 1, \quad a_n = a_{n-1} + 2
$

### Claim

$
a_n = 2n - 1
$

---

### Base Case

For ( n = 1 ):

$
a_1 = 1 = 2(1) - 1
$

---

### Induction Hypothesis

Assume:
$
a_k = 2k - 1
$

---

### Induction Step

$
a_{k+1} = a_k + 2
$

$
= (2k - 1) + 2
$

$
= 2(k+1) - 1
$

Hence proved.

---

## Why Induction is Important for Sequences & Sums

* Helps verify **closed formulas**
* Essential for **series evaluation**
* Useful in **recurrence relations**
* Common in **exam problems**
* Forms the foundation for algorithm analysis



## Summary

* Induction is ideal for proving formulas involving sequences and sums.
* The method relies on a verified base case and a correct inductive step.
* Many important formulas such as $ \sum n $, $ \sum 2^n $, and recursive sequences are proved using induction.

