# **Properties of Relation**

# **1. Reflexive Relation**

A reflexive relation is a type of **binary relation** on a set where every element in the set is related to itself. In other words, for any element "a" in the set, the pair (a, a) is a part of the relation. Formally, a relation R on a set A is reflexive if, for all elements "a" in A, (a, a) is in R.

 A reflexive relation is denoted as:

***R = {(a, a): a ∈ A}***

### **Properties of a Reflexive Relation**

* An empty relation on a non-empty relation set is never reflexive.  
* A relation defined on an empty set is always reflexive.  
* A universal relation defined on any set is always reflexive.

**Example:** Consider set A = {a, b} and R = {(a, a), (b, b)}. Here, R is a reflexive relation, as for both a and b, a R a and b R b are present in the set.

## **Solved Problems on Reflexive Relation**

**Problem 1:** Consider a set A = 1, 2, 3, and let R be a relation on A defined by R = (1, 1), (2, 2), (3, 3), (1, 2), (2, 1). Determine whether the relation R is reflexive.  
**Solution:**

*A relation is reflexive if every element in the set is related to itself. In this case, we need to check whether (a, a) is in R for every a in A. Let's check:*

* *For a = 1, (1, 1\) is in R.*  
* *For a= 2, (2, 2\) is in R.*
* *For a = 3, (3, 3\) is in R.*

*Since every element in A is related to itself, the relation R is reflexive.*

***Problem 2:** Consider the set C = a, b, c, and define a relation T on C by T = (a, a), (b, b), (c, c), (a, b), (b, a), (b, c), (c, b). Determine whether the relation T is reflexive.*

***Solution:***

*To check if T is reflexive, we need to ensure that (a, a), (b, b), and (c, c) are all in T. Let's check:*

* *(a, a) is in T.*  
* *(b, b) is in T.*  
* *(c, c) is in T.*

*Since every element in C is related to itself, the relation T is reflexive.*

#  **2. Symmetric Relation**

Symmetric relations are a type of relation where the two elements of set X are related with relation R, then reversing the order of the elements is also related with the relation R. In other words, a symmetric relation is defined as if xRy then yRx, where x and y are two elements of set S and R is a relation. A relation R on a set A is symmetric if, whenever

**(x, y) ∈ R, then (y, x) ∈ R.**

### **Properties of Symmetric Relations**

Some properties of a symmetric relation are listed below:

* An empty relation on any set is always symmetric.  
* A universal relation is always symmetric.  
* If R is a symmetric relation, then R\-1 is also symmetric.  
* If R1 and R2 are symmetric relations, then R1 ∪ R2 is also symmetric.  
* If R1 and R2 are symmetric relations, then R1 ∩ R2 is also symmetric.  
* A relation can be symmetric and antisymmetric at the same time.  
* A relation cannot be symmetric and asymmetric at the same time.  
* In the matrix representation of the symmetric relation, the transpose of the matrix is equal to the original matrix. MR = (MR)T.  
* In the directed graph representation of the symmetric relation, if there is an edge between two distinct nodes, then an opposite edge is also present between the two nodes.

### **Number of Symmetric Relations Formula**

The formula for the total number of symmetric relations with n-elements is given by:

***Number of Symmetric Relation = 2\[n(n \+1)\]/2***  
where,

* N is the Number of Symmetric Relations  
* n is Number of Elements in Set

**For example:** A = {7, 9} then symmetric relation R on A if,

* R = {(7, 9), (9, 7)}

* *(7, 5\) ∈ R then, (5, 7\) ∈ R , R is symmetric.*

## **Solved Problems on Symmetric Relation**

**Example 1:** Check whether the relation R \= {(2, 5), (3, 3)} is symmetric or not?

**Solution:**

*R = {(2, 5), (3, 3)}*

*Above relation is not a symmetric relation as:*

*(2, 5\) ∈ R but (5, 2\) ∉ R*

*R is not symmetric.*

**Example 2:** Prove that the given relation R = {(1, 2), (2, 1), (4, 4), (5, 7), (7, 5)} is a symmetric relation?

**Solution:**

*R = {(1,2), (2,1), (4,4), (5,7), (7, 5)}*

*Above relation is symmetric relation as:*

* *(1, 2\) ∈ R then, (2, 1\) ∈ R*  
* *(2, 1\) ∈ R then, (1, 2\) ∈ R*  
* *(4, 4\) ∈ R then, (4, 4\) ∈ R*  
* *(5, 7\) ∈ R then, (7, 5\) ∈ R*  
* *(7, 5\) ∈ R then, (5, 7\) ∈ R*  
  *R is symmetric.*

# **3. Asymmetric Relation**

An asymmetric relation is a specific type of binary relation on a set where the order of elements matters. In an asymmetric relation, if the pair (a, b) is in the relation, then the pair (b, a) must not be in the relation for any elements a and b from the set. In other words, the relationship is one-directional or asymmetric.

***∀ a, b ∈ A**, if **(a, b) ∈ R** then **(b, a) ∉ R***  
where ,

R is a subset of (A x A)  
Thus if an ordered pair of elements “a” to “b” (aRb) is present in relation R then an ordered pair of elements “b” to “a” (bRa) should not be present in relation R.

### **Properties of Asymmetric Relations**

Some of the properties of Asymmetric Relations are:

* Empty relations on any set are always asymmetric.  
* Every asymmetric relation is also irreflexive and anti-symmetric.  
* Universal relation over a non-empty set is never asymmetric.  
* A non-empty relation can not be both symmetric and asymmetric.  
* An asymmetric relation is always irreflexive, meaning no element is related to itself.  
* Asymmetric relations can be represented by directed acyclic graphs (DAGs).  
* Asymmetric relations are often used in the context of partial orderings, where the relation represents a partial order if it is antisymmetric and transitive.  
* While asymmetric relations are not necessarily antisymmetric, antisymmetric relations are always asymmetric.

**Example:** Consider set A = {a, b}

* R = {(a, b), (b, a)} is not asymmetric relation but  
* R = {(a, b)} is a symmetric relation.

## **4. Antisymmetric Relation**

The relation is said to be an antisymmetric relation if in a set S the two elements p and q are related with relation R then, p \= q. Also, if for every (p, q) ∈ R, (q, p) ∉ R then, R is antisymmetric. Mathematically, the antisymmetric relation is defined as:

If x and y are two elements in set X and R is a relation then, conditions for relation to be antisymmetric:

***(x, y) ∈ R then, (y, x) ∉ R***

### **Properties of Antisymmetric Relations**

The properties of antisymmetric relations are listed below:

* Empty relations on any set are always antisymmetric.  
* A relation can be symmetric and antisymmetric at same time.  
* If R is an antisymmetric relation, then R\-1 is also antisymmetric.  
* It R1 and R2 are two antisymmetric relations, then R1 ∩ R2 is also antisymmetric.  
* In the matrix representation of antisymmetric relation, either Mij = 0 or Mij ≠ 0 when i ≠ j.

### **Number of Antisymmetric Relations**

The formula for number of antisymmetric relations with n-elements is given by:

***Total number of antisymmetric relation = 2n × 3 \[n(n-1)\]/2***

**Example: If relation R = {(1, 1), (4, 7), (7, 4)} then, find the given relation is an antisymmetric relation or not?**

**Solution:**

*R = {(1, 1), (4, 7), (7, 4)}*  
*The above relation is antisymmetric as*  
*(1, 1\) ∈ R and (1, 1\) ∈ R and 1 \= 1\.*  
*(4, 7\) ∈ R and (7, 4\) ∈ R and 4 ≠ 7\.*

*R is not an antisymmetric relation.*

## **Problems on Antisymmetric Relations**

**1: Check whether the relation R = {(1,4), (2,5)} is antisymmetric or not?**

**Solution:**

*R = {(1,4), (2,5)}*  
*The above relation is antisymmetric as*  
*(1, 4\) ∈ R and (4, 1\) ∉ R.*  
*(2, 5\) ∈ R and (5, 2\) ∉ R.*  
*R is antisymmetric.*

***2: Prove the given relation R = {(2,2), (3,7)} is an antisymmetric relation?***

***Solution:***

*R = {(2, 2), (3, 7)}*  
*The above relation is antisymmetric as*  
*(2, 2\) ∈ R and (2, 2\) ∈ R and 2 \= 2\.*  
*(3, 7\) ∈ R and (7, 3\) ∉ R.*  
*R is antisymmetric.*

# ***5\. Transitive Relations***

 Transitive Relation is one of the necessary conditions for an **equivalence relation** as for any relation to be that needs to be Transitive at first.

In a Transitive Relation, if element A is related to element B and element B is related to element C, then there must also be a relationship between element A and element C, following the same rule or relation. In other words, if A relates to B and B relates to C, then A must relate to C.

Representation of a Transitive Relation:

**If (a, b) ∈ R and (b, c) ∈ R, then (a, c) ∈ R.**

**Example**

Some examples of transitive relationships are:

* A is a Subset of B  
* x is Divisible by y  
* A is Equal to B  
* △1 is Congruent to △2  
* This Implies that

## **Solved Examples of Transitive Relation**

**1: Consider a set of natural numbers and define a relation R as follows: (1, 2), (2, 3), (1, 3). Check if relation R is transitive.**

**Solution:**

*(1, 2\) and (2, 3\) we must verify if (1, 3\) also belongs to R.*  
*In this relation:*

* *(1, 2\) implies that 1 is related to 2\.*  
* *(2, 3\) implies that 2 is related to 3\.*

* *(1, 3\) implies that 1 is related to 3\.*

*Since (1, 3\) is indeed part of R, we conclude that relation R is transitive.*

