# Complements in Number System

## **1\. What is a Complement? (Definition)**

A **complement** of a number is a method used in number systems to:

* Perform **subtraction using addition**

* Represent **negative numbers**

* Simplify **computer arithmetic**

Complements depend on the **base (r)** of the number system.

---

## **2\. Base (r) of a Number System**

| Number System | Base (r) |
| ----- | ----- |
| Binary | 2 |
| Decimal | 10 |
| Octal | 8 |
| Hexadecimal | 16 |

---

## **3\. Types of Complements**

For any base **r**, there are **two types of complements**:

1. **(r − 1)’s complement**

2. **r’s complement**

---

# **4\. (r − 1)’s Complement**

## **Definition**

The **(r − 1)’s complement** of a number is obtained by **subtracting each digit of the number from (r − 1\)**.

### **Formula**

`(r − 1)’s complement of N = (r − 1) − each digit of N`

---

## **How to Find (r − 1)’s Complement**

### **Step-by-Step Method**

1. Identify the **base (r)**.

2. Subtract each digit from **(r − 1\)**.

3. Replace each digit with the result.

---

## **Examples**

### **Binary System (r \= 2\)**

* (r − 1\) \= 1

* **1’s complement**

**Example:**  
 Binary number: `1010`

`1 → 0`  
`0 → 1`  
`1 → 0`  
`0 → 1`

**1’s complement \= `0101`**

---

### **Decimal System (r \= 10\)**

* (r − 1\) \= 9

* **9’s complement**

**Example:**  
 Decimal number: `345`

`9 − 3 = 6`  
`9 − 4 = 5`  
`9 − 5 = 4`

**9’s complement \= `654`**

---

### **Octal System (r \= 8\)**

* (r − 1\) \= 7

**Example:**  
 `526₈`

`7 − 5 = 2`  
`7 − 2 = 5`  
`7 − 6 = 1`

**7’s complement \= `251₈`**

---

# **5\. r’s Complement**

## **Definition**

The **r’s complement** of a number is obtained by:

* Taking the **(r − 1)’s complement**

* **Adding 1** to it

---

## **Formula**

`r’s complement = (r − 1)’s complement + 1`

---

## **How to Find r’s Complement (Steps)**

1. Find the **(r − 1)’s complement**

2. Add **1** to the result

3. Ignore any overflow carry

---

## **Examples**

### **Binary System (r \= 2\)**

* r’s complement \= **2’s complement**

**Example:**  
 Binary number: `1010`

Step 1: Find 1’s complement

`1010 → 0101`

Step 2: Add 1

`0101`  
`+   1`  
`------`  
`0110`

**2’s complement \= `0110`**

---

### **Decimal System (r \= 10\)**

* r’s complement \= **10’s complement**

**Example:**  
 Decimal number: `345`

Step 1: 9’s complement  
 `654`

Step 2: Add 1

`654 + 1 = 655`

**10’s complement \= `655`**

---

### **Octal System (r \= 8\)**

* r’s complement \= **8’s complement**

**Example:**  
 `526₈`

Step 1: 7’s complement \= `251₈`  
 Step 2: Add 1

`251 + 1 = 252₈`

---

# **6\. Special Complements in Binary**

| Complement | Name |
| ----- | ----- |
| (r − 1)’s complement | 1’s complement |
| r’s complement | 2’s complement |

---

# **7\. Advantages of r’s Complement**

* Faster subtraction

* Used in **computer hardware**

* Represents negative numbers

* Only **addition circuitry** needed

---

# **8\. Comparison Table**

| Feature | (r − 1)’s Complement | r’s Complement |
| ----- | ----- | ----- |
| Extra step | No | Yes (add 1\) |
| Negative number representation | Less common | Most common |
| Used in computers | Rare | Widely used |

---

# **9\. Key Exam Points**

✔ r \= base of number system  
 ✔ (r − 1)’s complement → digit subtraction  
 ✔ r’s complement → add 1  
 ✔ Binary → 1’s & 2’s complement  
 ✔ Decimal → 9’s & 10’s complement

# Binary Subtraction Using Complements

In binary number system:

* Base **r \= 2**

* **(r – 1)’s complement \= 1’s complement**

* **r’s complement \= 2’s complement**

Binary subtraction can be done **without direct subtraction**, by using **addition and complements**.

---

## **1\. Why Use Complements for Subtraction?**

Computers:

* Cannot subtract directly

* Use **addition only**

* Use complements to represent **negative numbers**

So,

`A − B = A + (complement of B)`

---

# **2\. Binary Subtraction Using (r – 1)’s Complement**

### ***(Using 1’s Complement)***

---

## **Definition**

In this method:

* Take the **1’s complement of the subtrahend**

* Add it to the minuend

* Adjust result depending on carry

---

## **Rules (Important for Exam)**

1. Find **1’s complement** of subtrahend.

2. Add it to minuend.

3. **If carry is generated**:

   * Add the carry to LSB (**end-around carry**)

   * Result is **positive**

4. **If no carry**:

   * Take 1’s complement of result

   * Prefix **negative sign (−)**

---

## **Example 1: Positive Result (Carry Occurs)**

### **Example**

`A = 1101₂ (13)`  
`B = 0011₂ (3)`  
`Find: A − B`

### **Step 1: 1’s complement of B**

`B = 0011`  
`1’s complement = 1100`

### **Step 2: Add to A**

 `1101`  
`+ 1100`  
`--------`  
 `11001`

### **Step 3: End-around carry**

Carry \= `1`

`1001 + 1 = 1010`

### **Final Answer**

`1010₂ (10)`

✔ Correct because 13 − 3 \= 10

---

## **Example 2: Negative Result (No Carry)**

### **Example**

`A = 0101₂ (5)`  
`B = 1001₂ (9)`  
`Find: A − B`

### **Step 1: 1’s complement of B**

`1001 → 0110`

### **Step 2: Add to A**

`0101`  
`+0110`  
`------`  
 `1011`

### **Step 3: No carry → Negative result**

Take 1’s complement of result:

`1011 → 0100`

### **Final Answer**

`−0100₂ (−4)`

✔ Correct because 5 − 9 \= −4

---

# **3\. Binary Subtraction Using r’s Complement**

### ***(Using 2’s Complement)***

---

## **Definition**

In this method:

* Take **2’s complement** of the subtrahend

* Add it to the minuend

* Discard carry if present

---

## **Rules (Very Important)**

1. Find **2’s complement** of subtrahend.

2. Add it to minuend.

3. **If carry occurs**:

   * Discard carry

   * Result is **positive**

4. **If no carry**:

   * Take 2’s complement of result

   * Prefix **negative sign**

---

## **Example 3: Positive Result (Carry Occurs)**

### **Example**

`A = 1010₂ (10)`  
`B = 0011₂ (3)`  
`Find: A − B`

### **Step 1: 2’s complement of B**

`B = 0011`  
`1’s complement = 1100`  
`+1`  
`------`  
`1101`

### **Step 2: Add to A**

`1010`  
`+1101`  
`------`  
`10111`

### **Step 3: Discard carry**

`0111₂`

### **Final Answer**

`0111₂ (7)`

✔ Correct because 10 − 3 \= 7

---

## **Example 4: Negative Result (No Carry)**

### **Example**

`A = 0101₂ (5)`  
`B = 1000₂ (8)`  
`Find: A − B`

### **Step 1: 2’s complement of B**

`1000`  
`1’s complement = 0111`  
`+1`  
`------`  
`1000`

### **Step 2: Add to A**

`0101`  
`+1000`  
`------`  
 `1101`

### **Step 3: No carry → Negative**

Take 2’s complement of result:

`1101`  
`1’s complement = 0010`  
`+1`  
`------`  
`0011`

### **Final Answer**

`−0011₂ (−3)`

✔ Correct because 5 − 8 \= −3

---

# **4\. Key Differences Between r and (r−1) Complement**

| Feature | 1’s Complement (r−1) | 2’s Complement (r) |
| ----- | ----- | ----- |
| Carry handling | End-around carry | Discard carry |
| Zero representation | Two zeros | One zero |
| Hardware use | Rare | Widely used |
| Complexity | More steps | Simpler |

---

# **5\. Why 2’s Complement is Preferred**

✔ Single zero  
 ✔ Faster arithmetic  
 ✔ Easy sign detection  
 ✔ Used in **computer processors**

---

# **6\. Exam-Ready Summary**

* Binary base **r \= 2**

* 1’s complement \= invert bits

* 2’s complement \= invert bits \+ 1

* Carry → positive

* No carry → negative

* Negative result → take complement again

