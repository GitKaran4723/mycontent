**PROGRAM- 3**  
**8085 Program to find whether an 8-bit number is positive, negative or zero. If**   
**positive display EE, if negative display FF, if zero display DD**

LDA 8000H
CPI 00H
JZ ZERO
JM NEGATIVE
MVI A,0EEH
JMP STORE

NEGATIVE:  MVI A,0FFH
JMP STORE

ZERO:      MVI A,0DDH

STORE:     STA 8001H
HLT


**Input:**

| Address | Data |
| :---- | :---- |
| **8000H** | **78** |
| **8001H** | **0** |

**Output:**

| Address | Data |
| :---- | :---- |
| **8000H** | **78** |
| **8001H** | **238** |

**Possible Outputs(Depending on Inputs):**

| Input  | Output |
| :---- | :---- |
| **0  (ZERO)** | **221 (DDH)** |
| **78  (POSITIVE)** | **238 (EEH)** |
| **128  (NEGATIVE)** | **255  (FFH)** |

## **🔴 Important Tip About Negative Numbers (8085)**

**In the 8085 microprocessor, numbers are treated as signed 8-bit numbers using 2’s complement representation.**

### **🔢 Range of 8-bit signed numbers**

* **Positive numbers: `00H` to `7FH` (0 to \+127)**

* **Negative numbers: `80H` to `FFH` (−128 to −1)**

**👉 Negative numbers start from decimal 128, because:**

* **`80H` = `1000 0000` (MSB = 1\)**

* **MSB = 1 → Sign Flag = 1**

* **Hence, the processor treats it as a negative number**

## **🔍 Step-by-Step Logic**

### **1\. `LDA 8000H`**

* **Loads the contents of memory location 8000H into the Accumulator (A).**

* **Example:**

  * **If 8000H = `00H`, A = `00H`**

  * **If 8000H = `F5H`, A = `F5H` (negative number in signed form)**

---

### **2\. `CPI 00H`**

* **Compares the value in A with `00H`.**

* **Internally, the processor does:**  
   **A − 00H**

* **Flags are updated (Zero flag, Sign flag, etc.)**

* **Accumulator value does NOT change**

---

### **3\. `JZ ZERO`**

* **Jump if Zero flag = 1**

* **This happens when:**

  * **A = `00H`**

* **If true → program jumps to label ZERO**

---

### **4\. `JM NEGATIVE`**

* **Jump if Sign flag = 1**

* **Sign flag = 1 means:**

  * **The value in A is negative (MSB = 1, i.e., bit 7 = 1\)**

* **If true → program jumps to NEGATIVE**

---

### **5\. `MVI A, 0EEH` (Positive case)**

* **This executes only if the number is positive**

* **Loads `0EEH` into accumulator A**

---

### **6\. `JMP STORE`**

* **Unconditional jump to STORE**

* **Skips the NEGATIVE and ZERO sections**

---

## **🔁 NEGATIVE Section**

**`NEGATIVE: MVI A,0FFH`**  
**`JMP STORE`**

* **Executes if the number is negative**

* **Loads `0FFH` into accumulator**

* **Jumps to STORE**

---

## **🔁 ZERO Section**

**`ZERO: MVI A,0DDH`**

* **Executes if the number is zero**

* **Loads `0DDH` into accumulator**

* **Falls through to STORE (no jump needed)**

---

### **7\. `STORE: STA 8001H`**

* **Stores the value from accumulator A into memory location 8001H**

---

### **8\. `HLT`**

* **Halts the program**

---

## **🔹 Core Logic (One Line)**

**The program checks whether the number stored at 8000H is zero, positive (01H–7FH), or negative (80H–FFH) and stores a corresponding code at 8001H.**

---

## **🔹 Registers Used**

* **Accumulator (A)**

  * **Used to load the data from memory**

  * **Used for comparison and for storing the result before writing to memory**

---

## **🔹 Mnemonics Used in the Program**

| Mnemonic | Meaning / Purpose |
| ----- | ----- |
| **`LDA`** | **Load accumulator with data from memory** |
| **`CPI`** | **Compare immediate data with accumulator** |
| **`JZ`** | **Jump if Zero flag is set** |
| **`JM`** | **Jump if Sign flag is set (negative number ≥ 80H)** |
| **`MVI`** | **Move immediate data into register** |
| **`JMP`** | **Unconditional jump** |
| **`STA`** | **Store accumulator contents to memory** |
| **`HLT`** | **Halt the program** |

