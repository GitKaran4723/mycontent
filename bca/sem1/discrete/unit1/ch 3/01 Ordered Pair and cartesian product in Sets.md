# **Ordered Pair in Sets**

In **set theory,** ordered pairs are often used to define relations between elements of different sets. An ordered pair (a, b) signifies that 'a' is related to 'b' in some way, distinct from the pair (b, a) if 'a' and 'b' are different elements.

In set theory, ordered pairs are instrumental in establishing relations between elements of different sets.

 **example:**

 *A={(1,2),(3,4),(5,6)}*

# **Cartesian Product of Sets**

The Cartesian product of two sets, denoted by A × B, is the collection of all possible **ordered pairs**(a, b) such that the first element a belongs to set A and the second element b belongs to set B. It is written in set builder form as:

***A × B = {(a, b) : a ∈ A and b ∈ B}***

**Example:**

*Let A = {1, 2} and B = {4, 5, 6}*

*A × B = {(1, 4), (1, 5), (1, 6), (2, 4), (2, 5), (2, 6)}Sets*

## **Cartesian Product Formula**

For two sets A and B:

***A × B = {(a, b) ∣ a ∈ A, b ∈ B}***

Number of ordered pairs in A × B:  
***∣ A × B ∣ = ∣A∣ ⋅ |B|***  
Where:

* ∣A∣ = number of elements in set A  
* ∣B∣ = number of elements in set B

***Example:** If A = {1,2,3} and B = {x, y}* 

*A × B = {(1, x), (1, y), (2, x), (2, y), (3, x), (3, y)}*

*∣A × B∣ = 3⋅2 = 6*

## **Cartesian Product of Three Sets**

The Cartesian product of three sets (A, B, and C) is simply the set of all possible ordered triples (a, b, c), where the first element a comes from A, the second b from B, and the third c from C. We write it as A × B × C.

***A × B × C = {(a, b, c) ∣ a ∈ A, b ∈ B, c ∈ C}***

Number of Ordered Triples:

The total number of ordered triples is the product of the number of elements in each set:

***∣ A × B × C ∣ = ∣A∣ ⋅ ∣B∣ ⋅ ∣C∣***  
**Example:**

If A = {5, 6, 7}, B = {x, y} and C = {p, q, r}

A × B × C = {​(5, x, p), (5, x, q), (5, x, r), (5, y, p), (5, y, q), (5, y, r), (6, x, p), (6, x, q), (6, x, r), (6, y, p), (6, y, q), (6, y, r), (7, x, p), (7, x, q), (7, x, r), (7, y, p),(7, y, q), (7, y, r)}​

∣A × B × C∣ = 3⋅2⋅3 = 18\.

## **Properties of Cartesian Product**

**1\. Cartesian Product is non-commutative: A × B ≠ B × A**

**Example:** 

*A = {1, 2} , B = {a, b}*

*A × B = {(1, a), (1, b), (2, a), (2, b)}*

*B × A = {(a, 1), (b, 1), (b, 1), (b, 2)}*

*Therefore as A ≠ B we have A × B ≠ B × A*

**2\. A × B = B × A, only if A = B**

**Proof:**

*Let A × B = B × A then we have*  

*A ⊆  B  and B ⊆  A, it follows that A = B*

**3\. Cardinality of Cartesian Product is defined as the number of elements in A × B and is equal to the product of the cardinality of both sets, i.e., |A × B| = |A| × |B|**

**Proof:**

Let a ∈ A then the number of ordered pair (a, b) such that b ∈ B is |B|

Therefore we have |B| choices for b for each a where a ∈ A therefore the number of element in A × B is |A| × |B|

**4\. A × B = ∅, if either A = ∅ or B \= ∅**

**Proof:** 

Suppose A × B = ∅. This means there are no ordered pairs (a, b) where a ∈ A and b ∈ B.

## **Solved Problems on Cartesian Product of Sets**

***Problem 1:**  If A = {9, 10} and B = {3, 4, 6}, find A × B and |A × B|?* 

***Solution:***

*A × B = {(9, 3), (9, 4), (9, 6), (10, 3), (10, 4), (10, 6)}*

*|A × B| = |A| \* |B| = 2 \* 3 = 6*

***Problem 2:** Let A = {1, 2, 3}, B = {x, y, z}. R = {(a, b) ∈ A × B ∣ a is odd and b ≠ y}.*

***Solution:***

*Identify odd elements of A : 1 and 3\.*

*For each odd a, allowed b are elements of B except y, i.e. {x, z}.*

*Form ordered pairs: for a = 1: (1, x), (1, z). For a = 3 : (3, x), (3, z).*

*So R = {(1, x), (1, z), (3, x), (3, z)}.*

*Cardinality: ∣R∣ = 4\.*

***Problem 4:** If A × B = {(a, x), (a, y ), (b, x ), (b, y)}, find A and B?*

***Solution:***

*We know A is the set of all first components in ordered pairs of A × B and* 

*B is the set of the second component in the ordered pair of A × B.*

*Therefore A = {a, b} and B = {x, y}*

