**PROGRAM-  15**  
**8085 program to implement 2 out of 5 codes**  
---

**Code:**  

``` asm
LDA 8000H  
ANI 01FH  
MVI C,05H  
MVI D,00H  
LOOP:  RAR  
JNC SKIP  
INR D  
SKIP:  DCR C  
JNZ LOOP  
MVI A,02H  
CMP D  
JZ TRUE  
MVI A,0FFH  
JMP EXIT  
TRUE:  MVI A,0DDH  
EXIT:  STA 8001H  
HLT  
```

---

**Input:**

| Address | Data |
| :---- | :---- |
| **8000H** | **20** |
| **8001H** | **0** |

![Input](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769534832/fifteenprogipp_vmjscf.png)

---

**Output:**

| Address | Data |
| :---- | :---- |
| **8000H** | **20** |
| **8001H** | **221** |

![Output](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769534830/fifteenprogop_mivvge.png)

---

## **🔹Example:** 

* ## **Load value from 8000H (20 decimal → `00010100B`) into A.** 

* ## **Mask lower 5 bits (`ANI 01FH`) → A = `00010100B`.** 

* ## **Loop 5 times: rotate right through carry, count number of 1’s in D.** 

* ## **After loop, D = 2 → exactly 2 bits set.** 

* ## **If D = 2 → store 0DDH at 8001H, else 0FFH.** 

* ## **HLT stops execution.** 

## **Result: 8001H = 0DDH (221 decimal).**

---

## **🔹Step-by-Step Logic**

### **Step 1: LDA 8000H**

* **Load accumulator A with the 8-bit value stored at memory 8000H.**

* **Example: let’s say memory 8000H = ABH (we’ll keep it general for now).**

---

### **Step 2: ANI 01FH**

* **Logical AND accumulator with 00011111B (01FH).**

* **This keeps only the lower 5 bits of A (bits 0–4).**

* **Upper 3 bits become 0\.**

**Effect: isolates the lower 5 bits of the value.**

---

### **Step 3: MVI C,05H & MVI D,00H**

* **C = 5 → loop counter for 5 iterations.**

* **D = 0 → will count how many 1’s are rotated out (set bits).**

---

### **Step 4: LOOP Start**

**`RAR`**

* **Rotate accumulator right through carry.**

* **Bit 0 of A goes into Carry flag, previous Carry goes into bit 7\.**

**`JNC SKIP`**

* **If Carry = 0, skip next step.**

* **If Carry = 1, increment D (counts number of set bits rotated out).**

**`INR D`**

* **Increment D if Carry was 1 (bit 0 of A = 1 before rotate).**

**`SKIP: DCR C`**  
**`JNZ LOOP`**

* **Decrement loop counter C.**

* **Repeat loop 5 times (for 5 bits).**

**Effect: counts number of 1’s in lower 5 bits of original A.**

* **D now holds number of 1’s in bits 0–4.**

---

### **Step 5: Compare result**

**`MVI A,02H`**  
**`CMP D`**

* **Load A = 02H (decimal 2).**

* **Compare A with D.**

**`JZ TRUE`**

* **If D = 2 → jump to TRUE.**

* **Else → next instruction.**

**`MVI A,0FFH`**

* **If D ≠ 2 → A = FFH (indicates “false”).**

**`JMP EXIT`**

* **Skip TRUE section.**

**`TRUE: MVI A,0DDH`**

* **If D = 2 → A = DDH (indicates “true”).**

---

### **Step 6: Store Result**

**`EXIT: STA 8001H`**

* **Store the final A value (FFH or DDH) at memory 8001H.**

---

### **Step 7: HLT**

* **Stop execution.**

---

## **🔹Core Logic (One Line)**

**Counts the number of 1’s in the lower 5 bits of a memory value;**  
 **if exactly 2 bits are set → store DDH, else FFH in memory.**

---

## **🔹Registers Used**

* **A → accumulator for rotation, masking, and comparison**

* **C → loop counter (5 iterations)**

* **D → counts number of 1’s (set bits)**

---

## **🔹Mnemonics Used**

| Mnemonic | Function |
| ----- | ----- |
| **LDA** | **Load accumulator from memory** |
| **ANI** | **AND accumulator with immediate** |
| **MVI** | **Move immediate data to register** |
| **RAR** | **Rotate accumulator right through carry** |
| **JNC** | **Jump if carry = 0** |
| **INR** | **Increment register** |
| **DCR** | **Decrement register** |
| **JNZ** | **Jump if not zero** |
| **CMP** | **Compare accumulator with register** |
| **JZ** | **Jump if zero** |
| **JMP** | **Unconditional jump** |
| **STA** | **Store accumulator to memory** |
| **HLT** | **Halt execution** |

