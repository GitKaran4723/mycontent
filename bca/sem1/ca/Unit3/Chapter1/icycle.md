# **Instruction Cycle** 

---

## **1\. Introduction**

The **Instruction Cycle** (also called **Fetch-Decode-Execute Cycle**) is the **fundamental operational process of a CPU**. It is the **sequence of steps that the CPU performs to execute a single instruction** from a program stored in memory.

* Every instruction in a program undergoes this cycle.

* Controlled by the **Control Unit**.

* Synchronized with the **system clock**.

---

## **2\. Definition**

**Instruction Cycle is the sequence of micro-operations performed by the CPU to fetch an instruction from memory, decode it, execute it, and store the result.**

---

## **3\. Phases of the Instruction Cycle**

The instruction cycle consists of **four main phases**:

1. **Fetch Phase**

2. **Decode Phase**

3. **Execute Phase**

4. **Interrupt Phase (Optional)**

Some architectures include **Indirect Addressing Cycle** as a sub-phase if needed.

---

## **4\. Registers Used in Instruction Cycle**

| Register | Function |
| ----- | ----- |
| **PC (Program Counter)** | Holds the address of the next instruction |
| **IR (Instruction Register)** | Holds the current instruction |
| **AR (Address Register / MAR)** | Holds the memory address for read/write |
| **DR (Data Register / MDR)** | Holds data read from memory or to be written to memory |
| **AC (Accumulator)** | Stores results of arithmetic/logic operations |
| **INPR / OUTR** | Input/output registers for I/O instructions |
| **E (Link / Carry bit)** | Holds carry or overflow in arithmetic operations |

---

## **5\. Step 1 – Fetch Phase**

The **fetch phase** retrieves the instruction from memory.

### **Micro-Operations**

| Time Step | Operation |
| ----- | ----- |
| **T0** | AR ← PC → Send address of next instruction to memory |
| **T1** | IR ← M\[AR\], PC ← PC \+ 1 → Fetch instruction and increment PC |
| **T2** | Decode IR → Identify opcode and instruction type |

📌 After this phase, the instruction is ready to be executed.

---

## **6\. Step 2 – Decode Phase**

During the **decode phase**:

* The **Control Unit** examines the **opcode**.

* Determines the **type of instruction**:

  * Memory-Reference Instruction (e.g., LDA, ADD)

  * Register-Reference Instruction (e.g., CLA, CMA)

  * Input-Output Instruction (e.g., INP, OUT)

* Determines the **addressing mode**:

  * Direct or Indirect (I-bit in Basic Computer)

---

## **7\. Step 3 – Execute Phase**

The **execute phase** carries out the operation specified by the instruction.

### **A. Memory-Reference Instructions**

**Examples:** ADD, AND, LDA, STA, BUN, ISZ

#### **Example: ADD Instruction**

| Time | Micro-Operation |
| ----- | ----- |
| T3 | AR ← IR(0–11) → Load address field of instruction |
| T4 | DR ← M\[AR\] → Fetch data from memory |
| T5 | AC ← AC \+ DR → Add data to accumulator |

#### **Example: LDA Instruction**

| Time | Micro-Operation |
| ----- | ----- |
| T3 | AR ← IR(0–11) |
| T4 | DR ← M\[AR\] |
| T5 | AC ← DR |

---

### **B. Register-Reference Instructions**

**Examples:** CLA, CMA, INC, HLT

* Execute directly inside CPU using registers

* Usually complete in **1 micro-operation**

#### **Example: CLA (Clear Accumulator)**

| Time | Micro-Operation |
| ----- | ----- |
| T3 | AC ← 0 |

---

### **C. Input/Output Instructions**

**Examples:** INP, OUT, SKI, SKO

* Interact with input/output devices

* Example: INP (Input to AC)  
   | Time | Micro-Operation |  
   |------|----------------|  
   | T3 | AC(0–7) ← INPR |

---

### **D. Indirect Addressing Cycle**

If **I = 1** (indirect addressing):

| Time | Micro-Operation |
| ----- | ----- |
| T3 | AR ← M\[AR\] → Fetch the actual address from memory |

📌 Only for instructions that use **indirect memory addressing**.

---

## **8\. Step 4 – Interrupt Phase (Optional)**

If an **interrupt** occurs:

1. CPU **saves the current PC** and relevant registers.

2. **Transfers control** to the Interrupt Service Routine (ISR).

3. Executes ISR.

4. Returns to the next instruction.

---

## **9\. Timing of the Instruction Cycle**

* Each phase occurs during **one or more clock cycles**.

* **Timing signals** (T0, T1, T2, …) control micro-operations.

* Ensures proper **sequencing and synchronization**.

**Example Timing Sequence:**

`T0 → Send PC to MAR`  
`T1 → Fetch instruction to IR, increment PC`  
`T2 → Decode instruction`  
`T3 → Execute (or indirect addressing)`  
`T4 → Execute (complete operation)`

---

## **10\. Instruction Cycle Diagram (Conceptual)**

     `┌───────────┐`  
      `│ Fetch     │`  
      `└─────┬─────┘`  
            `│`  
            `▼`  
      `┌───────────┐`  
      `│ Decode    │`  
      `└─────┬─────┘`  
            `│`  
            `▼`  
      `┌───────────┐`  
      `│ Execute   │`  
      `└─────┬─────┘`  
            `│`  
            `▼`  
      `┌───────────┐`  
      `│ Interrupt │`  
      `└───────────┘`

---

## **11\. Importance of Instruction Cycle**

* Ensures **proper execution of programs**.

* Synchronizes **CPU operations**.

* Enables **efficient use of registers, memory, and ALU**.

* Forms the basis for **pipelining** in advanced CPUs.

---

## **12\. Advantages**

* Structured and systematic execution

* Enables CPU to execute any instruction type

* Ensures sequential processing

* Supports interrupts and multitasking

---

## **13\. Summary**

* The **Instruction Cycle** is the **basic operational cycle of the CPU**.

* Phases: **Fetch → Decode → Execute → Interrupt (optional)**.

* Uses **registers, timing signals, and control signals**.

* Includes **indirect addressing** if required.

* Fundamental to **all computer operations**.

