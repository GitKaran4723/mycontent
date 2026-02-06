# Pigeonhole Principle (PHP)

### Introduction

The **Pigeonhole Principle** is a fundamental counting principle in discrete mathematics. It is used to prove the **existence** of a particular condition without identifying exactly where it occurs. The idea is simple but extremely powerful and widely used in **mathematics, computer science, and logic**.

---

## Basic Statement of the Pigeonhole Principle

### Definition

If **n objects** are placed into **m boxes**, and if
$
n > m
$
then **at least one box contains more than one object**.

This principle is called the *Pigeonhole Principle* because if more pigeons than pigeonholes are present, at least one pigeonhole must contain more than one pigeon.

---

## Mathematical Form

Let:

* (n) = number of objects
* (m) = number of boxes

If
$
n > m
$
then at least one box contains **at least two objects**.
## Generalized Pigeonhole Principle

### Definition

If **n objects** are placed into **m boxes**, then at least one box contains **at least**:

$
\left\lceil \frac{n}{m} \right\rceil
$

objects, where ⌈ ⌉ denotes the **ceiling function** (smallest integer ≥ the value).


---

##  Examples

### Example 1: Birthdays

There are **13 people** and **12 months** in a year.
Since $13 > 12$, at least **two people share the same birth month**.

---

### Example 2: Socks

If you have **11 socks** and only **10 colors**, then at least **two socks are of the same color**.







---

### Example 3: Generalized Case

If **100 students** are distributed among **9 classrooms**, then at least one classroom contains:

$
\left\lceil \frac{100}{9} \right\rceil = 12
$

students.

---
### Example 4: Differences of Numbers

From any **6 integers**, there exist **two numbers whose difference is divisible by 5**.

**Reason:**
Possible remainders when dividing by 5 are:
({0,1,2,3,4}) → 5 boxes
6 numbers → objects
At least two numbers fall into the same remainder class.

---

### Example 5: Handshakes

In a group of **n people**, at least two people have the same number of friends.

**Reason:**
Possible number of friends ranges from 0 to (n-1), but both 0 and (n-1) cannot occur simultaneously → only (n-1) possibilities.

---




## Why the Pigeonhole Principle Works (Intuition)

* If each box had **at most k objects**, then the total number of objects would be **at most m × k**.
* If the number of objects exceeds this maximum, then one box must contain **more than k objects**.

This logic makes the principle a **proof by contradiction** tool.

---

## Applications of the Pigeonhole Principle

### 1. Computer Science

* Hashing collisions
* Memory allocation
* Data distribution problems



### 2. Mathematics

* Number theory
* Combinatorics
* Graph theory



### 3. Everyday Life

* Shared birthdays
* Duplicate phone numbers
* Repeated exam scores

---





## Steps to Apply the Pigeonhole Principle in Problems

1. Identify the **objects**
2. Identify the **boxes**
3. Compare (n) and (m)
4. Apply PHP or Generalized PHP
5. State the conclusion clearly

---

## Limitations of the Principle

* PHP proves **existence**, not exact identification
* It does not specify **which box** contains more objects
* Often needs **logical framing** to apply correctly

