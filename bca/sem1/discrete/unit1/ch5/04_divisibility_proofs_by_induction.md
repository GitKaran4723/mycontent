# Divisibility Proofs by Induction

In number theory and discrete mathematics, many statements involve **divisibility**, such as showing that an expression is divisible by a given integer for **all natural numbers**. Mathematical induction is one of the most effective methods to prove such statements.

A divisibility statement usually has the form:
$
f(n) \text{ is divisible by } k \quad \text{for all } n \ge n_0
$
which means:
$
k \mid f(n)
$

---

## General Method for Divisibility Proofs by Induction

To prove that $ k \mid f(n) $ for all $ n $, we proceed as follows:

1. **Base Case:** Verify that $ k \mid f(n_0) $.
2. **Induction Hypothesis:** Assume $ k \mid f(k) $, i.e.,
    $
   f(k) = k \cdot m \quad \text{for some integer } m
   $
3. **Induction Step:** Show that $ k \mid f(k+1) $ by expressing $ f(k+1) $ in terms of $ f(k) $.
4. **Conclusion:** By induction, the statement holds for all $ n \ge n_0 $.

---

### Example 1: Proving Divisibility by 3

### Statement

Prove that:
$
3 \mid (2^{2n} - 1) \quad \text{for all } n \ge 1
$

---

### Base Case

For ( n = 1 ):

$
2^{2(1)} - 1 = 4 - 1 = 3
$

Since $ 3 \mid 3 $, the base case is true.

---

### Induction Hypothesis

Assume that for some ( n = k ):
$
2^{2k} - 1 = 3m \quad \text{for some integer } m
$

---

### Induction Step

We must show:
$
3 \mid (2^{2(k+1)} - 1)
$

$
2^{2(k+1)} - 1 = 2^{2k+2} - 1
$

Rewrite:
$
= 4 \cdot 2^{2k} - 1
$

Add and subtract 4:
$
= 4(2^{2k} - 1) + 3
$

Using the induction hypothesis:
$
= 4(3m) + 3 = 3(4m + 1)
$

Thus, divisible by 3.

---

### Conclusion

By mathematical induction,
$
3 \mid (2^{2n} - 1) \quad \text{for all } n \ge 1
$

---

### Example 2: Divisibility by 5

### Statement

Prove that:
$
5 \mid (n^5 - n) \quad \text{for all } n \ge 1
$

---

### Base Case

For ( n = 1 ):

$
1^5 - 1 = 0
$

Since 5 divides 0, the base case holds.

---

### Induction Hypothesis

Assume:
$
k^5 - k = 5m \quad \text{for some integer } m
$

---

### Induction Step

Consider:
$
(k+1)^5 - (k+1)
$

Expand:
$
k^5 + 5k^4 + 10k^3 + 10k^2 + 5k + 1 - k - 1
$

$
= (k^5 - k) + 5(k^4 + 2k^3 + 2k^2 + k)
$

By hypothesis, $ k^5 - k $  is divisible by 5, and the remaining term is clearly divisible by 5.

Hence proved.

---

### Example 3: Divisibility Involving Sums

### Statement

Prove that:
$
6 \mid (n^3 - n) \quad \text{for all } n \ge 1
$

---

### Base Case

For ( n = 1 ):

$
1^3 - 1 = 0
$

Divisible by 6.

---

### Induction Hypothesis

Assume:
$
k^3 - k = 6m
$

---

### Induction Step

$
(k+1)^3 - (k+1)
$

$
= k^3 + 3k^2 + 3k + 1 - k - 1
$

$
= (k^3 - k) + 3k(k+1)
$

Since one of $ k $ or $ k+1 $ is even, $ 3k(k+1) $ is divisible by 6.

Hence proved.

---

### Example 4: Divisibility of a Summation

### Statement

Prove that:
$
3 \mid \sum_{i=1}^{n} (2i - 1)
\quad \text{when } n \equiv 0 \pmod{3}
$

Use induction by grouping or standard algebraic induction.

---

## Common Techniques Used in Divisibility Proofs

* Rewriting $ f(k+1) $ using $ f(k) $
* Factoring out the divisor
* Adding and subtracting suitable terms
* Using properties of even and odd numbers
* Applying binomial expansion

---

## Why Induction Works Well for Divisibility

* Divisibility is preserved under addition and multiplication
* Induction naturally builds expressions step-by-step
* Allows proof for infinite sets of integers


---

## Final Conclusion

Divisibility proofs by induction are essential in discrete mathematics and number theory. By verifying a base case and carefully expressing $ f(k+1) $ in terms of $ f(k) $, we can prove that an expression is divisible by a fixed integer for all natural numbers.

