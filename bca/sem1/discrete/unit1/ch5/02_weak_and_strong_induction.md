# Weak Induction vs Strong Induction

Mathematical induction is a proof technique used to prove statements that depend on natural numbers. There are **two main forms** of induction:

1. **Weak (Simple) Induction**
2. **Strong (Complete) Induction**

Both methods are logically equivalent, but they differ in how much information we assume during the inductive step.

---

## 1. Weak Induction (Simple Induction)

### Definition

**Weak induction** proves a statement $ P(n) $ for all $ n \ge n_0 $ by assuming the statement is true for **only one value**, namely ( n = k ), and then proving it for ( n = k+1 ).

### Steps in Weak Induction

1. **Base Case:** Prove $ P(n_0) $ is true.
2. **Induction Hypothesis:** Assume ( P(k) ) is true for some $ k \ge n_0 $.
3. **Induction Step:** Prove $ P(k+1) $ is true using $ P(k) $.

---

### Example (Weak Induction)

**Statement:**
Prove that

$
\sum_{i=1}^{n} i = \frac{n(n+1)}{2}, \quad n \ge 1
$

**Base Case:**
For ( n = 1 ):

$
1 = \frac{1(1+1)}{2} = 1
$

**Induction Hypothesis:**
Assume the statement is true for ( n = k ):

$
\sum_{i=1}^{k} i = \frac{k(k+1)}{2}
$

**Induction Step:**

$
\sum_{i=1}^{k+1} i = \sum_{i=1}^{k} i + (k+1)
$

$
= \frac{k(k+1)}{2} + (k+1)
$

$
= \frac{(k+1)(k+2)}{2}
$

Hence, true for all $ n \ge 1 $.

---

### When to Use Weak Induction

* Algebraic identities
* Summation formulas
* Simple inequalities
* Problems where $ P(k) $ alone is sufficient to prove $ P(k+1) $

---

## 2. Strong Induction (Complete Induction)

### Definition

**Strong induction** proves a statement $ P(n) $ by assuming that the statement is true for **all values from the base case up to ( k )**, and then proving it for ( k+1 ).

That is, we assume:

$
P(n_0), P(n_0+1), \dots, P(k)
$

---

### Steps in Strong Induction

1. **Base Case:** Prove $ P(n_0) $ is true.
2. **Induction Hypothesis:** Assume $ P(n) $ is true for **all** $ n_0 \le n \le k $.
3. **Induction Step:** Prove $ P(k+1) $ using the assumption for all previous values.

---

### Example (Strong Induction)

**Statement:**
Prove that every integer $ n \ge 2 $ can be written as a product of prime numbers.

**Base Case:**
For ( n = 2 ):
2 is a prime number. Hence true.

**Induction Hypothesis:**
Assume that every integer ( m ) such that
$
2 \le m \le k
$
can be expressed as a product of primes.

**Induction Step:**
Consider ( k+1 ):

* If ( k+1 ) is prime, it is already a product of primes.
* If ( k+1 ) is composite, then:
  $
  k+1 = a \times b
  $
  where $ 2 \le a, b \le k $

By the induction hypothesis, both ( a ) and ( b ) can be written as products of primes.
Hence, ( k+1 ) can also be written as a product of primes.

 Therefore, the statement holds for all $ n \ge 2 $.

---

### When to Use Strong Induction

* Problems involving **factorization**
* Recursive definitions
* Problems where $ P(k+1) $ depends on **multiple earlier cases**
* Number-theoretic proofs



---

### Important Note

Although **strong induction appears more powerful**, both weak and strong induction are **logically equivalent**.
Any statement proved using strong induction can also be proved using weak induction, and vice versa.

---

### Conclusion

* **Weak induction** assumes the statement for one step and proves the next.
* **Strong induction** assumes the statement for all previous steps and proves the next.
* Choose the method based on **how much prior information is needed** to complete the inductive step.
