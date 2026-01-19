# **Binary Codes** 

---

## **1\. What Are Binary Codes?**

A **binary code** is a system of representing **numbers, letters, symbols, or instructions** using **binary digits (bits)** — **0 and 1**.

### **Why Binary?**

Computers use binary because electronic circuits have only **two stable states**:

* ON / OFF

* High / Low voltage

* True / False

So everything inside a computer is ultimately represented using **binary codes**.

---

## **2\. Bit, Nibble, and Byte**

| Term | Meaning |
| ----- | ----- |
| Bit | One binary digit (0 or 1\) |
| Nibble | 4 bits |
| Byte | 8 bits |
| Word | Group of bytes (depends on system) |

Example:

`1011 → 4 bits → 1 nibble`  
`10110110 → 8 bits → 1 byte`

---

## **3\. Classification of Binary Codes**

Binary codes are broadly classified into:

### **A. Numeric Binary Codes**

* Used to represent numbers

### **B. Alphanumeric Binary Codes**

* Used to represent letters, numbers, symbols

### **C. Error Detecting & Correcting Codes**

* Used to find and correct errors

### **D. Special-Purpose Codes**

* Used for specific digital applications

---

## **4\. Numeric Binary Codes**

---

### **4.1 Straight (Pure) Binary Code**

* Direct base-2 representation of decimal numbers

| Decimal | Binary |
| ----- | ----- |
| 0 | 0000 |
| 1 | 0001 |
| 5 | 0101 |
| 9 | 1001 |

**Advantages**

* Simple

* Used internally by computers

**Disadvantages**

* Not suitable for decimal displays

* Difficult decimal correction

---

### **4.2 BCD (Binary Coded Decimal)**

Each **decimal digit** is represented separately by **4 bits**.

| Decimal Digit | BCD |
| ----- | ----- |
| 0 | 0000 |
| 5 | 0101 |
| 9 | 1001 |

Example:

`Decimal: 47`  
`BCD:     0100 0111`

❌ Invalid BCD codes: 1010 – 1111

**Advantages**

* Easy decimal display

* Used in calculators

**Disadvantages**

* Wastes bits

* Arithmetic is slower

---

### **4.3 8421 BCD Code**

* Weighted code

* Weights: **8, 4, 2, 1**

Example:

`Digit 6 → 0110 (4+2)`

---

### **4.4 Excess-3 (XS-3) Code**

* Non-weighted code

* Add **3** to each decimal digit and convert to binary

Example:

`Digit: 5`  
`5 + 3 = 8 → 1000`

| Decimal | XS-3 |
| ----- | ----- |
| 0 | 0011 |
| 9 | 1100 |

**Advantages**

* Self-complementing

* Useful in digital arithmetic

---

### **4.5 Gray Code (Reflected Binary Code)**

* Adjacent numbers differ by **only one bit**

| Decimal | Binary | Gray |
| ----- | ----- | ----- |
| 3 | 0011 | 0010 |
| 4 | 0100 | 0110 |

**Advantages**

* Minimizes errors

* Used in shaft encoders

**Disadvantages**

* Not suitable for arithmetic

---

## **5\. Alphanumeric Binary Codes**

---

### **5.1 ASCII (American Standard Code for Information Interchange)**

* 7-bit code (8-bit extended)

* Represents letters, digits, symbols

| Character | ASCII (Binary) |
| ----- | ----- |
| A | 1000001 |
| a | 1100001 |
| 0 | 0110000 |

**Features**

* Widely used

* Case-sensitive

---

### **5.2 EBCDIC**

* 8-bit code

* Used mainly by IBM mainframes

---

### **5.3 Unicode**

* Universal character set

* Supports all world languages

* Common formats: UTF-8, UTF-16, UTF-32

**Example**

`A → 0041₁₆`

---

## **6\. Error Detecting and Correcting Codes**

---

### **6.1 Parity Code**

Adds **one bit** to detect errors.

* **Even parity**

* **Odd parity**

Example:

`Data: 1011001`  
`Even parity bit: 0`

Detects **single-bit errors only**

---

### **6.2 Hamming Code**

* Can **detect and correct single-bit errors**

* Uses parity bits at positions 2ⁿ

Example:

`Data bits: 4`  
`Parity bits: 3`  
`Total bits: 7`

Used in RAM, communication systems

---

### **6.3 CRC (Cyclic Redundancy Check)**

* Polynomial-based

* Very powerful error detection

* Used in networks (Ethernet, USB)

---

## **7\. Special-Purpose Binary Codes**

---

### **7.1 Self-Complementing Codes**

* 9’s complement obtained by bit inversion

* Example: Excess-3

---

### **7.2 Weighted Codes**

* Each bit has a fixed weight

* Example: 8421, 2421

---

### **7.3 Non-Weighted Codes**

* No fixed positional weights

* Example: Gray code

---

## **8\. Comparison of Important Codes**

| Code | Weighted | Self-Complementing | Error Reduction |
| ----- | ----- | ----- | ----- |
| Binary | ✔ | ✘ | ✘ |
| BCD | ✔ | ✘ | ✘ |
| Excess-3 | ✘ | ✔ | ✘ |
| Gray | ✘ | ✘ | ✔ |

---

## **9\. Applications of Binary Codes**

* Computers and microprocessors

* Digital displays

* Data storage

* Communication systems

* Error detection and correction

* Industrial automation

---

## **10\. Key Points for Exams**

* BCD represents **each decimal digit separately**

* Gray code changes **one bit at a time**

* Excess-3 is **self-complementing**

* ASCII is **7-bit**

* Hamming code corrects **single-bit errors**

---

## **11\. Summary**

* Binary codes are essential for digital systems

* Different codes exist for different purposes

* No single code is perfect for all applications

* Selection depends on **speed, accuracy, storage, and complexity**

