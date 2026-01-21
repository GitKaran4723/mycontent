# **Instruction Classification of 8085**

The **8085 microprocessor** executes instructions that are classified based on **two criteria**:

1. **Word length (number of bytes)**

2. **Function (type of operation performed)**

Understanding these classifications is essential for programming efficiently and understanding memory usage.

---

## **1\. Classification Based on Word Length**

8085 instructions can occupy **1, 2, or 3 bytes in memory** depending on whether they use **immediate data or memory addresses**.

### **1.1 One-Byte Instructions**

* **Content:** Only the **opcode**; operand may be implied.

* **Memory:** 1 byte

* **Purpose:** Used for **register operations, accumulator operations, or control instructions**.

* **Examples:**  
   | Instruction | Description |  
   |-------------|-------------|  
   | `CMA` | Complement accumulator |  
   | `RAL` | Rotate accumulator left through carry |  
   | `RRC` | Rotate accumulator right |  
   | `NOP` | No operation |  
   | `HLT` | Halt CPU |

---

### **1.2 Two-Byte Instructions**

* **Content:** Opcode \+ **8-bit operand** (immediate data or I/O port)

* **Memory:** 2 bytes

* **Purpose:** Load data into registers, perform arithmetic/logical operations with immediate data, or access I/O.

* **Examples:**  
   | Instruction | Description |  
   |-------------|-------------|  
   | `MVI A, 55H` | Load accumulator with immediate data 55H |  
   | `ADI 0AH` | Add immediate 0AH to accumulator |  
   | `IN 01H` | Read data from I/O port 01H |  
   | `OUT 02H` | Send data to I/O port 02H |

---

### **1.3 Three-Byte Instructions**

* **Content:** Opcode \+ **16-bit address** (low byte first, then high byte)

* **Memory:** 3 bytes

* **Purpose:** Access memory locations, jumps, calls, or storing data.

* **Examples:**  
   | Instruction | Description |  
   |-------------|-------------|  
   | `LDA 2050H` | Load accumulator from memory 2050H |  
   | `STA 2052H` | Store accumulator to memory 2052H |  
   | `JMP 3000H` | Unconditional jump to address 3000H |  
   | `CALL 3000H`| Call subroutine at address 3000H |

---

## **2\. Classification Based on Function**

Instruction classification based on **function** is more useful for programming logic and understanding operation types.

---

### **2.1 Data Transfer Instructions**

* **Purpose:** Transfer data between **registers, memory, and I/O ports** without modifying it.

* **Flags Affected:** **None**

**Examples:**

| Instruction | Description |
| ----- | ----- |
| `MOV Rd, Rs` | Copy data from source register to destination register |
| `MVI R, data` | Load immediate 8-bit data into a register |
| `LDA addr` | Load accumulator from memory |
| `STA addr` | Store accumulator into memory |
| `LHLD addr` | Load H-L pair from memory |
| `SHLD addr` | Store H-L pair to memory |
| `LXI RP, data16` | Load 16-bit data into register pair |
| `XCHG` | Exchange D-E and H-L register pairs |
| `IN port` | Read data from I/O port |
| `OUT port` | Send data to I/O port |

---

### **2.2 Arithmetic Instructions**

* **Purpose:** Perform addition, subtraction, increment, decrement, and 16-bit addition.

* **Flags Affected:** **Z, S, P, CY, AC**

**Examples:** `ADD B`, `ADC C`, `SUB D`, `SBB E`, `INR A`, `DCR B`, `INX H`, `DCX D`, `DAD B`, `DAA`

---

### **2.3 Logical Instructions**

* **Purpose:** Perform **bitwise operations** on accumulator, complement, compare, or rotate.

* **Flags Affected:** **Z, S, P, CY (sometimes), AC**

**Examples:** `ANA B`, `ORA C`, `XRA D`, `CMA`, `CMP E`, `CPI 55H`, `RLC`, `RRC`, `RAL`, `RAR`

---

### **2.4 Branch / Program Control Instructions**

* **Purpose:** Control program flow – jumps, calls, returns, conditional execution.

* **Flags Affected:** Program Counter changes; some instructions check **flags**

**Examples:** `JMP 2050H`, `JC 3000H`, `JZ 2050H`, `CALL 3000H`, `RET`, `RST n`

---

### **2.5 Stack / Machine Control Instructions**

* **Purpose:** Handle **stack operations** and control CPU operations like interrupts or halt.

* **Flags Affected:** Usually none

**Examples:** `PUSH B`, `POP D`, `XTHL`, `SPHL`, `HLT`, `NOP`, `EI`, `DI`

---

## **3\. Summary Table**

| Classification | Subtype | Word Length | Purpose | Examples |
| ----- | ----- | ----- | ----- | ----- |
| **Word Length** | 1-byte | 1 | Single-byte operations | CMA, RAL, NOP, HLT |
|  | 2-byte | 2 | Immediate data / I/O operations | MVI, ADI, IN, OUT |
|  | 3-byte | 3 | Memory reference, jumps, calls | LDA, STA, JMP, CALL |
| **Function** | Data Transfer | 1–3 | Move data between registers, memory, I/O | MOV, MVI, LDA, STA, LXI, IN, OUT |
|  | Arithmetic | 1–3 | Perform addition, subtraction, increment, decrement | ADD, SUB, INR, DCR, DAD, INX |
|  | Logical | 1–3 | Perform bitwise, compare, rotate operations | ANA, ORA, XRA, CMP, RLC, RRC |
|  | Branch/Control | 3 | Jump, call, return, restart program | JMP, JC, JZ, CALL, RET, RST |
|  | Stack/CPU Control | 1–1 | Stack operations, CPU control, interrupts | PUSH, POP, HLT, NOP, EI, DI |

---

### **4\. Key Points**

1. Word length determines **memory size occupied** by instruction.

2. Functional classification helps **design program logic**.

3. **Data transfer instructions** are foundational, as they move data to prepare for arithmetic and logical operations.

4. Flags are updated depending on the type of instruction.

