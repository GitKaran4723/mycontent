# **Central Processing Unit (CPU)** 

---

## **1\. Introduction**

The **Central Processing Unit (CPU)** is the **brain of a computer**.

* It performs **all processing operations**: arithmetic, logic, control, and data transfer.

* It executes instructions stored in memory and coordinates all activities of other computer components.

📌 Without a CPU, a computer is just a collection of memory and input/output devices—it cannot process data.

---

## **2\. Functions of the CPU**

The CPU has three primary functions:

1. **Arithmetic Operations:**

   * Addition, subtraction, multiplication, division, increment, decrement

   * Example: `AC ← AC + DR`

2. **Logical Operations:**

   * AND, OR, NOT, XOR, complement, shift

   * Used for decision making and control

3. **Control Operations:**

   * Directs the flow of data between CPU, memory, and I/O devices

   * Generates control signals to synchronize operations

---

## **3\. Components of the CPU**

The CPU consists of **two main parts**:

| Component | Function |
| ----- | ----- |
| **Arithmetic and Logic Unit (ALU)** | Performs arithmetic and logical operations |
| **Control Unit (CU)** | Directs the execution of instructions and controls data flow |
| **Registers** | Temporary storage inside the CPU for instructions and data |

---

### **3.1 Arithmetic and Logic Unit (ALU)**

* Performs **arithmetic operations**: ADD, SUB, INC, DEC

* Performs **logical operations**: AND, OR, NOT, XOR

* Interacts with **Accumulator (AC)**, **Data Register (DR)**, and **Link (E)**

**Example Micro-Operations:**

`AC ← AC + DR   // Addition`  
`AC ← AC AND DR // Logical AND`  
`AC ← AC’      // Complement`

---

### **3.2 Control Unit (CU)**

The Control Unit manages **all CPU operations**:

1. **Instruction Fetch:** Retrieves instructions from memory

2. **Instruction Decode:** Interprets the opcode and determines operation

3. **Execution Control:** Sends control signals to ALU, registers, memory, and I/O devices

4. **Timing Generation:** Synchronizes operations using clock pulses

**Control Signals Example:**

* `LDAC` – Load AC

* `CLAC` – Clear AC

* `READ` – Read memory

* `WRITE` – Write memory

---

### **3.3 Registers**

Registers are **temporary storage locations inside the CPU** for fast access:

| Register | Purpose |
| ----- | ----- |
| **AC (Accumulator)** | Stores intermediate results of operations |
| **DR (Data Register)** | Holds data read from memory or to be written |
| **AR (Address Register / MAR)** | Holds memory address for read/write |
| **IR (Instruction Register)** | Holds the current instruction being executed |
| **PC (Program Counter)** | Holds address of next instruction |
| **E (Link)** | 1-bit register for carry/overflow |
| **SC (Sequence Counter)** | Controls timing of micro-operations |

---

## **4\. Operation of the CPU**

The CPU works in a **repetitive cycle called the Instruction Cycle**:

### **4.1 Instruction Cycle Steps**

1. **Fetch:**

   * Retrieve the instruction from memory

   * Example: `IR ← M[PC]`, `PC ← PC + 1`

2. **Decode:**

   * CU interprets the instruction

   * Determines type: Memory-Reference, Register-Reference, I/O

3. **Execute:**

   * ALU performs the operation

   * OR data transferred between CPU, memory, or I/O

4. **Store / Write Back:**

   * Result stored back in memory or output register

5. **Check for Interrupts:**

   * If enabled and requested, CPU executes **Interrupt Service Routine (ISR)**

---

## **5\. Data Path in the CPU**

* Data flows between **Memory, ALU, Registers, and I/O devices** through **buses**:

`Memory ↔ DR ↔ AC ↔ ALU ↔ E`  
          `↕`  
        `I/O Registers`

* Controlled by the **CU** using **control signals**.

---

## **6\. Types of Operations Performed by CPU**

| Operation Type | Example Instructions |
| ----- | ----- |
| **Memory-Reference** | LDA, ADD, STA, BUN |
| **Register-Reference** | CLA, CMA, INC, HLT |
| **I/O Operations** | INP, OUT, SKI, SKO, ION, IOF |

---

## **7\. Timing and Control in the CPU**

* **Clock signals** divide time into steps (T0, T1, T2…)

* Each step triggers **micro-operations**, e.g., `AR ← PC` or `AC ← DR`

* Control Unit generates **synchronized control signals** for **fetch, decode, execute**

**Example:** Fetch Cycle

| Time | Micro-Operation |
| ----- | ----- |
| T0 | AR ← PC |
| T1 | IR ← M\[AR\], PC ← PC \+ 1 |
| T2 | Decode IR |

---

## **8\. Interrupts in CPU**

* CPU can **pause current execution** to respond to **external events**.

* Steps for handling an interrupt:

  1. Save PC and status

  2. Jump to **Interrupt Service Routine (ISR)**

  3. Execute ISR

  4. Return to original program

* Controlled using **IEN flag** and I/O flags (**FGI / FGO**).

---

## **9\. Summary**

* **CPU is the central unit of a computer** that executes instructions.

* Composed of **ALU, Control Unit, and Registers**.

* Performs **arithmetic, logic, control, and I/O operations**.

* Works using **instruction cycles**: fetch → decode → execute → store.

* Uses **control signals and buses** to manage data flow.

* Supports **interrupts for asynchronous events**.

# **General Register Organization** 

---

## **1\. Introduction**

**General Register Organization** refers to a CPU design in which a set of **general-purpose registers (GPRs)** is used to **store data temporarily during program execution**.

* Registers are **high-speed storage elements inside the CPU**.

* They **reduce memory access**, speeding up execution.

* Unlike **accumulator-based computers** (which have only one main register), general register computers use **multiple registers**.

---

## **2\. Concept**

* A **general register** can store **data, operands, or intermediate results**.

* **Any general register can be used for any operation** (hence “general-purpose”).

* Instructions can **operate directly on registers**, reducing dependence on memory.

**Example:**

`R1 ← R2 + R3`

Here, R1, R2, R3 are general-purpose registers.

---

## **3\. Structure of General Register Organization**

### **3.1 Components**

| Component | Function |
| ----- | ----- |
| **General-Purpose Registers (R0-Rn)** | Store operands, results, or data temporarily |
| **ALU (Arithmetic Logic Unit)** | Performs arithmetic and logical operations using registers |
| **Control Unit** | Generates control signals to select registers and perform operations |
| **Bus System** | Transfers data between registers, memory, and ALU |

---

### **3.2 Register File**

* A **register file** is a **collection of general-purpose registers**.

* Example: 8 registers (R0 to R7), each 16 bits.

* Contains **read and write ports** to allow ALU to read/write data simultaneously.

**Diagram (conceptual)**

          `+---------------------+`  
           `|  Register File      |`  
           `|  R0  R1  R2  ... R7|`  
           `+---------------------+`  
            `^         ^`  
            `|         |`  
          `Read Bus   Write Bus`

---

### **3.3 Read and Write Ports**

* **Read Port:** Sends content of a register to ALU.

* **Write Port:** Receives output from ALU and stores it into a register.

* **Multiple ports** allow simultaneous operations.

---

## **4\. Operations Using General Registers**

### **4.1 Arithmetic Operations**

`R1 ← R2 + R3  // Add contents of R2 and R3, store result in R1`

* **R2 and R3** send values to ALU

* ALU performs addition

* Result written into **R1**

### **4.2 Logical Operations**

`R0 ← R1 AND R2  // Logical AND of R1 and R2, result in R0`

* Similar flow as arithmetic operations

### **4.3 Data Transfer**

`R3 ← Memory[100]   // Load from memory to R3`  
`Memory[200] ← R4   // Store from R4 to memory`

---

## **5\. Advantages of General Register Organization**

1. **Faster execution:**

   * Reduces memory access; operations are mostly register-to-register.

2. **Flexibility:**

   * Any register can be used for any operation.

3. **Reduced instruction length:**

   * Register addressing requires fewer bits than memory addressing.

4. **Supports complex instructions efficiently:**

   * Useful in **Load/Store architectures**.

---

## **6\. Addressing Modes with Registers**

* **Register Addressing Mode:** Operand is in a register

* **Register Indirect Addressing:** Register contains memory address

* **Immediate Addressing:** Constant operand specified in instruction

**Example:**

| Instruction | Meaning |
| ----- | ----- |
| `ADD R1, R2` | R1 ← R1 \+ R2 |
| `MOV R0, #5` | R0 ← 5 (immediate value) |
| `LOAD R3, (R4)` | Load content of memory addressed by R4 into R3 |

---

## **7\. Comparison with Accumulator-Based Architecture**

| Feature | Accumulator-Based | General Register-Based |
| ----- | ----- | ----- |
| Number of registers | 1 (AC) | Multiple (R0-Rn) |
| Memory access | Frequent | Reduced (register-to-register operations) |
| Instruction length | Short | Slightly longer (needs to specify registers) |
| Flexibility | Limited | High |
| Speed | Moderate | High |

**Conclusion:** General registers make the CPU faster and more flexible than accumulator-only architectures.

---

## **8\. CPU Organization with General Registers**

**Data Flow Example:**

`Memory → DR → R2 → ALU → R1 → Memory/Output`

* The **ALU** takes operands from registers, performs operation, and writes back to a register or memory.

* The **Control Unit** selects which registers participate in each operation.

---

## **9\. Summary**

* **General Register Organization** uses multiple high-speed registers for computation.

* Reduces dependence on memory, speeding up execution.

* Supports **arithmetic, logical, and data transfer operations**.

* Provides **flexibility** and **efficient instruction execution**.

* Widely used in **modern CPU designs** and **RISC architectures**.

