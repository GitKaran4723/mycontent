**PROGRAM-  19**  
**8085 program to find Multiplication of 2-digit BCD numbers**  
---

**Code:**  

``` asm
LXI  H,8000H  
MOV C,M  
INX H  
MOV D,M  
XRA A  
MOV B,A  
LOOP:   ADD C  
DAA  
JNC NEXT  
INR B  
NEXT:  DCR D  
JNZ LOOP  
STA 8002H  
MOV A,B  
STA 8003H  
HLT
```
  
---

**Input:**

| Address | Data |
| :---- | :---- |
| **8000H** | **07** |
| **8001H** | **05** |
| **8002H** | **0** |

![Input](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769616826/nineteenprogip_oqzxbk.png)

---

**Output:**

| Address | Data |
| :---- | :---- |
| **8000H** | **07    ( 07H )** |
| **8001H** | **05   ( 05H )** |
| **8002H** | **53   ( 35H )** |

![Output](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769616826/nineteenprogop_rulmin.png)

---

## **🔹Example:**

* **Inputs:**

**`8000H = 07  (multiplicand)`**    
**`8001H = 05  (multiplier)`**

* **Operation: 7 × 5 using repeated BCD addition**

* **Result in accumulator: 35H (BCD)**

* **Stored in memory:**

**`8002H = 35H`**

* **Simulator displays 53 because it converts 35H to decimal (3×16 \+ 5 \= 53\)**

## **🔹Step-by-Step Logic** 

---

### **1\. Point to first number**

**`LXI H,8000H`**

* **HL pair points to memory location 8000H**

---

### **2\. Load first BCD number (multiplicand)**

**`MOV C,M`**

* **Contents of 8000H → Register C**

* **`C` holds the number to be added repeatedly**

---

### **3\. Point to second number**

**`INX H`**

* **HL → 8001H**

---

### **4\. Load second BCD number (multiplier)**

**`MOV D,M`**

* **Contents of 8001H → Register D**

* **`D` acts as loop counter**

---

### **5\. Clear accumulator**

**`XRA A`**

* **A \= 00H**

* **Accumulator will hold lower BCD result**

---

### **6\. Clear higher BCD result**

**`MOV B,A`**

* **B \= 00H**

* **`B` will store carry / higher BCD digit**

---

## **7\. Start Multiplication Loop**

**`LOOP: ADD C`**

* **A \= A \+ C**

* **Adds the multiplicand once**

---

### **8\. Decimal Adjust**

**`DAA`**

* **Adjusts accumulator to valid BCD**

* **Required after every BCD addition**

---

### **9\. Check for carry**

**`JNC NEXT`**

* **If no carry, jump to NEXT**

* **If carry occurs, continue**

---

### **10\. Increment higher BCD digit**

**`INR B`**

* **Carry means result exceeded 9**

* **Increment higher BCD digit stored in `B`**

---

### **11\. Decrement multiplier**

**`NEXT: DCR D`**

* **One addition completed**

* **Decrease loop counter**

---

### **12\. Repeat until multiplier becomes zero**

**`JNZ LOOP`**

* **If D ≠ 0, repeat addition**

* **If D \= 0, multiplication is complete**

---

## **13\. Store lower BCD result**

**`STA 8002H`**

* **Store accumulator (LSB of product) in memory**

---

## **14\. Store higher BCD result**

**`MOV A,B`**  
**`STA 8003H`**

* **Move higher BCD digit to accumulator**

* **Store it at 8003H**

---

### **15\. Stop program**

**`HLT`**

---

## **🔹Core Logic (one line)**

**Multiply two BCD numbers using repeated addition with DAA, storing the result as a two-digit BCD.**

---

## **🔹Registers Used** 

* **A → Accumulator, holds lower BCD result**

* **B → Holds carry / higher BCD digit**

* **C → Multiplicand (first number)**

* **D → Multiplier (loop counter)**

* **H-L → Memory pointer to input numbers**

---

## **🔹Mnemonics Used** 

| Mnemonic | Purpose |
| ----- | ----- |
| **LXI H,addr** | **Load HL pair with memory address** |
| **MOV C,M** | **Load multiplicand from memory to C** |
| **INX H** | **Point HL to next memory location** |
| **MOV D,M** | **Load multiplier from memory to D** |
| **XRA A** | **Clear accumulator** |
| **MOV B,A** | **Clear higher BCD digit** |
| **ADD C** | **Add multiplicand to accumulator** |
| **DAA** | **Decimal adjust accumulator (BCD correction)** |
| **JNC label** | **Skip increment if no carry** |
| **INR B** | **Increment higher BCD digit if carry occurs** |
| **DCR D** | **Decrement multiplier (loop counter)** |
| **JNZ label** | **Repeat loop until multiplier \= 0** |
| **STA addr** | **Store accumulator in memory** |
| **MOV A,B** | **Move higher BCD digit to accumulator** |
| **HLT** | **Stop program** |

