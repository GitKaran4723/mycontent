# **Probability of an Event**

---

## **1\. What is Probability?**

* In daily life, probability means the **likelihood** or **chance** of something happening.

  * Example: “There is a 70% chance of rain tomorrow.”

* In mathematics, probability is a **measure** of how likely an event is to occur, expressed as a number between **0 and 1**.

👉 **Key Idea:**

*  P(E) \= 0  → Event is **impossible**.

* P(E) \= 1 → Event is **certain**.

* Values between 0 and 1 represent different degrees of likelihood.

---

## **2\. Classical Definition of Probability**

* **Formula:**  
   P(E) \= Number of Favorable OutcomesTotal number of outcomes in S  
   *(valid only when all outcomes are equally likely)*

* **Explanation:**

  * Favorable outcomes \= outcomes that satisfy event E.

  * Total outcomes \= size of sample space.

### **Examples:**

1. **Rolling a die** → Event: getting an even number.

   * Sample space  S \= {1,2,3,4,5,6}  (6 outcomes).  
   * Favorable outcomes \= {2,4,6} → 3 outcomes.  
   * P(E) \=36 \= 0.5  
        
2. **Tossing a coin** → Event: getting Head.

   * Sample space  S \= {H,T}  (2 outcomes).

   * Favorable outcomes \= {H} → 1 outcome.

   *  P(E) \= 0.5  
      

3. **Drawing a card** → Event: getting a King from a standard 52-card pack.

   * Favorable outcomes \= 4 Kings.

   * Total outcomes \= 52\.

   * P(E) \= 4/52 \= 1/13  
      

👉 **Limitations:**

* Only works if outcomes are equally likely.

* Cannot be directly applied to real-life complex cases like weather prediction.

---

## **3\. Axiomatic Definition of Probability (Kolmogorov’s Axioms)**

In modern probability theory, probability is defined axiomatically (mathematically rigorous).

Let (S) be the sample space, and (A) be an event (subset of (S)). Then a probability function (P) satisfies these **axioms**:

1. **Non-negativity:**  
      
    0  P(A)  1  
      
    The probability is always between 0 and 1\.

2. **Certainty:**  
      
    P(S) \= 1  
      
    The probability of the entire sample space is 1 (something from S must happen).

3. **Additivity (for mutually exclusive events):**

    P(A  B) \= P(A) \+ P(B)

---

### **Examples (Axiomatic Approach):**

1. Toss a coin once.

   * P(H) \= 0.5, P(T) \= 0.5.

   * Since (H) and (T) are mutually exclusive,  
        
      P(H  T) \= P(H) \+ P(T) \= 0.5 \+ 0.5 \= 1  
      

2. Roll a die. Let (A={2,4,6}) (even), (B={1,3,5}) (odd).

   * P(A) \= 0.5, P(B) \= 0.5.

   * (A) and (B) are mutually exclusive.

   * P(A  B) \= P(A) \+ P(B) \= 1  
      

👉 **Why Axiomatic Definition?**

* Works even when outcomes are not equally likely.

* Forms the basis of modern probability, useful in **advanced fields like AI, machine learning, risk management**.

---

## **4\. Purpose of Probability**

* Provides a **mathematical framework to measure uncertainty**.

* Helps us in:

  * Predicting events (weather, stock market, elections).

  * Making decisions under risk (business, insurance, quality control).

  * Scientific experiments (physics, biology, engineering).

* Acts as the **foundation** for probability rules, random variables, and statistical inference.

---

✅ **Quick Recap:**

* **Classical Definition:** Probability \= Favorable outcomes ÷ Total outcomes (works only for equally likely outcomes).

* **Axiomatic Definition:** Probability is defined by 3 rules (non-negativity, certainty, additivity).

* **Purpose:** Gives us a reliable, mathematical way of handling uncertainty.

---

