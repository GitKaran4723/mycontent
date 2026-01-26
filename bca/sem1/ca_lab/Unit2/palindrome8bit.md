**PROGRAM- 8**  
 **8085 Program to check whether 1-byte number is a palindrome or not. If it is a palindrome display FF otherwise display DD.**  
---

Code:  

``` asm
LDA 8000H  
MOV H,A  
MVI C,08H  
MVI D,00H  
LOOP:  MOV A,H  
RLC  
MOV H,A  
MOV A,D  
RAR  
MOV D,A  
DCR C  
JNZ LOOP  
MOV A,H  
CMP D  
JZ TRUE  
MVI A,0DDH  
JMP EXIT  
TRUE:  MVI A,0FFH  
EXIT:  STA 8001H  
HLT   
```

---

**Input:**

| Address | Data |
| :---- | :---- |
| **8000H** | **129** |
| **8001H** | **0** |

![Input](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769449877/eightprogip_yurryq.png)

---

**Output:**

| Address | Data |
| :---- | :---- |
| **8000H** | **129** |
| **8001H** | **255** |

![Output](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769449877/eightprogop_qmxd8q.png)

---

### **🔹Example:**

### **Input = 129 (decimal) → 81H (hex)**

### **Memory Before Execution:**

### **`8000H → 129 (decimal) / 81H (hex)`**

### 

### **Program Execution:**

* ### **Checks if 129 is a bitwise palindrome → it is.** 

* ### **Sets A = 0FFH (TRUE).** 

* ### **Stores in memory 8001H.** 

### **Memory After Execution:**

| Address | Value (Hex) | Value (Decimal) |
| ----- | ----- | ----- |
| **8000H** | **81H** | **129** |
| **8001H** | **FFH** | **255** |

### ---

### **✅ Output at 8001H:**

* ### **Hex: FFH** 

* ### **Decimal: 255**

### **🔍 Step-by-Step Logic**

---

### **Step 1: LDA 8000H**

* **Instruction: `LDA 8000H`**

* **Effect: Load the value stored at memory location `8000H` into accumulator A.**

**Purpose: Get the input data from memory.**

---

### **Step 2: MOV H,A**

* **Instruction: `MOV H,A`**

* **Effect: Copy the value of accumulator A into register H.**

**Purpose: H will be used to hold the "rotating" value.**

---

### **Step 3: MVI C,08H**

* **Instruction: `MVI C,08H`**

* **Effect: Load `C` with 8, which will act as a loop counter.**

**Purpose: Perform 8 rotations (one for each bit in a byte).**

---

### **Step 4: MVI D,00H**

* **Instruction: `MVI D,00H`**

* **Effect: Initialize register D to 0\.**

**Purpose: D will accumulate the bits that get rotated out of H (through RAR).**

---

### **Step 5: LOOP start**

**`LOOP:  MOV A,H`**  
       **`RLC`**  
       **`MOV H,A`**  
       **`MOV A,D`**  
       **`RAR`**  
       **`MOV D,A`**  
       **`DCR C`**  
       **`JNZ LOOP`**

**Let’s break this inner loop iteration by iteration:**

1. **`MOV A,H` → Load the current value of H into the accumulator.**

2. **`RLC` → Rotate accumulator left circular. This moves MSB of H to LSB of H.**

3. **`MOV H,A` → Store the rotated value back into H.**

    **⚡ Effect: H is rotated left by 1 bit.**

4. **`MOV A,D` → Load D into accumulator. D holds previously rotated-out bits.**

5. **`RAR` → Rotate accumulator right through carry. This shifts D right by 1, and the carry from previous RLC rotation goes into MSB of D.**

6. **`MOV D,A` → Store updated value back into D.**

    **⚡ Effect: D accumulates the bits that were rotated out from H in the left rotations.**

7. **`DCR C` → Decrement loop counter C.**

8. **`JNZ LOOP` → Repeat until 8 rotations are done.**

**✅ Overall effect of loop:**

* **H rotates left 8 times (full byte rotation).**

* **D collects the bits shifted out during each rotation.**

* **This is essentially performing bit reversal: H and D together reverse the order of bits.**

---

### **Step 6: Compare H and D**

**`MOV A,H`**  
**`CMP D`**  
**`JZ TRUE`**

* **Load H into A, compare with D.**

* **If H = D → jump to TRUE.**

**Purpose: Check if the original number (after bit manipulations) equals its “mirror” in D.**

---

### **Step 7: Set result if not equal**

**`MVI A,0DDH`**  
**`JMP EXIT`**

* **If H ≠ D → load `0DDH` into A.**

* **Jump to EXIT.**

---

### **Step 8: TRUE case**

**`TRUE:  MVI A,0FFH`**

* **If H = D → load `0FFH` into A.**

---

### **Step 9: Store result and halt**

**`EXIT:  STA 8001H`**  
**`HLT`**

* **Store the result (0FFH if TRUE, 0DDH if FALSE) in memory 8001H.**

* **Halt the program.**

---

**🔹Overall Logic (one line):**

* **Checks if the binary representation of a byte is a palindrome and stores `0xFF` if TRUE, `0xDD` if FALSE.**

---

**🔹Registers Used:**

* **A (Accumulator): Holds data for operations and comparisons**

* **H: Stores original/rotated value of input byte**

* **D: Stores the reversed bits of the input byte**

* **C: Loop counter for 8-bit rotations**

---

**🔹Mnemonics Used:**

| Mnemonic | Use |
| ----- | ----- |
| **LDA** | **Load accumulator from memory** |
| **MOV** | **Copy data between registers** |
| **MVI** | **Load immediate data into register** |
| **RLC** | **Rotate accumulator left circular** |
| **RAR** | **Rotate accumulator right through carry** |
| **DCR** | **Decrement register (loop counter)** |
| **JNZ** | **Jump if not zero (loop)** |
| **CMP** | **Compare accumulator with register** |
| **JZ** | **Jump if zero (conditional branch)** |
| **STA** | **Store accumulator into memory** |
| **JMP** | **Unconditional jump** |
| **HLT** | **Halt the program** |

