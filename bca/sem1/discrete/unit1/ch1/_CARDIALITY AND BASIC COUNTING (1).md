## **CARDIALITY**

A set is a collection of distinct objects, considered as a whole. These objects are called the elements or members of the set. For example, the set of natural numbers less than 5 can be written as {1, 2, 3, 4}.

The number of elements in the set or a measure of its size is known as the **cardinality of a set**. 

* It can be finite or infinite.  
* It is denoted by: |A| or card(A)  
* For example, the set {1, 2, 3, 4, 5} has a cardinality of 5\. 

## **Cardinality of Different Sets**

Some of the common sets with cardinality are:

 ###  **1. Cardinality of a Finite Set**

   **Cardinality** of a finite set refers to the number of elements in the set. If a set S is finite, its cardinality is simply the count of distinct elements within the set.

The total number in the set is known as the cardinality of a power set.

*For example: If A \= {1, 2, 3, 4, 5}, then |A| \= 5\.*

### **2. Cardinality of an Infinite Set**

A set is countably infinite if its elements can be put into a one-to-one correspondence with the natural numbers N \= {1, 2, 3, . . . }. This means that you can list the elements of the set in a sequence (even if the sequence goes on forever).

The cardinality of a countably infinite set is denoted by ℵ0.

**Examples:**

* ***Natural Numbers:** The set of natural numbers N={1, 2, 3, . . .} is countably infinite.*  
* ***Integers:** The set of integers Z={. . . ,−2, −1, 0, 1, 2, . . . } is countably infinite because you can list them in a sequence like 0, 1, −1, 2, −2, . . .*  
* ***Rational Numbers:** The set of rational numbers Q \= {a/b ∣ a,b ∈ Z, b ≠ 0} is countably infinite, though it's less obvious. The rationals can be arranged in a sequence by arranging fractions by their sum of numerator and denominator.*

 ### **3. Cardinality of a Countable Set**

    A set is countable if:

* It is finite  
* It is infinite, but you can list its elements one by one (like 1st, 2nd, 3rd, …), meaning there's a bijection with natural numbers N.

If a set is countable and infinite, it is known as a countably infinite set. Examples include the sets of natural numbers (ℕ), integers (ℤ), and rational numbers (Q).

* For a finite countable set, its cardinality is simply the number of elements it contains.  
* However, for an infinite countable set, its cardinality is the same as that of the natural numbers.

 ### **4. Cardinality of an Uncountable Set**

A set is uncountable if:

* It is infinite  
* Its elements cannot be listed not even in an infinite list like a1, a2, a3.

If a set is uncountable, it is infinite and its elements cannot be listed in sequence; it is called an uncountably infinite set.

* For an uncountable set, its elements cannot be listed in a sequence.  
* The cardinality of an uncountable set is greater than that of the natural numbers.

 ### **5. Cardinality of a Power Set**

**Power Set** of a set S is the set of all possible subsets of S, including the empty set and S itself.

If a set A has n elements, then the cardinality of its power set is equal to 2n, which is the number of subsets of the set A.

If a set S has n elements, the power set P(S) will have 2n elements. This is because each element in S can either be included in or excluded from a subset, leading to 2n possible subsets.

For any finite set S with n elements: ∣P(S)∣ \= 2n

*Consider the set S \= {a, b}.*

*Subsets of S are:*

* *{} (the empty set)*  
* *{a}*  
* *{b}*  
* *{a, b}*

*The power set P(S) is {{}, {a}, {b}, {a, b}}*

*Since S has 2 elements, the cardinality of the power set P(S) is 22 \= 4\.*

 ### **6. Cardinality of Cartesian Products**

The Cartesian product of two sets A and B, denoted by A × B, is the set of all ordered pairs (a, b) where a ∈ A and b ∈ B.

The cardinality of the Cartesian product A x B is the total number of ordered pairs formed from A and B. It is given by:

*|  A x B | \=| A | x | B |*

* Where |A| and |B| are cardinalities of sets A and B.

**Finite Set Example:** If A \= {1, 2} and B \= {x, y, z}, then A × B \= {(1, x), (1, y), (1, z), (2, x), (2, y), (2, z)}, so ∣A × B∣ \= 6\.

**Infinite Set Example:** If A \= {1, 2,3,4,........} and B \= {10,20,30,........}, then |A × B| \= {(1, 10), (1, 20), (1, 30),...........,(2, 10), (2, 20), (2, 30)}.

### **Formulas Related to Cardinality**

* If A and B are two disjoint sets, then

*n(A U B) \= n(A) \+ n (B).*

* For any two sets A and B,

*n (A U B) \= n(A) \+ n (B) \- n (A ∩ B).*

This is popularly known as the "inclusion-exclusion principle".

* For any three sets A, B, and C,

*n(A U B U C) \= n (A) \+ n(B) \+ n(C) \- n(A ∩ B) \- n(B ∩ C) \- n(C ∩ A) \+ n (A ∩ B ∩ C).*

### **COUNTING BASICS** 

Basic counting is about finding how many outcomes or objects are possible in a situation without listing them all.


### **a. Rule of Sum (Addition Principle)**

Used when choices do not overlap.

If one task can be done in mmm ways and another in nnn ways, and you can choose only one, then total ways:

m+nm \+ nm+n

Example  
 You can choose:

* 3 math books or

* 5 physics books

Total choices:

3+5=83 \+ 5 \= 83+5=8


### **b. Rule of Product (Multiplication Principle)**

Used when choices happen in sequence.

If one task can be done in mmm ways and after that another in nnn ways, then total ways:

m×nm \\times nm×n

Example

* 4 shirts

* 3 pants

Total outfits:

4×3=124 \\times 3 \= 124×3=12

---

## **Counting Using Sets**


* Step 1 has ∣A∣|A|∣A∣ choices

* Step 2 has ∣B∣|B|∣B∣ choices

Total outcomes:

∣A∣×∣B∣|A| \\times |B|∣A∣×∣B∣

This directly connects cardinality with counting.

