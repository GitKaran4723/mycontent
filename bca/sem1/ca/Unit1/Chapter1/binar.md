# **Binary Arithmetic**

## **1\. Binary Number System (Definition)**

The **binary number system** is a **base-2** number system that uses only **two digits:**

* **0**

* **1**

Each digit is called a **bit**.  
 Binary numbers are mainly used in **digital electronics and computers**.

**Example:**  
 Binary: `1011₂`  
 Decimal: `11₁₀`

---

## **2\. Important Terms**

### **Bit**

A **bit** is the smallest unit of data in computing and can be **0 or 1**.

### **Nibble**

A group of **4 bits**  
 Example: `1010`

### **Byte**

A group of **8 bits**  
 Example: `11001010`

### **Most Significant Bit (MSB)**

The **leftmost bit** of a binary number. It has the **highest value**.

### **Least Significant Bit (LSB)**

The **rightmost bit** of a binary number. It has the **lowest value**.

### **Binary Point**

Same as a decimal point but used in binary numbers.  
 Example: `101.01₂`

---

## **3\. Rules of Binary Arithmetic**

### **Basic Binary Rules**

Binary arithmetic follows simple rules based on **0 and 1**.

---

## **4\. Binary Addition**

### **Addition Rules**

<pre>
A   B   SUM   CARRY
0   0    0      0
0   1    1      0
1   0    1      0
1   1    0      1
</pre>

---

### **Example 1: Simple Addition**

  `1011`  
 `+ 1101`  
 `-------`  
 `11000`

### **Example 2: With Carry**

  `111`  
 `+ 101`  
 `-------`  
 `1100`

---

## **5\. Binary Subtraction**

### **Subtraction Rules**

| A | B | Result |
| ----- | ----- | ----- |
| 0 | 0 | 0 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |
| 0 | 1 | 1 (Borrow from next bit) |

---

### **Example 1: Simple Subtraction**

  `1011`  
 `- 0010`  
 `-------`  
   `1001`

### **Example 2: With Borrow**

  `1000`  
 `- 0001`  
 `-------`  
   `0111`

---

## **6\. Binary Multiplication**

### **Multiplication Rules**

| A | B | Product |
| ----- | ----- | ----- |
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

---

### **Example: Binary Multiplication**

  `101`  
 `×  11`  
 `------`  
   `101   (101 × 1)`  
 `+1010   (101 × 1, shifted left)`  
 `------`  
  `1111`

---

## **7\. Binary Division**

### **Division Rules**

Binary division is similar to decimal division but uses **0 and 1** only.

* If divisor is **greater**, write **0**

* If divisor is **equal or smaller**, write **1**

---

### **Example: Binary Division**

`1010 ÷ 10`

`10 )1010`  
     `10`  
     `----`  
      `10`  
      `10`  
     `----`  
       `0`

**Result:**  
 `1010 ÷ 10 = 101`

---

## **8\. Summary Table**

| Operation | Key Idea |
| ----- | ----- |
| Addition | Carry when 1 \+ 1 |
| Subtraction | Borrow when 0 − 1 |
| Multiplication | Same as decimal but simpler |
| Division | Repeated subtraction |

---

## **9\. Applications of Binary Arithmetic**

* Computer processors

* Digital circuits

* Programming

* Data storage

* Networking

