# **OCTAL ARITHMETIC (BASE–8)** 

---

## **1\. Octal Number System**

### **Definition**

The **octal number system** is a **base-8** number system.

### **Base (r)**

`r = 8`

### **Digits Used**

`0, 1, 2, 3, 4, 5, 6, 7`

⚠ Digits **8 and 9 are not allowed** in octal.

---

## **2\. Place Value in Octal System**

Each position has a weight of a power of **8**.

| Position | Power | Value |
| ----- | ----- | ----- |
| Rightmost | 8⁰ | 1 |
| Next | 8¹ | 8 |
| Next | 8² | 64 |
| Next | 8³ | 512 |

### **Example**

`(526)₈`  
`= 5×8² + 2×8¹ + 6×8⁰`  
`= 5×64 + 2×8 + 6×1`  
`= 320 + 16 + 6`  
`= 342₁₀`

---

## **3\. Relation Between Octal and Binary**

Each **octal digit corresponds to 3 binary bits**.

### **Octal to Binary Table**

| Octal | Binary |
| ----- | ----- |
| 0 | 000 |
| 1 | 001 |
| 2 | 010 |
| 3 | 011 |
| 4 | 100 |
| 5 | 101 |
| 6 | 110 |
| 7 | 111 |

✔ This makes octal arithmetic easier by converting to binary if required.

---

## **4\. Octal Addition**

---

### **Rules for Octal Addition**

1. Add digits column-wise (right to left)

2. If **sum \< 8** → write sum

3. If **sum ≥ 8**:

   * Write **(sum − 8\)**

   * Carry **1** to next column

---

### **Octal Addition Table (Important)**

| A \+ B | Result |
| ----- | ----- |
| 3 \+ 4 | 7 |
| 5 \+ 3 | 10₈ |
| 6 \+ 4 | 12₈ |
| 7 \+ 7 | 16₈ |

---

### **Example 1: Simple Addition**

 `245₈`  
`+ 132₈`  
`------`  
  `377₈`

---

### **Example 2: Addition with Carry**

 `567₈`  
`+ 245₈`  
`------`  
 `1034₈`

✔ Correct because carries are handled in base-8.

---

## **5\. Octal Subtraction (Direct Method)**

---

### **Rules for Octal Subtraction**

1. Subtract digit by digit

2. If **top digit ≥ bottom digit**, subtract directly

3. If **top digit \< bottom digit**:

   * Borrow **1 from next column**

   * Borrowed value \= **8**

---

### **Example 1: Simple Subtraction**

 `654₈`  
`− 243₈`  
`------`  
  `411₈`

---

### **Example 2: Subtraction with Borrow**

 `503₈`  
`− 267₈`

Borrow process:

 `503₈`  
`− 267₈`  
`------`  
  `214₈`

---

## **6\. Octal Subtraction Using Complements**

Used in **digital systems** instead of borrowing.

---

### **Complements in Octal**

| Complement Type | Name |
| ----- | ----- |
| (r − 1)’s | **7’s complement** |
| r’s | **8’s complement** |

---

### **7’s Complement**

Subtract each digit from **7**

**Example**

`237₈`  
`7’s complement = 540₈`

---

### **8’s Complement**

`8’s complement = 7’s complement + 1`

**Example**

`7’s comp of 237 = 540`  
`+1`  
`---`  
`541₈`

---

### **Steps for Subtraction Using 8’s Complement**

1. Find **8’s complement** of subtrahend

2. Add it to minuend

3. If **carry occurs** → discard carry (positive result)

4. If **no carry** → take 8’s complement of result and prefix **minus sign**

---

### **Example**

`654₈ − 237₈`

8’s complement of 237₈ \= `541₈`

Add:

`654`  
`+541`  
`----`  
`1415`

Discard carry:

`415₈`

✔ Correct result

---

## **7\. Octal Multiplication**

---

### **Rules**

1. Multiply digits like decimal

2. If product ≥ 8:

   * Write remainder

   * Carry quotient

---

### **Multiplication Table (Partial)**

| × | 2 | 3 | 4 |
| ----- | ----- | ----- | ----- |
| 4 | 10₈ | 14₈ | 20₈ |
| 7 | 16₈ | 25₈ | 34₈ |

---

### **Example**

 `37₈`  
`×  5₈`  
`-----`  
 `233₈`

---

## **8\. Octal Division**

---

### **Rules**

* Similar to decimal division

* Quotient digits must be **0–7**

* Remainder \< divisor

---

### **Example**

 644₈ ÷ 4₈

---

## **`Step-by-Step Solution (Long Division Method)`**

     `161₈`  
`4 ) 644₈`  
    `4`  
    `----`  
    `24`  
    `24`  
    `----`  
     `4`  
      `4`  
     `----`  
      `0`

### **`Explanation`**

1. **`6 ÷ 4 = 1`**`, remainder 2`

2. `Bring down 4 → 24₈`

3. **`24₈ ÷ 4 = 6`**`, remainder 0`

4. `Bring down 4`

5. **`4 ÷ 4 = 1`**`, remainder 0`

---

## **`Final Answer`**

644₈ ÷ 4₈ = 161₈

---

## **`Verification (Optional but Confirms Accuracy)`**

161₈ × 4₈ = 644₈ ✔

---

### **`Key Exam Points`**

* `Base = 8`

* `Quotient digits must be 0–7`

* `Remainder < divisor`

* `Borrow/carry uses 8, not 10`

---

## **9\. Octal Fractions**

### **Example**

`0.25₈`  
`= 2×8⁻¹ + 5×8⁻²`  
`= 0.3125₁₀`

---

## **10\. Advantages of Octal Arithmetic**

✔ Compact representation of binary  
 ✔ Easy conversion to binary  
 ✔ Useful in early computing systems

---

## **11\. Exam-Ready Summary**

* Base of octal \= **8**

* Digits \= **0 to 7**

* Carry and borrow \= **8**

* Complements: **7’s and 8’s**

* Each octal digit \= **3 binary bits**

