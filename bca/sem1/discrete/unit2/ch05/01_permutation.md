# Permutation

### Introduction

A **permutation** is an **arrangement** of objects in a **specific order**.
In permutations, **order matters**. Even if the same objects are used, a different order gives a different permutation.

---

## Definition of Permutation

A **permutation** is an ordered arrangement of objects selected from a set.

Example:
If the set is ({A, B, C}), then

* ABC and BAC are **different permutations**
* because the order is different.

---

## Permutation of (r) Objects Taken from (n) Objects

### Formula

$
^nP_r = \frac{n!}{(n-r)!}
$

Where:

* (n) = total number of distinct objects
* (r) = number of objects selected
* (!) = factorial

---

### Example 1

In how many ways can **3 students** be selected and arranged from **5 students**?

$
^5P_3 = \frac{5!}{(5-3)!} = \frac{5!}{2!} = 60
$

---

## Permutation of All Objects

When all (n) objects are arranged:

$
^nP_n = n!
$

---

### Example 2

In how many ways can **4 books** be arranged on a shelf?

$
4! = 24
$

---

## Permutations with Repetition Allowed

### Definition

When an object can be **repeated**, the number of permutations is:

$
n^r
$

---

### Example 3

How many **3-digit numbers** can be formed using digits 0–9 (repetition allowed)?

$
10^3 = 1000
$

---

## Permutations with Repeated Objects

### Definition

If among (n) objects:

* (p) objects are identical of one type
* (q) objects are identical of another type

Then the number of distinct permutations is:

$
\frac{n!}{p!q!}
$

---

### Example 4

How many distinct permutations of the word **LEVEL**?

* Total letters = 5
* L appears twice, E appears twice

$
\frac{5!}{2!2!} = 30
$

---

## Circular Permutations

### Definition

Arrangements of objects in a **circle**, where rotations are considered the same.

---

### Formula

$
(n - 1)!
$

---

### Example 5

In how many ways can **5 people** sit around a round table?

$
(5 - 1)! = 4! = 24
$

---

## Permutations Under Restrictions

### Example 6

In how many ways can 5 people sit in a row if **two particular people must sit together**?

**Method:**

* Treat the two people as **one unit**
* Total units = 4

$
4! \times 2! = 48
$

---

### Example 7

In how many ways can 5 people sit in a row if **two particular people must not sit together**?

$
\text{Total permutations} - \text{Together}
$

$
5! - (4! \times 2!) = 120 - 48 = 72
$

---



## Applications of Permutations

* Seating arrangements
* Passwords and PIN numbers
* Ranking problems
* Scheduling tasks
* Cryptography

---

## Common Exam Mistakes

* Using permutation when **order does not matter**
* Forgetting to divide for **repeated objects**
* Using $n!$ instead of $(n-1)!$ for circular cases

---

