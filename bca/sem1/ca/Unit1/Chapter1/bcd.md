# **BCD (Binary Coded Decimal) Arithmetic**

---

## **1\. What is BCD? (Definition)**

**BCD (Binary Coded Decimal)** is a number system in which **each decimal digit (0–9)** is represented **individually** by its **4-bit binary equivalent**.

### **Valid BCD Codes**

| Decimal | BCD |
| ----- | ----- |
| 0 | 0000 |
| 1 | 0001 |
| 2 | 0010 |
| 3 | 0011 |
| 4 | 0100 |
| 5 | 0101 |
| 6 | 0110 |
| 7 | 0111 |
| 8 | 1000 |
| 9 | 1001 |

🚫 **Invalid BCD codes**:  
 `1010` to `1111` (decimal 10–15)

---

## **2\. Why BCD Arithmetic is Needed**

* Computers use **binary**

* Humans use **decimal**

* BCD allows **easy decimal display and accuracy**

* Used in **financial, calculator, and display systems**

---

# **3\. BCD Addition**

---

## **Rules for BCD Addition (Very Important)**

1. Add BCD digits using **binary addition**

2. Check the result:

   * If **sum ≤ 1001 (9)** and **no carry**, result is valid

   * If **sum \> 1001** **OR** **carry = 1**, result is **invalid**

3. If invalid → **add 0110 (6)** to correct

4. Propagate carry to the next BCD digit

---

## **Why Add 0110?**

* Binary maximum for BCD = `1001` (9)

* Binary `1010–1111` are invalid

* Adding **6 (0110)** shifts result into valid BCD range and produces correct carry

---

## **Example 1: Simple BCD Addition (No Correction Needed)**

### **Example**

`25 + 14`

### **Step 1: Convert to BCD**

`2 → 0010`  
`5 → 0101`

`1 → 0001`  
`4 → 0100`

### **Step 2: Add**

 `0010 0101`  
`+ 0001 0100`  
`------------`  
  `0011 1001`

✔ Result is valid BCD

### **Answer**

`39`

---

## **Example 2: BCD Addition with Correction**

### **Example**

`28 + 35`

### **Step 1: BCD Conversion**

`2 → 0010   8 → 1000`  
`3 → 0011   5 → 0101`

### **Step 2: Binary Addition**

 `0010 1000`  
`+ 0011 0101`  
`------------`  
  `0101 1101`

🚫 `1101` is invalid (\>1001)

---

### **Step 3: Add Correction Factor (0110)**

 `1101`  
`+ 0110`  
`-------`  
`1 0011`

Carry = 1 → added to next digit

---

### **Final Result**

`0101 + 0001 = 0110`

### **Answer**

`63`

✔ Correct (28 \+ 35 = 63\)

---

# **4\. BCD Subtraction**

BCD subtraction is performed using **10’s complement method**.

---

## **Rules for BCD Subtraction**

1. Find **9’s complement** of each BCD digit of subtrahend

2. Add **1** → get **10’s complement**

3. Add to minuend using **BCD addition rules**

4. If carry occurs → discard carry (positive result)

5. If no carry → take 10’s complement of result and prefix **negative sign**

---

## **Example 3: BCD Subtraction (Positive Result)**

### **Example**

`45 − 27`

### **Step 1: BCD Representation**

`45 → 0100 0101`  
`27 → 0010 0111`

---

### **Step 2: 9’s Complement of Subtrahend**

`2 → 7 → 0111`  
`7 → 2 → 0010`

### **Step 3: Add 1 → 10’s Complement**

`0111 0010 + 1 = 0111 0011`

---

### **Step 4: Add to Minuend**

 `0100 0101`  
`+ 0111 0011`  
`------------`  
  `1011 1000`

🚫 Invalid BCD → add 0110

---

### **Step 5: BCD Correction**

`1000 + 0110 = 1 1110`

---

### **Step 6: Discard Carry**

`0001 1000`

### **Answer**

`18`

✔ Correct (45 − 27 = 18\)

---

## **Example 4: BCD Subtraction (Negative Result)**

### **Example**

`32 − 58`

### **Step 1: Convert to BCD**

`32 → 0011 0010`  
`58 → 0101 1000`

---

### **Step 2: 10’s Complement of 58**

9’s complement:

`5 → 4`  
`8 → 1`

\+1 → `0100 0010`

---

### **Step 3: Add**

 `0011 0010`  
`+ 0100 0010`  
`------------`  
  `0111 0100`

🚫 No carry → negative result

---

### **Step 4: Take 10’s Complement**

`74 → 26`

### **Final Answer**

`−26`

✔ Correct (32 − 58 = −26)

---

# **5\. Comparison: BCD vs Binary Arithmetic**

| Feature | BCD | Binary |
| ----- | ----- | ----- |
| Digits | Decimal digits | Bits |
| Speed | Slower | Faster |
| Correction needed | Yes | No |
| Accuracy | High | High |
| Usage | Financial systems | CPUs |

---

# **6\. Exam-Ready Key Points**

✔ BCD uses **4 bits per decimal digit**  
 ✔ Valid codes: `0000–1001`  
 ✔ Correction factor = **0110**  
 ✔ Subtraction uses **10’s complement**  
 ✔ Widely used in calculators and banking systems

