# **Equivalence Relations**

An **equivalence relation** is a type of relation that satisfies three fundamental properties: reflexivity, symmetry, and transitivity. These properties ensure that it defines a partition on a set, where elements are grouped into equivalence relation based on their similarity or equality.

## **Properties of Equivalence Relation**

*  Equivalence relations are often denoted by the symbol "≡" or by writing "∼" between related elements.
* An example of an equivalence relation is the "congruence modulo n" relation in modular arithmetic, where two integers are related if their difference is a multiple of n. This relation is reflexive, symmetric, and transitive.  
* Equivalence relations are widely used in mathematics, computer science, and other fields for classifying objects, defining partitions, and simplifying complex problems.

## **How to Verify an Equivalence Relation?**

Let us assume that R is a relation on the set of ordered pairs of positive integers such that ((a, b), (c, d))∈ R if and only if ad \= bc. Is R an equivalence relation?
To prove that R is an equivalence relation, we must show that R is

* Reflexive Relation  
* Symmetric Relation  
* Transitive Relation

Let's verify all these relations for any given relation R.

## **Verify Reflexive Relation**

The process of identifying if any given relation is reflexive:

* Check for the existence of every aRa tuple in the relation for all a present in the set.  
* If every tuple exists, then the relation is reflexive. Otherwise, not reflexive.

### **Example for Reflexive Relation**

Consider set A = {a, b} and a relation R = {{a, a}, {b, b}}.

*For the element a in A:*   
*⇒ The pair {a, a} is present in R.*  
*⇒ ARA is satisfied.*

*For the element b in A:*  
*⇒ The pair {b, b} is present in R.*  
*⇒ Hence bRb is satisfied.*

As the condition for 'a', ‘b’ is satisfied, the relation is reflexive.

## **Verify Symmetric Relation**

To verify a symmetric relation, do the following:

* Manually check for the existence of every bRa tuple for every aRb tuple in the relation.  
* If any of the tuples do not exist, then the relation is not symmetric; else, it is symmetric.

Follow the example given below for better understanding.

### **Example for Symmetric Relation**

Consider set A = { 1, 2, 3, 4 } and a relation R = { (1, 2), (1, 3), (2, 1), (3, 4), (3, 1),(4.3) }

*For the pair (1, 2\) in R:*

*⇒ The reversed pair (2, 1\) is present in the relation.*  
*⇒ This pair satisfies the condition*

*For the pair (1, 3\) in R:*

*⇒ The reversed pair (3, 1\) is present in the relation.*  
*⇒ This pair satisfies the condition*

*For the pair (2, 1\) in R:*

*⇒ The reversed pair (1, 2\) is present in the relation.*  
*⇒ This pair satisfies the condition*

*For the pair (3, 4\) in R:*

*⇒ The reversed pair (4, 3\) is present in the relation.*  
*⇒ This pair satisfy the condition*

*For the pair (3, 1\) in R:*

*⇒ The reversed pair (1, 3\) is present in the relation*  
*⇒ This pair satisfies the condition*

As the set satisfies the condition, the relation is **symmetric.**

## **Verify Transitive Relation**

To verify the transitive relation:

* Firstly, find the tuples of the form **aRb & bRc** in the relation.  
* For every such pair, check if **aRc** is also present in R.  
* If any of the tuples do not exist, then the relation is not transitive; else, it is transitive.

### **Example for Transitive Relation**

Consider set R = {(1, 2), (1, 3), (2, 3), (3, 4), (1,4)}

*For the pairs (1, 2\) and (2, 3):*

*⇒ The relation (1, 3\) exists*  
*⇒ This satisfies the condition.*

*For the pairs (1, 3\) and (3, 4):*

*⇒ The relation (1, 4\) exists.*  
*⇒ This satisfies the condition.*

*So the relation is **transitive.***

Hence, the transitive property is proved.

## **Solved Problems on Equivalence Relation**

**1:** Show that the relation R, defined in the set A of all polygons as R = {(P1, P2): P1 and P2 have the same number of sides}, is an equivalence relation on A.

**Solution:**

*Given A = set of all polygons*  
*R = {(P1, P2): P1 and P2 have same number of sides}*  
*In order to prove that R is an equivalence relation, we must show that R is reflexive, symmetric and transitive.*

* *Reflexive: Let P A*  
  *Clearly, Number of sides of P = number of sides of P*  
  *(P, P) ⋿ R ∀ P ⋿ A*  
  *Hence, R is reflexive.*  
* *Symmetric: Let P1, P2 ⋿ A*  
  *Let (P1, P2) ⋿ R ⇒ P1 and P2 have same number of sides*  
  *⇒ P2 and P1 have same number of sides*  
  *⇒ (P2, P1) ⋿ A*  
  *Hence R is Symmetric.*

* *Transitive: Let P1, P2 ⋿ A*  
  *Let (P1, P2) ⋿ R and (P2, P3) ⋿ R*  
  *⇒ Number of sides of P1 = number of sides of P2 and*  
  *⇒ Number of sides of P2 = number of sides of P3*  
  *⇒ Number of sides of P1 = number of sides of P3*  
  *⇒ (P1, P3) ⋿ R*  
  *Hence R is transitive.*

**2:** Show that the relation R in the set A = {x ⋿ Z : 0 ≤ x ≤ 12} given by R = {(a, b): a = b} is an equivalence relation.  
**Solution:**

*Let A = { x ∈ Z: 0 ≤ x ≤ 12 } and the relation R = { ( a, b ) ∈ A × A: a = b }.*  
*We show that (R) is an equivalence relation by verifying the three required properties: reflexive, symmetric, and transitive.*

* *Reflexive*
  *A relation R on a set A is reflexive if ( a, a ) ∈ R for all a ∈ A.*  
  *Take any a ∈ A.*  
  *Since ( a = a ), by definition of R, ( a, a ) ∈ R*  
  *Hence, (R) is reflexive.*

* *Symmetric*
  *A relation (R) is symmetric if ( a, b ) ∈ R ⇒ ( b, a ) ∈ R.*   
  *Assume ( a, b ) ∈ R*  
  *Then ( a = b ).*  
  *This implies ( b = a ), so ( b, a ) ∈ R*  
  *Hence, (R) is symmetric.*

* *Transitive*
  *A relation (R) is transitive if ( a, b ) ∈ R and ( b, c ) ∈ R ⇒ ( a, c ) ∈ R*  
  *Assume( a, b ) ∈ R and ( b, c ) ∈ R Then ( a = b ) and ( b = c ).*  
  *So ( a = c ),  which implies ( a, c ) ∈ R*  
  *Hence, (R) is transitive.*

---

