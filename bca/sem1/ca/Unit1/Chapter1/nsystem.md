# Decimal conversions

## **🔢 Number Systems in Computer Architecture**

A **number system** defines how numbers are represented using digits and a **base (radix)**.

| Number System | Base | Digits Used |
| ----- | ----- | ----- |
| Decimal | 10 | 0–9 |
| Binary | 2 | 0, 1 |
| Octal | 8 | 0–7 |
| Hexadecimal | 16 | 0–9, A–F |

---

## **1️⃣ Decimal Number System (Base 10)**

* Used by humans

* Digits: **0–9**

* Example:  
  345₁₀ = 3 × 10² + 4 × 10¹ + 5 × 10⁰


---

## **2️⃣ Binary Number System (Base 2)**

* Used internally by computers

* Digits: **0 and 1**

* Each digit is called a **bit**

* Example:  
  $(1011)_2$ = 1 × 2³ \+ 0 × 2² \+ 1 × 2¹ \+ 1 × 2⁰ = 11₁₀

---

## **3️⃣ Octal Number System (Base 8\)**

* Digits: **0–7**

* Shorthand for binary (3 bits \= 1 octal digit)

* Example:  
  (17)₈ = (1111)₂ = (15)₁₀  

---

## **4️⃣ Hexadecimal Number System (Base 16\)**

* Digits: **0–9, A–F**

* Compact representation of binary

* Used in **memory addresses, machine code**

* Example:  
   (2F)₁₆ = (47)₁₀

| Hex | Binary |
| ----- | ----- |
| A | 1010 |
| F | 1111 |

---

## **🔁 Number System Conversions**

### **Decimal → Binary**

Divide by 2, record remainders

`25 → 11001₂`

### **Binary → Decimal**

Multiply each bit by power of 2

### **Binary → Octal**

Group bits in **3s**

### **Binary → Hexadecimal**

Group bits in **4s**

## **📌 Why Binary is Used in Computers**

* Easy to implement with **electronic switches**

* High reliability

* Simple logic operations

---

## **🧠 Applications in Computer Architecture**

* CPU operations

* Memory addressing

* Instruction encoding

* Data representation

**🔢 Decimal to Binary Conversion**  
 **There are two cases depending on whether the number is integer or fractional.**

---

**1️⃣ Decimal → Binary (Integer Part)**  
 Method: Repeated Division by 2

Steps:

1. Divide the decimal number by 2

2. Write down the remainder (0 or 1\)

3. Divide the quotient again by 2

4. Repeat until quotient becomes 0

5. Read the remainders from bottom to top ⬆️

Example: Convert 25₁₀ to Binary

Division Table:  
 25 ÷ 2 = 12 remainder 1  
 12 ÷ 2 = 6 remainder 0  
 6 ÷ 2 = 3 remainder 0  
 3 ÷ 2 = 1 remainder 1  
 1 ÷ 2 = 0 remainder 1

**Binary = 11001₂ ✅**

---

**2️⃣ Decimal → Binary (Fractional Part)**  
 **Method: Repeated Multiplication by 2**

Steps:

1. Multiply the fractional part by 2

2. Write down the integer part (0 or 1\)

3. Use the new fractional part

4. Repeat until fraction becomes 0 or desired precision

Example: Convert 0.625₁₀ to Binary

Multiplication Table:  
 0.625 × 2 = 1.25 → Integer part = 1  
 0.25 × 2 = 0.5 → Integer part = 0  
 0.5 × 2 = 1.0 → Integer part = 1

**Binary = 0.101₂ ✅**

---

**3️⃣ Decimal with Integer \+ Fraction**

Example: Convert 10.625₁₀ to Binary

* Integer part: 10 → 1010

* Fraction part: 0.625 → 0.101

**✅ Final Answer: 1010.101₂**

**Representation of Powers of 2:**

Powers of 2 are represented using an exponent notation where 2 is the base and the exponent indicates how many times the base is multiplied by itself. The expression 2^n means 2 raised to the power n. Positive exponents represent repeated multiplication by 2, zero exponent represents the value 1, and negative exponents represent the reciprocal of the corresponding positive power. This form of representation is widely used in computer architecture to describe binary weights, memory sizes, and number conversions.

🔢 **Decimal to Octal Conversion**  
 Octal number system uses base 8 (digits 0–7).

---

1️⃣ **Decimal → Octal (Integer Part)**  
 **Method:** Repeated Division by 8

**Steps:**

1. Divide the decimal number by 8

2. Write down the remainder (0–7)

3. Divide the quotient again by 8

4. Repeat until the quotient becomes 0

5. Read the remainders from **bottom to top**

**Example:** Convert 125₁₀ to Octal

Division Table:  
 125 ÷ 8 = 15 remainder 5  
 15 ÷ 8 = 1 remainder 7  
 1 ÷ 8 = 0 remainder 1

**Octal = 175₈**  
 💡 Note: "Rem" stands for remainder obtained by division.

2️⃣ **Decimal → Octal (Fractional Part)**  
 **Method:** Repeated Multiplication by 8

**Steps:**

1. Multiply the fractional part by 8

2. Write down the integer part

3. Use the new fractional part

4. Repeat until fraction becomes 0 or desired precision

**Example:** Convert 0.375₁₀ to Octal

Multiplication Table:  
 0.375 × 8 = 3.0 → Integer part = 3

**Octal = 0.3₈**

---

3️⃣ **Decimal with Integer \+ Fraction**

**Example:** Convert 10.375₁₀ to Octal

* Integer part: 10 → 12

* Fractional part: 0.375 → 0.3

✅ **Final Answer: 12.3₈**

---

📌 **Key Points (Small Note)**

* Integers → divide by 8 🔁

* Fractions → multiply by 8 ✖️

* Read integer remainders **bottom to top** ⬆️

* Read fractional digits **top to bottom** ⬇️  

**DECIMAL TO HEXADECIMAL CONVERSION**

Hexadecimal number system uses base 16\.  
 Digits used: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F  
 (A = 10, B = 11, C = 12, D = 13, E = 14, F = 15\)

---

1. Decimal to Hexadecimal (Integer Part)  
    Method: Repeated Division by 16

Steps:

1. Divide the decimal number by 16

2. Write the remainder (0–15). Convert 10–15 to A–F

3. Divide the quotient by 16 and repeat

4. Continue until the quotient is 0

5. Read the remainders from bottom to top

Example: Convert 254 to Hexadecimal  
 254 ÷ 16 = 15 remainder 14 (E)  
 15 ÷ 16 = 0 remainder 15 (F)  
 Hexadecimal = FE

---

2. Decimal to Hexadecimal (Fractional Part)  
    Method: Repeated Multiplication by 16

Steps:

1. Multiply the fractional part by 16

2. Take the integer part (0–15). Convert 10–15 to A–F

3. Use the new fractional part and repeat

4. Stop when fraction becomes 0 or desired precision is reached

Example: Convert 0.625 to Hexadecimal  
 0.625 × 16 = 10.0 → A  
 Hexadecimal = 0.A

---

3. Decimal with Integer and Fraction

Example: Convert 26.625 to Hexadecimal

* Integer part: 26 → 1A

* Fractional part: 0.625 → 0.A  
   Hexadecimal = 1A.A

---

**Powers of 10 (Decimal Number System)**

* Decimal number system uses base 10 (digits 0–9)

* Powers of 10 are written as 10ⁿ, where n can be positive, zero, or negative

* Positive powers: repeated multiplication by 10

* Zero power: 10⁰ = 1

* Negative powers: repeated division by 10

---

1. **Positive Powers of 10**  
    10⁰ = 1  
    10¹ = 10  
    10² = 100  
    10³ = 1,000  
    10⁴ = 10,000  
    10⁵ = 100,000  
    10⁶ = 1,000,000

Rule: 10ⁿ = 10 × 10 × … × 10 (n times)

---

2. **Zero Power of 10**  
    10⁰ = 1  
    Rule: Any non-zero number raised to the power 0 is 1

**Reason (Using Laws of Exponents):**  
 For any non-zero number aaa:  
 $a^m$ ÷ $a^n$ = $a^{(m−n)}$

If m = n:  
 $a^n$ ÷ $a^n$ = $a^{(n−n)}$ = $a^0$

But $a^n$ ÷ $a^n$ = 1, so $a^0$ = 1

---

3. **Negative Powers of 10**  
    10⁻¹ = 0.1  
    10⁻² = 0.01  
    10⁻³ = 0.001  
    10⁻⁴ = 0.0001  
    10⁻⁵ = 0.00001  
    10⁻⁶ = 0.000001

Rule: 10⁻ⁿ = 1 / 10ⁿ

---

Quick Tips:

* Positive powers → move decimal point to the right

* Negative powers → move decimal point to the left

* 10⁰ = 1 → acts as the neutral element

Key Points:

* Integer part → divide by 16

* Fractional part → multiply by 16

* Remainders 10–15 → A–F

* Read integer digits bottom to top, fractional digits top to bottom

# Binary conversions

🔢 **Binary Number System**

* Binary uses **base 2** (digits 0 and 1\)

* Each digit is called a **bit**

* Binary numbers are converted to other number systems using **weights (powers of 2\)**

---

### **1️⃣ Binary → Decimal Conversion**

**Method:** Multiply each bit by 2 raised to the position power (starting from 0 at the rightmost bit) and sum all results.

**Steps:**

1. Write the binary number.

2. Assign powers of 2 to each bit from right to left (0, 1, 2…).

3. Multiply each bit by $2^{position}$.

4. Add all results.

**Example:** Convert 1011₂ to Decimal

| BIT | 1 | 0 | 1 | 1 | 1 |
|-----|---|---|---|---|---|
| 2<sup>position</sup> | 2<sup>3</sup> | 2<sup>2</sup> | 2<sup>1</sup> | 2<sup>0</sup> |
| Multiply | 1×8 | 0×4 | 1×2 | 1×1 |

**Sum:** 8 \+ 0 \+ 2 \+ 1 = 11

✅ **Decimal = 11₁₀**

---

### **2️⃣ Binary → Octal Conversion**

**Method:** Group binary digits in **3s from right to left** (for integer part) and convert each group to octal.

**Steps:**

1. Write binary number.

2. Group bits in 3s from right to left. Add leading zeros if needed.

3. Convert each 3-bit group to octal.

**Example:** Convert 101101₂ to Octal

* Group: 101 101

* Convert: 101 → 5, 101 → 5

✅ **Octal = 55₈**

---

### **3️⃣ Binary → Hexadecimal Conversion**

**Method:** Group binary digits in **4s from right to left** (for integer part) and convert each group to hexadecimal.

**Steps:**

1. Write binary number.

2. Group bits in 4s from right to left. Add leading zeros if needed.

3. Convert each 4-bit group to hexadecimal (0–9, A–F).

**Example:** Convert 10110110₂ to Hexadecimal

* Group: 1011 0110

* Convert: 1011 → B, 0110 → 6

✅ **Hexadecimal = B6₁₆**

---

**🔢 Powers of 2 (Positive, Zero, and Negative)**

**Positive Powers of 2:**  
 $2^0$ = 1  
 $2^1$ = 2  
 $2^2$ = 4  
 $2^3$ = 8  
 $2^4$ = 16  
 $2^5$ = 32  
 $2^6$ = 64  
 $2^7$ = 128  
 $2^8$ = 256  
 $2^9$ = 512  
 $2^{10}$ = 1024  
 $2^{11}$ = 2048  
 $2^{12}$ = 4096  
 $2^{13}$ = 8192  
 $2^{14}$ = 16384  
 $2^{15}$ = 32768

**Negative Powers of 2:**  
 $2^{-1}$ = 0.5  
 $2^{-2}$ = 0.25  
 $2^{-3}$ = 0.125  
 $2^{-4}$ = 0.0625  
 $2^{-5}$ = 0.03125  
 $2^{-6}$ = 0.015625  
 $2^{-7}$ = 0.0078125  
 $2^{-8}$ = 0.00390625

**💡 Tip:**

* Positive powers → repeated multiplication by 2

* Negative powers → repeated division by 2

# Octal conversions

---

🔢 **Octal Number System**

* Octal uses **base 8** (digits 0–7)

* Each octal digit can be represented by **3 binary bits**

---

### **1️⃣ Octal → Binary Conversion**

**Method:** Convert each octal digit to its **3-bit binary equivalent**

**Steps:**

1. Write the octal number.

2. Replace each digit with its 3-bit binary equivalent.

**Example:** Convert 75₈ to Binary

* 7 → 111

* 5 → 101

✅ **Binary = 111101₂**

---

### **2️⃣ Octal → Decimal Conversion**

**Method:** Multiply each digit by **8 raised to its position power** (positions start from 0 on the right) and sum the results.

**Steps:**

1. Write the octal number.

2. Assign powers of 8 to each digit from right to left.

3. Multiply each digit by $8^{position}$.

4. Sum all results.

**Example:** Convert 75₈ to Decimal

| Digit | 7 | 5 |
| ----- | ----- | ----- |
| $8^{position}$ | $8^1$ | $8^0$ |
| Multiply | 7×8 = 56 | 5×1 = 5 |

**Sum:** 56 \+ 5 = 61

✅ **Decimal = 61₁₀**

---

### **3️⃣ Octal → Hexadecimal Conversion**

**Method 1:** **Via Binary** (simpler)

1. Convert octal → binary (each octal digit → 3 bits)

2. Group binary digits in **4s from right to left**

3. Convert each 4-bit group → hexadecimal

**Example:** Convert 75₈ to Hexadecimal

* Octal → Binary: 7 5 → 111 101 → 111101

* Group in 4s: 0011 1101 (added leading zeros)

* Convert each group: 0011 → 3, 1101 → D

✅ **Hexadecimal = 3D₁₆**

📌 **Tips:**

* **Octal → Binary:** 1 octal digit \= 3 binary bits

* **Octal → Decimal:** Multiply each digit by 8^position

* **Octal → Hexadecimal:** First convert to binary, then to hex

🔢 **Powers of 8 (Octal Base)**

* Base: 8 (digits 0–7)

* Powers of 8 are written as 8ⁿ, where n can be **positive, zero, or negative**

* Positive powers → repeated multiplication by 8

* Zero power → 8⁰ = 1

* Negative powers → repeated division by 8

---

### **1️⃣ Positive Powers of 8**

8⁰ = 1  
 8¹ = 8  
 8² = 64  
 8³ = 512  
 8⁴ = 4,096  
 8⁵ = 32,768  
 8⁶ = 262,144

**Rule:** 8ⁿ = 8 × 8 × … × 8 (n times)

---

### **2️⃣ Zero Power of 8**

8⁰ = 1

**Reason:** Any non-zero number raised to 0 is 1

---

### **3️⃣ Negative Powers of 8**

8⁻¹ = 1 / 8 = 0.125  
 8⁻² = 1 / 64 = 0.015625  
 8⁻³ = 1 / 512 = 0.001953125  
 8⁻⁴ = 1 / 4,096 = 0.000244140625  
 8⁻⁵ = 1 / 32,768 = 0.000030517578125

**Rule:** 8⁻ⁿ = 1 / 8ⁿ

---

📌 **Quick Tips:**

* Positive powers → multiply repeatedly

* Negative powers → divide repeatedly

* 8⁰ = 1 → neutral element

# Hexadecimal conversions

🔢 **Hexadecimal Number System**

* Hexadecimal uses **base 16** (digits 0–9 and letters A–F)

* Each hex digit can be represented by **4 binary bits**

---

### **1️⃣ Hexadecimal → Decimal Conversion**

**Method:** Multiply each digit by **16 raised to its position power** (positions start from 0 on the right) and sum the results.

**Steps:**

1. Write the hexadecimal number.

2. Assign powers of 16 to each digit from right to left.

3. Multiply each digit by $16^{position}$ (convert A–F → 10–15).

4. Sum all results.

**Example:** Convert 1A₁₆ to Decimal

| Digit | 1 | A(10 ) |
| ----- | ----- | ----- |
| $16^{position}$ | $16^1$ | $16^0$ |
| Multiply | 1×16 = 16 | 10×1 = 10 |

**Sum:** 16 \+ 10 = 26

✅ **Decimal = 26₁₀**

---

### **2️⃣ Hexadecimal → Binary Conversion**

**Method:** Convert each hexadecimal digit to its **4-bit binary equivalent**

**Steps:**

1. Write the hexadecimal number.

2. Replace each digit with its 4-bit binary equivalent.

**Example:** Convert 1A₁₆ to Binary

* 1 → 0001

* A → 1010

✅ **Binary = 00011010₂** (or 11010₂ removing leading zeros)

---

### **3️⃣ Hexadecimal → Octal Conversion**

**Method:** Convert hex → binary → octal

**Steps:**

1. Convert hex → binary (4 bits per hex digit)

2. Group binary digits in **3s from right to left**

3. Convert each 3-bit group → octal

**Example:** Convert 1A₁₆ to Octal

* Hex → Binary: 1 A → 0001 1010 → 00011010

* Group in 3s: 000 110 10 → add leading zeros → 000 110 010

* Convert each group: 000 → 0, 110 → 6, 010 → 2

✅ **Octal = 062₈**

---

📌 **Tips:**

* **Hex → Decimal:** Multiply digits by $16^{position}$

* **Hex → Binary:** 1 hex digit = 4 binary bits

* **Hex → Octal:** Convert via binary, then group in 3s

🔢 **Powers of 16 (Hexadecimal Base)**

* Base: 16 (digits 0–9 and A–F)

* Powers of 16 are written as 16ⁿ, where n can be **positive, zero, or negative**

* Positive powers → repeated multiplication by 16

* Zero power → 16⁰ = 1

* Negative powers → repeated division by 16

---

### **1️⃣ Positive Powers of 16**

16⁰ = 1  
 16¹ = 16  
 16² = 256  
 16³ = 4,096  
 16⁴ = 65,536  
 16⁵ = 1,048,576  
 16⁶ = 16,777,216

**Rule:** 16ⁿ = 16 × 16 × … × 16 (n times)

---

### **2️⃣ Zero Power of 16**

16⁰ = 1

**Reason:** Any non-zero number raised to 0 is 1

---

### **3️⃣ Negative Powers of 16**

16⁻¹ = 1 / 16 = 0.0625  
 16⁻² = 1 / 256 = 0.00390625  
 16⁻³ = 1 / 4,096 = 0.000244140625  
 16⁻⁴ = 1 / 65,536 = 0.0000152587890625  
 16⁻⁵ = 1 / 1,048,576 = 0.00000095367431640625

**Rule:** 16⁻ⁿ = 1 / 16ⁿ

---

📌 **Quick Tips:**

* Positive powers → multiply repeatedly

* Negative powers → divide repeatedly

* 16⁰ = 1 → neutral element

