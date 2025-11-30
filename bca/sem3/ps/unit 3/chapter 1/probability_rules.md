# **Basic Probability Rules**

---

## **1\. Why Do We Need Rules?**

* In many problems, events are not isolated — they overlap or combine.

* **Basic probability rules** help us calculate probabilities systematically, especially when events interact.

* These rules are based on **set operations** (union, intersection, complement).

---

## **2\. Rule 1: The Range Rule**

* For any event (A):  
     
   0  P(A)  1  
   

* **Example:** If you roll a die, P(A) can never be negative or greater than 1\.

👉 Ensures probability always stays between 0 and 1\.

---

## **3\. Rule 2: Complement Rule**

* The probability of “not A” is:  
     
   P(A′) \= 1 \- P(A)  
   

* **Example:** Toss a coin.

  * (P(H) \= 0.5).

  * Probability of NOT getting Head (i.e., Tail):  
     P(H′) \= 1 \- 0.5 \= 0.5

Useful when it’s easier to calculate the complement than the event itself.

---

## **4\. Rule 3: Addition Rule**

This rule deals with “OR” situations (union of events).

### **(a) Mutually Exclusive Events (cannot happen together)**  P(A  B) \= P(A) \+ P(B)  

* **Example:** Roll a die. Event A={2}, Event B={5}.

  * P(A) \=1/6, (P(B) \= 1/6.

  * Since (A) and (B) cannot occur together,  
       
     P(A  B) \= 1/6 \+ 1/6 \= 2/6 \= 1/3  
     

---

### **(b) Non-Mutually Exclusive Events (can happen together)**

 P(A  B) \= P(A) \+ P(B) \- P(A  B)  
 

* **Example:** Roll a die.

  * Event A \= {2,4,6} (even).

  * Event B \= {3,4,5} (≥3 but ≤5).

  * P(A) \= 3/6, , P(B) \= 3/6, , P(A  B) \= 1/6 (since {4} is common).

  * P(A  B) \= 3/6 \+ 3/6 \- 1/6 \= 5/6

Addition rule avoids **double counting** overlapping outcomes.

---

## **5\. Rule 4: Multiplication Rule**

This rule deals with “AND” situations (intersection of events).

### **(a) Independent Events**

 P(A  B) \= P(A) x P(B)  
 

* **Example:** Toss 2 coins.

  * Event (A): First coin is Head → P(A)= 1/2.

  * Event (B): Second coin is Head → P(B)=1/2.

  * Since independent,  
       
     P(A  B) \= 1/2 x 1/2 \= 1/4

---

### **(b) Dependent Events**

If events affect each other:  
   
 P(A  B) \= P(A) x P(B|A)  
 

* **Example:** Drawing 2 cards **without replacement**.

  * Event (A): First card is an Ace → P(A) \= 4/52.

  * Event (B): Second card is an Ace given first was Ace → (P(B|A) \= \\tfrac{3}{51}).

  * \[  
     P(A \\cap B) \= \\tfrac{4}{52} \\times \\tfrac{3}{51} \= \\tfrac{1}{221}  
     \]

👉 Multiplication rule handles both **independent** and **dependent** events.

---

## **6\. Rule 5: Law of Total Probability**

If events (A\_1, A\_2, \\dots, A\_n) are mutually exclusive and cover the whole sample space (S):  
 \[  
 P(B) \= \\sum\_{i=1}^n P(A\_i) P(B|A\_i)  
 \]

* **Example:** A factory has 3 machines producing 30%, 50%, and 20% of total items.

  * Defect rates \= 1%, 2%, 3% respectively.

  * Probability of defective item \=  
     \[  
     0.3(0.01) \+ 0.5(0.02) \+ 0.2(0.03) \= 0.019  
     \]

👉 Helps when probabilities come from different sources.

---

## **7\. Rule 6: Boole’s Inequality**

For any events (A\_1, A\_2, \\dots, A\_n):  
 \[  
 P(A\_1 \\cup A\_2 \\cup \\dots \\cup A\_n) \\leq P(A\_1) \+ P(A\_2) \+ \\dots \+ P(A\_n)  
 \]

👉 Useful when exact probability is hard, but an **upper bound** is needed.

---

## **8\. Purpose**

* Rules are the **grammar of probability**.

* They allow us to:

  * Handle complex event combinations.

  * Avoid errors like double-counting.

  * Work with both independent and dependent events.

  * Solve real-world problems in insurance, finance, computer science, and engineering.

---

✅ **Quick Recap:**

* Complement Rule: (P(A′) \= 1 \- P(A))

* Addition Rule: (P(A \\cup B) \= P(A) \+ P(B) \- P(A \\cap B))

* Multiplication Rule: (P(A \\cap B) \= P(A) \\times P(B|A))

* Probabilities always between 0 and 1\.

* Advanced: Law of Total Probability, Boole’s Inequality.

---

Would you like me to next prepare **Concept 5: Applications of Probability Rules** in the same style, with **real-life and exam-style solved problems**?

