## **1\. What is the Hexadecimal Number System?**

Hexadecimal (often called **hex**) is a **base-16** number system.

### **Digits Used**

Hex uses **16 symbols**:

| Decimal | Hex |
| ----- | ----- |
| 0–9 | 0–9 |
| 10 | A |
| 11 | B |
| 12 | C |
| 13 | D |
| 14 | E |
| 15 | F |

So after 9 comes **A, B, C, D, E, F**, then it rolls over.

### **Why Hexadecimal Is Used**

Hexadecimal is widely used in computing because:

* It maps neatly to **binary** (1 hex digit \= 4 binary bits)

* It is shorter and easier to read than long binary numbers

* Used in **memory addresses, machine code, colors (HTML), debugging**

Example:

`Binary: 110111101010110110101011`  
`Hex:    DEADAB`

---

## **2\. Place Value in Hexadecimal**

Just like decimal is based on powers of 10, hex is based on **powers of 16**.

### **Place Values**

| Position | Power of 16 |
| ----- | ----- |
| 1st (rightmost) | 16⁰ \= 1 |
| 2nd | 16¹ \= 16 |
| 3rd | 16² \= 256 |
| 4th | 16³ \= 4096 |

### **Example**

Hex number:

`2F3₁₆`

Convert to decimal:

`= 2×16² + F×16¹ + 3×16⁰`  
`= 2×256 + 15×16 + 3`  
`= 512 + 240 + 3`  
`= 755₁₀`

---

## **3\. Hexadecimal Addition**

### **Rules**

1. Add digits just like decimal

2. If the result ≥ 16, **carry 1** to the next column

3. Use hex digit values (A=10, B=11, etc.)

### **Hex Addition Table (Common Sums)**

| Hex | \+1 |
| ----- | ----- |
| 9 | A |
| A | B |
| B | C |
| C | D |
| D | E |
| E | F |
| F | 10 (carry 1\) |

---

### **Example 1: Simple Addition**

  `A3`  
`+  1F`  
`------`

Step by step:

* 3 \+ F \= 18₁₀ \= **12₁₆** → write 2, carry 1

* A \+ 1 \+ carry \= 12₁₀ \= **C**

Result:

`C2₁₆`

---

### **Example 2: Larger Addition**

 `4E7`  
`+ 2B9`  
`------`

* 7 \+ 9 \= 16 → 0, carry 1

* E(14) \+ B(11) \+ 1 \= 26 → 1A → write A, carry 1

* 4 \+ 2 \+ 1 \= 7

Result:

`7A0₁₆`

---

## **4\. Hexadecimal Subtraction**

### **Rules**

* Subtract like decimal

* Borrow **16** instead of 10

* Convert letters to decimal mentally if needed

---

### **Example 1: Simple Subtraction**

 `B5`  
`- 3A`  
`-----`

* 5 − A → borrow from B

* 5 \+ 16 \= 21 → 21 − 10 \= 11 (B)

* B becomes A

* A − 3 \= 7

Result:

`7B₁₆`

---

### **Example 2: Multiple Borrows**

 `100`  
`-  2F`  
`-----`

* 0 − F → borrow from next column

* After borrowing:

  * 16 − 15 \= 1

  * Next column becomes F

* F − 2 \= D

Result:

`D1₁₆`

---

## **5\. Hexadecimal Multiplication**

### **Rules**

* Multiply digits as decimal values

* Convert product back to hex

* Shift left (×16) for each position

---

### **Example 1: Single-Digit**

`A × 4`

* A \= 10

* 10 × 4 \= 40₁₀

* 40₁₀ \= 28₁₆

Answer:

`28₁₆`

---

### **Example 2: Multi-Digit**

  `2F`  
`×  3`  
`-----`

* F × 3 \= 45 → 2D → write D, carry 2

* 2 × 3 \+ 2 \= 8

Result:

`8D₁₆`

---

## **6\. Hexadecimal Division**

### **Rules**

1. Convert divisor to decimal if needed

2. Divide like decimal long division

3. Convert results back to hex

---

### **Example**

`9C ÷ 4`

* 9C₁₆ \= 156₁₀

* 156 ÷ 4 \= 39

* 39₁₀ \= 27₁₆

Answer:

`27₁₆`

---

## **7\. Conversion Between Hex and Binary**

### **Hex → Binary**

Each hex digit \= **4 bits**

| Hex | Binary |
| ----- | ----- |
| 0 | 0000 |
| 1 | 0001 |
| A | 1010 |
| F | 1111 |

Example:

`3A₁₆ = 0011 1010₂`

---

### **Binary → Hex**

Group bits in sets of 4\.

Example:

`10110110₂`  
`= 1011 0110`  
`= B6₁₆`

---

## **8\. Hexadecimal vs Decimal vs Binary**

| System | Base | Digits |
| ----- | ----- | ----- |
| Binary | 2 | 0–1 |
| Decimal | 10 | 0–9 |
| Hexadecimal | 16 | 0–9, A–F |

---

## **9\. Real-World Applications of Hex Arithmetic**

* **Memory addressing** (0x7FFF)

* **Machine language**

* **Color codes** (\#FF5733)

* **Debugging tools**

* **Networking & protocols**

---

## **10\. Key Takeaways**

* Hex is base-16

* Letters A–F represent 10–15

* Carry and borrow happen at **16**

* Hex arithmetic follows the same logic as decimal

* Hex is a compact representation of binary

