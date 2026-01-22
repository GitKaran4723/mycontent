# **De Morgan's Law in Set Theory**

 In set theory, there are two De Morgan's Laws that are:

* First De Morgan's Law  
* Second De Morgan's Law

## **First De Morgan's Law**

First De Morgan's law states that **"The complement of the union of two sets is equal to the intersection of the complements of each set."**

Let A and B be two sets, then mathematically First De Morgan's Law is given as:

***(A ∪ B)' = A' ∩ B'***  
Where 

* **U** represents the Union operation between sets,  
* **∩** represents the intersection operation between sets, and   
* **'** represents complement operation on a set.

It is also called **De Morgan's Law of Union.**

### **Proof Using Algebra of Sets**

 We need to prove, (A ∪ B)' = A' ∩ B' Let X = (A ∪ B)' and Y = A' ∩ B' Let p be any element of X, then p ∈ X ⇒ p ∈ (A ∪ B)' ⇒ p ∉ (A ∪ B) ⇒ p ∉ A or p ∉ B ⇒ p ∈ A' and p ∈ B' ⇒ p ∈ A' ∩ B' ⇒ p ∈ Y

∴ X ⊂ Y              . . . (i)

Again, let q be any element of Y, then q ∈ Y ⇒ q ∈ A' ∩ B'  
⇒ q ∈ A' and q ∈ B'  
⇒ q ∉ A and q ∉ B  
⇒ q ∉ (A ∪ B)  
⇒ q ∈ (A ∪ B)'  
⇒ q ∈ X

∴ Y ⊂ X              . . . (ii)

From (i) and (ii) X = Y

(A ∪ B)' = A' ∩ B'

## **Second De Morgan's Law**

Second, De Morgan's law states that **"The complement of intersection of two sets is equal to the union of the complements of each set."**

Let A and B be two sets, then mathematically First De Morgan's Law is given as:

***(A ∩ B)' = A' ∪ B'***  
Where 

* **U** represents the Union operation between sets,  
* **∩** represents the intersection operation between sets, and   
* **'** represents complement operation on a set.

It is also called **De Morgan's Law of Intersection**.

### **Proof Using Algebra of Sets**

Second De Morgan's law: (A ∩ B)' = A' ∪ B'

Let X = (A ∩ B)' and Y = A' ∪ B'  
Let p be any element of X, then p ∈ X ⇒ p ∈ (A ∩ B)'  
⇒ p ∉ (A ∩ B)  
⇒ p ∉ A or p ∉ B  
⇒ p ∈ A' or p ∈ B'  
⇒ p ∈ A' ∪ B'  
⇒ p ∈ Y

∴ X ⊂ Y \--------------(i)

Again, let q be any element of Y, then q ∈ Y ⇒ q ∈ A' ∪ B'

⇒ q ∈ A' or q ∈ B'  
⇒ q ∉ A and q ∉ B  
⇒ q ∉ (A ∩ B)  
⇒ q ∈ (A ∩ B)'  
⇒ q ∈ X

∴ Y ⊂ X \--------------(ii)

From (i) and (ii) X = Y

(A ∩ B)' = A' ∪ B'

## **Solved Question on De Morgan's Law**

**Question 1:** Given that U = {2, 3, 7, 8, 9}, A = {2, 7} and B = {2, 3, 9}. Prove De Morgan's Second Law.

**Solution:**

*U = {2, 3, 7, 8, 9}, A = {2, 7} and B = {2, 3, 9}*  
*To Prove: (A ∩ B)' = A' ∪ B'*  
*(A ∩ B) = {2}*  
*(A ∩ B)' = U \- (A ∩ B) = {2, 3, 7, 8, 9} \- {2}*  
***(A ∩ B)' = {3, 7, 8, 9}***  
*A' = U \- A = {2, 3, 7, 8, 9} \- {2, 7}*  
*A' = {3, 8, 9}*  
*B' = U \- B = {2, 3, 7, 8, 9} \- {2, 3, 9}*  
*B' = {7, 8}*  
*A' ∪ B' = {3, 8, 9} ∪ {7, 8}*  
***A' ∪ B' = {3, 7, 8, 9}***

***(A ∩ B)' = A' ∪ B'***

**Question 2:** Given that U = {1, 4, 6, 8, 9}, A = {1, 9} and B = {4, 6, 9}. Prove De Morgan's First Law.

**Solution:**

*U = {1, 4, 6, 8, 9}, A = {1, 9} and B = {4, 6, 9}*  
*To Prove: (A ∪ B)' = A' ∩ B'*  
*(A ∪ B) = {1, 4, 6, 9}*  
*(A ∪ B)' = U \- (A ∪ B) = {1, 4, 6, 8, 9} \- {1, 4, 6, 9}*  
***(A ∪ B)' = {8}***  
*A' = U \- A = {1, 4, 6, 8, 9} \- {1, 9}*  
*A' = {4, 6, 8}*  
*B' = U \- B = {1, 4, 6, 8, 9} \- {4, 6, 9}*  
*B' = {1, 8}*  
*A' ∩ B' = {4, 6, 8} ∩ {1, 8}*  
***A' ∩ B' = {8}***  
***(A ∪ B)' = A' ∩ B'***

