# 1

# **DECIMAL CODES** 

---

## **1\. What Are Decimal Codes?**

**Decimal codes** are **binary codes used to represent decimal numbers (0–9)** in digital systems.

Since computers operate in **binary (0 and 1\)** but humans use **decimal (0–9)**, decimal codes act as a **bridge** between human-readable numbers and machine-readable binary form.

👉 Each **decimal digit** is represented separately using **binary bits**.

---

## **2\. Why Decimal Codes Are Needed**

* Digital systems work in binary

* Humans use decimal numbers

* Direct binary representation is difficult for decimal displays

* Decimal codes allow **accurate decimal representation and display**

Used in:

* Calculators

* Digital clocks

* Digital meters

* Financial and commercial systems

---

## **3\. Classification of Decimal Codes**

Decimal codes are mainly classified into:

### **A. Weighted Decimal Codes**

Each bit position has a fixed weight.

### **B. Non-Weighted Decimal Codes**

No fixed positional weights.

---

## **4\. Weighted Decimal Codes**

---

### **4.1 8421 BCD Code (Binary Coded Decimal)**

This is the **most common decimal code**.

#### **Weights:**

`8   4   2   1`

| Decimal Digit | 8421 BCD |
| ----- | ----- |
| 0 | 0000 |
| 1 | 0001 |
| 5 | 0101 |
| 9 | 1001 |

❌ Invalid BCD combinations: **1010 to 1111**

#### **Example**

Decimal number: **59**

`5 → 0101`  
`9 → 1001`  
`BCD = 0101 1001`

#### **Advantages**

* Simple

* Easy decimal display

* Widely used

#### **Disadvantages**

* Wastes bits

* Arithmetic is slower than pure binary

---

### **4.2 2421 Code**

Weights:

`2   4   2   1`

| Decimal | 2421 |
| ----- | ----- |
| 0 | 0000 |
| 5 | 1011 |
| 9 | 1111 |

#### **Features**

* **Self-complementing code**

* 9’s complement obtained by bit inversion

---

### **4.3 5211 Code**

Weights:

`5   2   1   1`

* Weighted decimal code

* Less commonly used

* Useful in some arithmetic circuits

---

## **5\. Non-Weighted Decimal Codes**

---

### **5.1 Excess-3 (XS-3) Code**

#### **Rule:**

Add **3** to the decimal digit and convert to binary.

| Decimal | XS-3 |
| ----- | ----- |
| 0 | 0011 |
| 4 | 0111 |
| 9 | 1100 |

#### **Example**

Decimal: **27**

`2 + 3 = 5 → 0101`  
`7 + 3 = 10 → 1010`  
`XS-3 = 0101 1010`

#### **Advantages**

* Self-complementing

* Simplifies subtraction

#### **Disadvantages**

* Arithmetic is complex

* Not intuitive

---

### **5.2 Gray Code (Reflected Decimal Code)**

* Adjacent numbers differ by **only one bit**

* Not suitable for arithmetic

| Decimal | Gray Code |
| ----- | ----- |
| 3 | 0010 |
| 4 | 0110 |

Used in:

* Rotary encoders

* Position sensors

---

## **6\. Comparison of Decimal Codes**

| Code | Weighted | Self-Complementing | Usage |
| ----- | ----- | ----- | ----- |
| 8421 BCD | ✔ | ✘ | Displays, calculators |
| 2421 | ✔ | ✔ | Arithmetic circuits |
| XS-3 | ✘ | ✔ | Digital subtraction |
| Gray | ✘ | ✘ | Error reduction |

---

## **7\. Decimal Code Arithmetic**

### **BCD Addition Rule**

1. Add normally in binary

2. If sum \> 1001 or carry occurs → add **0110**

#### **Example**

 `0101 (5)`  
`+ 0100 (4)`  
`--------`  
  `1001 (9) → valid`

If invalid:

`Add 0110`

---

## **8\. Applications of Decimal Codes**

* Digital clocks

* Calculators

* Digital voltmeters

* Banking and financial systems

* Seven-segment displays

* Embedded systems

---

## **9\. Advantages of Decimal Codes**

✔ Human-friendly  
 ✔ Accurate decimal representation  
 ✔ Easy display interfacing

---

## **10\. Disadvantages of Decimal Codes**

❌ Uses more bits  
 ❌ Slower arithmetic  
 ❌ Complex correction logic

---

## **11\. Key Exam Points**

* Decimal codes represent digits **0–9 only**

* BCD uses **4 bits per digit**

* XS-3 and 2421 are **self-complementing**

* Invalid BCD codes range from **1010–1111**

* Gray code reduces transition errors

---

## **12\. Summary**

* Decimal codes convert decimal digits into binary form

* Used where **accuracy and display** are important

* Multiple types exist, each suited for specific tasks

* Most widely used decimal code is **8421 BCD**

# .

# **Binary to Gray Code Conversion** 

---

## **1\. What Is Gray Code?**

**Gray code** (also called **Reflected Binary Code**) is a **binary code in which two successive values differ by only one bit**.

### **Why Gray Code Is Used**

In normal binary, multiple bits can change at once, which can cause **errors** in digital systems (especially sensors and encoders).

Gray code **minimizes transition errors** by allowing **only one bit change** at a time.

---

## **2\. Difference Between Binary and Gray Code**

| Decimal | Binary | Gray |
| ----- | ----- | ----- |
| 3 | 0011 | 0010 |
| 4 | 0100 | 0110 |

Binary change from 3 → 4: **3 bits change**  
 Gray change from 3 → 4: **1 bit changes**

---

## **3\. Rule for Binary → Gray Conversion**

### **Golden Rule**

1. **MSB (Most Significant Bit) of Gray \= MSB of Binary**

2. Each next Gray bit is obtained by:

Gray bit=Current binary bit⊕Previous binary bit\\text{Gray bit} \= \\text{Current binary bit} \\oplus \\text{Previous binary bit}Gray bit=Current binary bit⊕Previous binary bit

Where **⊕ (XOR)** means:

* Same bits → 0

* Different bits → 1

---

## **4\. XOR Truth Table**

| Binary A | Binary B | A ⊕ B |
| ----- | ----- | ----- |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

---

## **5\. Step-by-Step Conversion Method**

### **Step 1:**

Write the **binary number**

### **Step 2:**

Copy the **MSB** directly to Gray code

### **Step 3:**

XOR each pair of adjacent binary bits

---

## **6\. Example 1 (4-bit Conversion)**

### **Binary Number:**

`1011`

### **Step-by-Step Table**

| Binary | 1 | 0 | 1 | 1 |
| ----- | ----- | ----- | ----- | ----- |
| Gray | 1 | 1 | 1 | 0 |

### **Explanation:**

* Gray MSB \= Binary MSB \= **1**

* 1 ⊕ 0 \= **1**

* 0 ⊕ 1 \= **1**

* 1 ⊕ 1 \= **0**

### **Final Gray Code:**

`1110`

---

## **7\. Example 2 (5-bit Conversion)**

### **Binary:**

`11001`

| Binary | 1 | 1 | 0 | 0 | 1 |
| ----- | ----- | ----- | ----- | ----- | ----- |
| Gray | 1 | 0 | 1 | 0 | 1 |

Explanation:

* MSB → 1

* 1 ⊕ 1 \= 0

* 1 ⊕ 0 \= 1

* 0 ⊕ 0 \= 0

* 0 ⊕ 1 \= 1

### **Gray Code:**

`10101`

---

## **8\. Table Conversion Example (0–7)**

| Decimal | Binary | Gray |
| ----- | ----- | ----- |
| 0 | 000 | 000 |
| 1 | 001 | 001 |
| 2 | 010 | 011 |
| 3 | 011 | 010 |
| 4 | 100 | 110 |
| 5 | 101 | 111 |
| 6 | 110 | 101 |
| 7 | 111 | 100 |

---

## **9\. Why Only One Bit Changes in Gray Code**

Gray code is designed so that:

* Consecutive values differ in **exactly one bit**

* This avoids **ambiguity and glitches**

* Especially important in **rotary encoders and ADCs**

---

## **10\. Hardware Implementation (Concept)**

Binary → Gray conversion can be implemented using:

* **XOR gates**

* One XOR gate per bit (except MSB)

Example:

`G2 = B3 ⊕ B2`  
`G1 = B2 ⊕ B1`

---

## **11\. Advantages of Gray Code**

✔ Reduces errors  
 ✔ Single-bit transitions  
 ✔ Simple hardware  
 ✔ Used in encoders and communication systems

---

## **12\. Limitations**

❌ Not suitable for arithmetic  
 ❌ Needs conversion back to binary for calculations

---

## **13\. Common Exam Mistakes**

❌ XOR Gray bits with Gray bits (wrong)  
 ❌ Forgetting to copy MSB directly  
 ❌ Treating Gray code like weighted code

---

## **14\. Summary**

* Gray code changes only **one bit at a time**

* MSB remains the same

* Other bits are generated using **XOR**

* Used mainly for **error reduction**

* Not meant for arithmetic operations

# 2

# **Gray Code to Binary Code Conversion** 

---

## **1\. What Is Gray Code? (Quick Reminder)**

Gray code is a binary code in which **only one bit changes at a time** when numbers increase.

Example:

| Decimal | Binary | Gray |
| ----- | ----- | ----- |
| 2 | 010 | 011 |
| 3 | 011 | 010 |

This property reduces errors in **sensors, encoders, and ADCs**.

---

## **2\. Why Do We Convert Gray Code to Binary?**

Gray code:

* Is **safe for transmission**

* Reduces switching errors

* **Cannot be used for arithmetic**

Binary code:

* Is used by computers

* Supports arithmetic and logic operations

👉 Therefore, Gray code must be converted to **binary** before processing.

---

## **3\. Key Idea Behind the Conversion**

Gray code does **not store the actual value** of a number.  
 Instead, it stores **information about change** between bits.

Binary code stores the **actual value**.

So, to get the binary number:

* Start from the left (MSB)

* Rebuild the binary bits one by one using the Gray bits

---

## **4\. Step-by-Step Method (Simple Explanation)**

### **Step 1: Copy the MSB**

The **first (leftmost) bit** of the binary number is the **same as the first Gray bit**.

---

### **Step 2: Move Left to Right**

For each next position:

* Look at the **previous binary bit**

* Look at the **current Gray bit**

If the Gray bit is:

* **0** → binary bit stays the **same**

* **1** → binary bit **changes (flips)**

This continues until the last bit.

---

## **5\. Example 1 (Easy Example)**

### **Given Gray Code:**

`1011`

### **Conversion:**

| Gray Bit | Explanation | Binary Bit |
| ----- | ----- | ----- |
| 1 | MSB copied | 1 |
| 0 | No change | 1 |
| 1 | Change | 0 |
| 1 | Change | 1 |

### **Final Binary:**

`1101`

---

## **6\. Example 2 (Another Example)**

### **Gray Code:**

`0110`

| Gray Bit | Binary Bit |
| ----- | ----- |
| 0 | 0 |
| 1 | 1 |
| 1 | 0 |
| 0 | 0 |

### **Final Binary:**

`0100`

---

## **7\. Why This Method Works**

* Gray bits indicate **whether a change occurred**

* Binary bits show the **result after applying all changes**

* Each bit depends on the **previous binary bit**

That’s why the process is **sequential**.

---

## **8\. Simple Way to Remember**

**Gray \= change information**  
 **Binary \= actual value**

---

## **9\. Common Mistakes to Avoid**

❌ Converting each Gray bit independently  
 ❌ Forgetting to copy the MSB  
 ❌ Treating Gray code like weighted binary  
 ❌ Trying arithmetic directly on Gray code

---

## **10\. Short Exam Answer**

Gray code to binary conversion is done by copying the most significant bit directly. Each following binary bit is obtained by checking the corresponding Gray bit: if it is 0, the binary bit remains the same; if it is 1, the binary bit is inverted from the previous binary bit.

---

## **11\. Summary**

* Gray code reduces errors

* Binary code allows computation

* Conversion starts from MSB

* Each bit depends on the previous one

* Used in digital systems and encoders

