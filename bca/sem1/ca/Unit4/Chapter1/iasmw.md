# **Writing, Assembling, and Executing a Simple Program in 8085 Microprocessor**

---

## **1\. Introduction**

The **8085 microprocessor** executes instructions stored in memory. Writing a program involves:

1. **Writing the assembly code** – instructions in human-readable form.

2. **Assembling the code** – converting assembly code to machine code (hexadecimal opcodes).

3. **Loading into memory** – transferring machine code into microprocessor memory.

4. **Executing the program** – running instructions sequentially by the CPU.

**Example Task:** Add two numbers stored in memory and store the result in another memory location.

---

## **2\. Steps to Write an 8085 Program**

### **Step 1: Understand the Problem**

* Suppose we want to **add two numbers stored at memory locations 2050H and 2051H** and store the result at **2052H**.

**Given:**

* First number at 2050H = 05H

* Second number at 2051H = 0AH

**Goal:** Store sum in 2052H.

---

### **Step 2: Identify Instructions Needed**

* **Load the first number into accumulator:** `LDA 2050H`

* **Add the second number to accumulator:** `ADD` (via memory reference)

* **Store result in memory:** `STA 2052H`

* **End program:** `HLT`

---

### **Step 3: Write the Assembly Code**

**Assembly Code:**

`MVI A, 00H      ; Clear accumulator (optional)`  
`LDA 2050H       ; Load first number into accumulator`  
`ADD M           ; Add number at 2051H (if M points to 2051H using H-L)`  
`STA 2052H       ; Store result at memory location 2052H`  
`HLT             ; Stop execution`

**Explanation of Instructions:**

| Instruction | Purpose |
| ----- | ----- |
| MVI A, 00H | Initialize accumulator to 0 |
| LDA 2050H | Load number from memory 2050H into accumulator |
| ADD M | Add content of memory location pointed by H-L to accumulator |
| STA 2052H | Store result into memory 2052H |
| HLT | Halt the processor |

---

### **Step 4: Assign Memory Addresses**

* Program is stored in consecutive memory addresses starting, for example, **2000H**:

| Memory Address | Instruction / Data |
| ----- | ----- |
| 2000H | MVI A, 00H |
| 2002H | LDA 2050H |
| 2005H | ADD M |
| 2006H | STA 2052H |
| 2009H | HLT |
| 2050H | 05H (First number) |
| 2051H | 0AH (Second number) |
| 2052H | ? (Result) |

Note: `ADD M` requires **H-L pair** to point to the memory location (here, set HL = 2051H). Alternatively, you can use `ADD` with memory address directly if using `ADD M` after `LDA` and setting H-L.

---

## **3\. Assembling the Program**

* **Assembly:** Convert instructions into **machine code (hex opcodes)**.

* Example machine code for above program:

| Instruction | Opcode (Hex) |
| ----- | ----- |
| MVI A, 00H | 3E 00 |
| LDA 2050H | 3A 50 20 |
| ADD M | 86 |
| STA 2052H | 32 52 20 |
| HLT | 76 |

**Explanation:**

* `3E 00` → MVI A,00H

* `3A 50 20` → LDA 2050H (Little-endian: low byte first)

* `86` → ADD M (Add memory pointed by H-L pair to accumulator)

* `32 52 20` → STA 2052H

* `76` → HLT

Little-endian means **low-order byte of address is stored first**, then high-order byte.

---

## **4\. Loading the Program into Memory**

**Steps:**

1. Connect **8085 trainer kit or simulator**.

2. Select **memory start address** (e.g., 2000H).

3. Enter **machine code (hex opcodes)** sequentially.

4. Enter data at memory addresses 2050H and 2051H.

---

## **5\. Executing the Program**

**Steps:**

1. Set **Program Counter (PC) to start address** (2000H).

2. Use **Step/Run mode** on trainer kit or simulator:

   * **Step mode:** Execute instructions one by one, observe accumulator, memory, and flags.

   * **Run mode:** Execute entire program continuously.

3. After HLT, check **memory location 2052H** for result.

**Expected Result:**

* 05H \+ 0AH = 0FH → stored at **2052H**

---

## **6\. Flow of Program Execution**

1. **PC = 2000H**, fetch `MVI A, 00H` → Accumulator = 00H

2. **PC = 2002H**, fetch `LDA 2050H` → Accumulator = 05H

3. **PC = 2005H**, fetch `ADD M` → Accumulator = 05H \+ 0AH = 0FH

4. **PC = 2006H**, fetch `STA 2052H` → Memory 2052H = 0FH

5. **PC = 2009H**, fetch `HLT` → CPU stops

---

## **7\. Important Notes**

* Always **initialize accumulator or registers** if needed.

* Keep track of **H-L register pair** if using memory reference instructions like `ADD M`.

* **Flags** will be updated automatically after arithmetic/logical instructions.

* **Use little-endian format** for memory addresses in machine code.

---

### **8\. Summary Steps**

| Step | Description |
| ----- | ----- |
| 1 | Analyze the problem and identify operations |
| 2 | Write assembly code using 8085 instructions |
| 3 | Assign memory addresses for instructions and data |
| 4 | Assemble the code → convert to machine code (hex) |
| 5 | Load program and data into memory |
| 6 | Set program counter to start address |
| 7 | Execute program using step/run mode |
| 8 | Verify result in memory or registers |

---

### **9\. Exam-Ready Example**

**Task:** Add two numbers and store result

**Assembly Code:**

`MVI A,00H`  
`LDA 2050H`  
`ADD M`  
`STA 2052H`  
`HLT`

**Machine Code:**

`3E 00`  
`3A 50 20`  
`86`  
`32 52 20`  
`76`

**Memory Layout:**

`2000H: 3E 00`  
`2002H: 3A 50 20`  
`2005H: 86`  
`2006H: 32 52 20`  
`2009H: 76`  
`2050H: 05`  
`2051H: 0A`  
`2052H: 0F (Result)`

