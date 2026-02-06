# Counting Principles in Discrete Mathematics

**Counting principles** are basic rules used to determine the number of possible outcomes or arrangements without listing them individually. They are widely used in **computer science, probability, algorithms, and combinatorics**.

---

## 1. Rule of Sum (Addition Principle)

### Definition

If a task can be performed in **m ways** or in **n ways**, and **both cannot occur together**, then the total number of ways is:

$
m + n
$

### Example

* A student can choose **3 mathematics books** or **5 physics books**.
* Total choices = $3 + 5 = 8$

### Use

Used when choices are **mutually exclusive**.

---

## 2. Rule of Product (Multiplication Principle)

### Definition

If a task consists of **two or more steps**, where:

* Step 1 can be done in **m ways**
* Step 2 can be done in **n ways**

Then the total number of ways is:

$
m \times n
$

### Example

* 4 shirts and 3 pants
* Total outfits = $4 \times 3 = 12$

### Use

Used when choices occur **together in sequence**.

---

## 3. Principle of Inclusion and Exclusion (PIE)

### Definition

Used to count elements in **overlapping sets**.

For two sets **A** and **B**:

$
|A \cup B| = |A| + |B| - |A \cap B|
$

### Example

* 20 students like tea
* 15 like coffee
* 5 like both

$
|A \cup B| = 20 + 15 - 5 = 30
$

### Use

Prevents **double counting**.

---


## 4. Counting with Repetition

### Definition

When objects can be **repeated**.

### Formula

Number of r-length sequences from n objects:
$
n^r
$

### Example

* Binary strings of length 4:
  $
  2^4 = 16
  $

---

## 5. Tree Diagram Method

### Definition

A **visual method** to list all possible outcomes step-by-step.

### Example

* Tossing a coin twice → {HH, HT, TH, TT}

Used mainly for **small problems**.

---

# Applications of Counting Principles

* Password and PIN generation
* Data structures and algorithms
* Probability calculations
* Cryptography
* Database query optimization

---

