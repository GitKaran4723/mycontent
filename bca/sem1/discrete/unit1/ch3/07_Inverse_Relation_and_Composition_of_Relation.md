# **Inverse Relation**

An inverse relation is the opposite of a given relation obtained by interchanging or swapping the elements of each ordered pair. In simple terms, if (x, y) is a point in a relation R, then (y, x) is an element in the inverse relation.

**R−1: B → A**

## **Properties of Inverse Relations**

* Inverse relations, reverse the roles of the input and output values.
* The domain of a relation transforms into the range of its inverse, and vice versa.  
* The composition of a relation with its inverse results in the identity relation i.e., R o (R\-1) = Identity  
* The inverse of an inverse relation is the original relation itself i.e., (R\-1)\-1 = R  
* If a relation is injective (one-to-one), then its inverse is also injective.  
* If a relation is surjective (onto), then its inverse is also surjective

**Example**
If R = {(2, 8), (3, 12), (4, 16)}, then  
 the inverse relation R−1 would be {(8, 2), (12, 3), (16, 4)}

## **Inverse Relation Solved Examples**

 **1: Determine the inverse of the following relation. R = {(8, 9\) (3, 5), (4, 6)}**

**Solution:**

Given: R = {(8,9) (3,5), (4,6)}   
The inverse of set R will be,  
R⁻¹ = {(9,8), (5,3), (6,4)}

**2: Determine the inverse of the function R = (x, x2)where x is a prime number smaller than 15\.**

**Solution:**

The list of prime numbers less than 15 includes 2, 3, 5, 7, 11 and 13\.  
R = {(2,4), (3,9), (5,25), (7,49), (11, 121), (13, 169)}  
The inverse of set R should be,  
R⁻¹ = {(4,2), (9,3), (25,5), (49,7), (121, 11), (169, 13)} 

**3: Determine the domain and the range of the relation R = (x, x2)where x is an even number smaller than 9\.**

**Solution:**

The list of even numbers less than 9 includes 2, 4, 6 and 8. 
R = {(2,4), (4,16), (6,36), (8,64)}

* Domain of R = {2, 4, 6, 8} 
* Range of R = {4, 16, 36, 64}

# **Composition of Relations**

A composition of relations is a method whereby two sets are combined to produce a new one by use of a combination of every feasible pair of elements from the two sets, so indirectly.

**S ⚬ R  = (a, c) | ∃b ∈ B such that (a, b) ∈ R and (b, c) ∈ S**

Interpreting the definition above:

* (a, b) ∈ R denotes a in A and b in B relate based on the relation R.  
* (b, c) ∈ S denotes b in B and c in C relate based on the relation S  
* (a, c) ∈ S ⚬ R reveals an indirect relationship between a in A and c in C based on b in B.

## **Properties of Composition of Relations**

The properties of composition of relations are as follows:

* **Identity Relation:** For any set A, the identity relation IA on A is defined as IA = {(a, a) | a ∈ A}. The identity relation acts as a neutral element in the composition: R ⚬ IA = R and IB ⚬ R = R, where R ⊆ A x B.  
* **Associativity:** Composition of relations is associative. If R ⊆ A x B, S ⊆ B x C and T ⊆ C x D then T ⚬ (S ⚬ R) = (T ⚬ S) ⚬ R.  
* **Inverse Relation:** If R ⊆ A x B, the inverse relation R\-1 ⊆ B x A is defined as (b, a) ∈ R\-1 ⇔ (a, b) ∈ R. The composition of a relation and its inverse has properties similar to functions: R ⚬ R\-1 ⊆ IB and R\-1 ⚬ R ⊆ IA.  
* **Distributivity over Union:** Composition of relations distributes over the union: R ⚬ (S ⋃ T) = (R ⚬ S) ⋃ (R ⚬ T) and (R ⋃ S) ⚬ T = (R ⚬ T) ⋃ (S ⚬ T).  
* **Monotonicity:** If R1 ⊆ R2 and S1 ⊆ S2 , then: S1 ⚬ R1 ⊆ S2 ⚬ R2.

**Example**
Let us consider that we have three sets: A, B, and C. Let R be a relation from A to B and let S be a relation from B to C. The composition S ⚬ R is a relation from A to C that contains all pairs (a, c) such as there is an element b ∈ B such that (a, b) ∈ R and (b, c) ∈ S.

## **Solved Examples on Composition of Relations**

**1: Given the two relations as below:**

* **Relation (R) as {(1, 20), (24, 38)}**  
* **Relation (S) as {(8, 9), (7, 6)}**

**Find the composition of this relations i.e. S ⚬ R.**

**Solution:**

Now, let us consider that (a, b) ∈ R, and we need  to find the corresponding b in S as (b, c) in order to form the composition of relations.

And finally after combining the pairs we can get S ⚬ R where (a, c) ∈ (S ⚬ R).

But, from the relation R we can find that R doesn't have any b values that matches with the first element of the pair in S. So, we can say that S ⚬ R = ∅.

***2: Given the two relations as below:**

* **Relation (R) as {(1, 20), (25, 35)}** 
* **Relation (S) as {(20, 40), (35, 56)}**

**Find the composition of this relations i.e. S ⚬ R.**

**Solution:**

Now, let us consider that (a, b) ∈ R, and we need  to find the corresponding b in S as (b, c) in order to form the composition of relations.

And finally after combining the pairs we can get S ⚬ R where (a, c) ∈ (S ⚬ R) where. Now, from the given relations:

1\. Now if we combine (1, 20\) from R and (20, 40\) from S it is going to result in (1,40).  
2\. We can merge (25, 35\) from R and (35, 56\) from S to get (25,56).

Therefore, we obtain S ⚬ R ={(1,40), (25, 56)}.

