# **Instruction Classification in 8085 Microprocessor** 

---

## **1\. Introduction**

The **8085 microprocessor** has **74 instructions** with **246 opcodes**, which can be classified based on **functionality**.

**Definition:**

*Instruction classification is the process of grouping instructions according to their purpose, such as data transfer, arithmetic, logic, branch, or control operations.*

**Purpose:** Helps in understanding **how to write programs efficiently**.

---

## **2\. Types of Instructions**

8085 instructions can be broadly divided into **five major categories**:

1. **Data Transfer Instructions**

2. **Arithmetic Instructions**

3. **Logical Instructions**

4. **Branch / Program Control Instructions**

5. **Stack / Machine Control Instructions**

---

### **2.1 Data Transfer Instructions (MOV, MVI, LXI, LDA, STA, etc.)**

* **Purpose:** Transfer data between **registers, memory, and I/O devices**.

* **Characteristics:**

  * Do not affect flags (except for some special cases like XCHG)

  * Simple **copy operations**

**Common Instructions:**

| Instruction | Purpose | Example |
| ----- | ----- | ----- |
| MOV | Copy data from register to register | `MOV A, B` |
| MVI | Move immediate data to register/memory | `MVI A, 55H` |
| LXI | Load 16-bit immediate data into register pair | `LXI H, 2000H` |
| LDA | Load accumulator from memory | `LDA 2050H` |
| STA | Store accumulator to memory | `STA 3000H` |
| LHLD | Load H-L pair directly from memory | `LHLD 2050H` |
| SHLD | Store H-L pair directly to memory | `SHLD 3000H` |
| XCHG | Exchange D-E and H-L register pairs | `XCHG` |
| IN | Read data from input port | `IN 01H` |
| OUT | Send data to output port | `OUT 02H` |

**Example Use:** Copy data from memory to accumulator and then store in another location.

---

### **2.2 Arithmetic Instructions (ADD, SUB, INR, DCR, etc.)**

* **Purpose:** Perform **arithmetic operations** like addition, subtraction, increment, and decrement.

* **Flags Affected:** CY, Z, S, P, AC

**Common Instructions:**

| Instruction | Purpose | Example |
| ----- | ----- | ----- |
| ADD | Add register/memory to accumulator | `ADD B` |
| ADC | Add with carry | `ADC C` |
| SUB | Subtract register/memory from accumulator | `SUB D` |
| SBB | Subtract with borrow | `SBB E` |
| INR | Increment register/memory by 1 | `INR A` |
| DCR | Decrement register/memory by 1 | `DCR B` |
| INX | Increment register pair by 1 | `INX H` |
| DCX | Decrement register pair by 1 | `DCX D` |
| DAD | Add register pair to H-L pair | `DAD B` |

**Example Use:** Add two numbers stored in memory and store the result in accumulator.

---

### **2.3 Logical Instructions (ANA, ORA, XRA, CMA, etc.)**

* **Purpose:** Perform **bitwise and logical operations** on data in accumulator.

* **Flags Affected:** Z, S, P, CY (C is sometimes reset, not affected)

**Common Instructions:**

| Instruction | Purpose | Example |
| ----- | ----- | ----- |
| ANA | Logical AND accumulator with register/memory | `ANA B` |
| ORA | Logical OR accumulator with register/memory | `ORA C` |
| XRA | Logical XOR accumulator with register/memory | `XRA D` |
| CMA | Complement accumulator | `CMA` |
| RLC | Rotate accumulator left | `RLC` |
| RRC | Rotate accumulator right | `RRC` |
| RAL | Rotate accumulator left through carry | `RAL` |
| RAR | Rotate accumulator right through carry | `RAR` |
| CMP | Compare accumulator with register/memory | `CMP E` |
| CPI | Compare accumulator with immediate | `CPI 55H` |

**Example Use:** Perform bitwise AND on two numbers stored in registers.

---

### **2.4 Branch / Program Control Instructions (JMP, CALL, RET, etc.)**

* **Purpose:** Control the **flow of the program** – jump, call subroutine, return, or conditionally execute instructions.

* **Types:** Unconditional and Conditional

**Common Instructions:**

| Instruction | Purpose | Example |
| ----- | ----- | ----- |
| JMP | Unconditional jump | `JMP 2050H` |
| JC | Jump if carry set | `JC 3000H` |
| JZ | Jump if zero | `JZ 2050H` |
| JNC | Jump if carry not set | `JNC 2050H` |
| JNZ | Jump if not zero | `JNZ 2050H` |
| CALL | Call subroutine | `CALL 3000H` |
| RET | Return from subroutine | `RET` |
| RST | Restart (call fixed address) | `RST 7` |

**Example Use:** Execute a subroutine only if a certain condition (e.g., zero flag set) is met.

---

### **2.5 Stack / Machine Control Instructions (PUSH, POP, HLT, NOP, etc.)**

* **Purpose:** Control **CPU operations**, stack manipulation, or halt execution.

**Common Instructions:**

| Instruction | Purpose | Example |
| ----- | ----- | ----- |
| PUSH | Store register pair on stack | `PUSH B` |
| POP | Retrieve register pair from stack | `POP D` |
| XTHL | Exchange stack top with H-L pair | `XTHL` |
| SPHL | Load stack pointer from H-L | `SPHL` |
| NOP | No operation | `NOP` |
| HLT | Halt CPU | `HLT` |
| DI | Disable interrupts | `DI` |
| EI | Enable interrupts | `EI` |

**Example Use:** Save registers on stack before subroutine and restore after.

---

## **3\. Summary Table of 8085 Instruction Classification**

| Category | Purpose | Examples | Flags Affected |
| ----- | ----- | ----- | ----- |
| Data Transfer | Move data between registers, memory, I/O | MOV, MVI, LXI, LDA, STA, IN, OUT | None (usually) |
| Arithmetic | Add, subtract, increment, decrement | ADD, SUB, INR, DCR, INX, DCX, DAD | Z, S, P, CY, AC |
| Logical | AND, OR, XOR, complement, compare, rotate | ANA, ORA, XRA, CMA, CMP, RLC, RRC | Z, S, P, CY |
| Branch / Program Control | Jump, call, return | JMP, JC, JZ, CALL, RET, RST | None directly (affects PC) |
| Stack / Machine Control | Push/pop stack, enable/disable interrupts, halt | PUSH, POP, NOP, HLT, DI, EI | None directly |

---

## **4\. Importance of Instruction Classification**

* Helps **programmers select the right instruction** for specific tasks.

* **Optimizes memory and CPU usage**.

* Essential for **writing structured and efficient 8085 programs**.

* Helps in **understanding flags and program flow control**.