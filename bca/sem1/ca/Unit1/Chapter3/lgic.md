# **LOGIC GATES**

---

## **1\. What is a Logic Gate?**

A **logic gate** is a basic digital electronic circuit that performs a logical operation on one or more **binary inputs (0 or 1\)** and produces a **single binary output** according to the rules of **Boolean algebra**.

Logic gates are the fundamental building blocks of:

* Digital computers

* Microprocessors

* Memory units

* Control circuits

* Digital communication systems

---

## **2\. Types of Logic Gates**

Logic gates are classified into:

### **Basic Logic Gates**

* AND

* OR

* NOT

### **Special / Derived Logic Gates**

* XOR

* XNOR

---

## **3\. BASIC LOGIC GATES**

---

### **3.1 AND Gate**

**Definition:**  
 An **AND gate** produces an output **1 only when all its inputs are 1**.  
 If any input is 0, the output is 0\.

**Boolean Expression:**  
 Y \= A \* B

**Truth Table:**

| A | B | Y |
| ----- | ----- | ----- |
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

**Working:**  
 The AND gate performs **logical multiplication**. The output is high only when **all input conditions are satisfied**.

**Applications:**

* Enable circuits

* Control systems

* Multiplication in digital circuits

---

### **3.2 OR Gate**

**Definition:**  
 An **OR gate** produces an output **1 if any one or more inputs are 1**.  
 The output is 0 only when **all inputs are 0**.

**Boolean Expression:**  
 Y \= A \+ B

**Truth Table:**

| A | B | Y |
| ----- | ----- | ----- |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

**Working:**  
 The OR gate performs **logical addition**.

**Applications:**

* Alarm circuits

* Decision-making circuits

---

### **3.3 NOT Gate (Inverter)**

**Definition:**  
 A **NOT gate** produces an output that is the **complement of the input**.

**Boolean Expression:**  
 Y \= NOT A

**Truth Table:**

| A | Y |
| ----- | ----- |
| 0 | 1 |
| 1 | 0 |

**Working:**  
 The NOT gate **inverts** the input signal.

**Applications:**

* Bit inversion

* Signal complementing

---

## **4\. SPECIAL / DERIVED LOGIC GATES**

---

### **4.1 XOR Gate (Exclusive OR)**

**Definition:**  
 An **XOR gate** produces an output **1 when the inputs are different**.  
 The output is 0 when the inputs are the same.

**Boolean Expression:**  
 Y \= A XOR B

**Truth Table:**

| A | B | Y |
| ----- | ----- | ----- |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

**Working:**  
 The XOR gate performs **modulo-2 addition**.

**Applications:**

* Half adders

* Full adders

* Parity checking

* Error detection

---

### **4.2 XNOR Gate (Exclusive NOR)**

**Definition:**  
 An **XNOR gate** produces an output **1 when both inputs are the same**.

**Boolean Expression:**  
 Y \= NOT (A XOR B)

**Truth Table:**

| A | B | Y |
| ----- | ----- | ----- |
| 0 | 0 | 1 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

**Applications:**

* Equality comparators

* Error checking

---

## **5\. Summary Table of All Logic Gates**

| Gate | Function | Boolean Expression |
| ----- | ----- | ----- |
| AND | All inputs must be 1 | A \* B |
| OR | Any input is 1 | A \+ B |
| NOT | Complement | NOT A |
| XOR | Inputs different | A XOR B |
| XNOR | Inputs same | NOT (A XOR B) |

---

## **6\. Importance of Logic Gates**

* Form the **basis of digital electronics**

* Used in **arithmetic circuits, memory, and control units**

* Essential for **computer architecture and VLSI design**

