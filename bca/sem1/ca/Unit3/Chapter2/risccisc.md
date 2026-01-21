# **Reduced Instruction Set Computer (RISC)** 

---

## **1\. Introduction**

**RISC (Reduced Instruction Set Computer)** is a **CPU design philosophy** that uses a **small, highly optimized set of instructions**.

* Focuses on **simple instructions that can execute very quickly**, usually in **one clock cycle**.

* RISC designs aim for **high performance, pipelining, and efficient hardware utilization**.

**Key Idea:**

“Simpler instructions executed faster, and more instructions can be combined to perform complex tasks.”

---

## **2\. Features of RISC Architecture**

1. **Small Instruction Set**

   * Limited number of instructions (usually \< 100\)

   * Each instruction is simple and uniform in length

2. **Single-Cycle Execution**

   * Most instructions complete in **one clock cycle**

   * Reduces **CPU complexity and execution time**

3. **Load/Store Architecture**

   * Only **load and store instructions access memory**

   * All other operations (arithmetic, logical) work on **registers**

4. **Fixed Instruction Length**

   * Usually **32-bit instructions**

   * Simplifies **instruction decoding** and **pipelining**

5. **Large Number of General-Purpose Registers**

   * Reduces memory access frequency

   * Improves performance

6. **Simple Addressing Modes**

   * Usually supports only **register and immediate addressing**

   * Complex addressing handled via multiple simple instructions

7. **Pipelining Friendly**

   * Uniform instruction length and simplicity make **pipelining easier**

---

## **3\. Advantages of RISC**

1. **Faster execution** due to single-cycle instructions

2. **Simpler hardware design** → easier to implement pipelines

3. **Efficient use of registers** → reduces memory access delays

4. **Predictable instruction timing** → simplifies compiler optimization

5. **Scalability** → RISC cores can be used in embedded systems, smartphones, etc.

---

## **4\. Disadvantages of RISC**

1. **More instructions per program**

   * Complex operations may require several simple instructions

2. **Larger code size**

   * Because one high-level operation may need multiple simple instructions

3. **Compiler dependency**

   * Performance depends heavily on compiler optimization

---

## **5\. Instruction Types in RISC**

RISC instructions are usually classified as:

**Load/Store Instructions** – Access memory

 `LOAD R1, 2000   // R1 ← M[2000]`  
`STORE R1, 3000  // M[3000] ← R1`

1. 

**Arithmetic and Logic Instructions** – Operate on registers

 `ADD R1, R2, R3  // R3 ← R1 + R2`  
`AND R1, R2, R3  // R3 ← R1 AND R2`

2. 

**Branch / Control Instructions** – Change program flow

 `BEQ R1, R2, LABEL  // Branch if R1 = R2`  
`JMP ADDRESS         // Unconditional jump`

3. 

**Immediate Instructions** – Operate with constants

 `ADDI R1, R2, #5  // R2 ← R2 + 5`

4. 

---

## **6\. Examples of RISC Processors**

* **ARM (Advanced RISC Machine)** – Widely used in smartphones

* **MIPS (Microprocessor without Interlocked Pipeline Stages)**

* **SPARC (Scalable Processor Architecture)**

* **PowerPC (used in Apple and embedded systems)**

---

## **7\. Why RISC is Important**

1. **High-performance computing**

   * Simple instructions, pipelining → faster execution

2. **Embedded Systems**

   * Low power consumption, simple design

3. **Compiler-friendly**

   * Easier to optimize due to simple instruction set

4. **Scalable architecture**

   * Can be implemented in single-core, multi-core, or embedded devices

---

## **8\. Summary**

* **RISC (Reduced Instruction Set Computer)** is a CPU design that uses a **small set of simple instructions**.

* Focuses on **speed, pipelining, and register operations**.

* Uses **load/store architecture**, **fixed-length instructions**, and **large number of registers**.

* Advantages: fast execution, simple hardware, easy pipelining.

* Disadvantages: larger code size, more instructions per program.

# **Complex Instruction Set Computer (CISC)** 

---

## **1\. Introduction**

**CISC (Complex Instruction Set Computer)** is a CPU design philosophy that:

* Uses a **large number of instructions**, some of which can perform **complex tasks in a single instruction**.

* The goal is to **reduce the number of instructions per program**, even if individual instructions take **multiple clock cycles** to execute.

**Key Idea:**

“Fewer instructions per program, but each instruction can be complex and take multiple steps.”

CISC was dominant in early computing due to **memory limitations** and the desire to **simplify programming**.

---

## **2\. Features of CISC Architecture**

1. **Large Instruction Set**

   * Hundreds of instructions available

   * Can perform complex operations like **arithmetic, memory operations, string processing**

2. **Variable Instruction Length**

   * Instructions may vary from **1 to several bytes**

   * Includes multiple operands, addressing modes, and operation codes

3. **Multiple Addressing Modes**

   * Supports **direct, indirect, register, memory, indexed, and immediate** addressing

   * Makes programming easier

4. **Memory-to-Memory Operations**

   * Many instructions can directly operate on **memory operands** without using registers

5. **Microcode-Based Execution**

   * Complex instructions are broken down into **micro-operations** executed sequentially by the control unit

6. **Fewer Registers**

   * Relies more on **memory for intermediate results** than on registers

7. **Instruction Complexity**

   * Some instructions can perform **load, operation, and store in one instruction**

---

## **3\. Advantages of CISC**

1. **Reduced number of instructions per program**

   * One instruction can perform multiple tasks

2. **Ease of programming**

   * Higher-level operations directly supported by hardware

3. **Memory-efficient programs**

   * Because instructions can be complex, fewer instructions are needed

4. **Backward compatibility**

   * New CISC CPUs often support older instruction sets

---

## **4\. Disadvantages of CISC**

1. **Slower execution per instruction**

   * Complex instructions require multiple cycles to execute

2. **Difficult to pipeline**

   * Variable instruction length and complexity make pipelining harder

3. **Complex hardware**

   * Control unit is complicated due to microcode and multiple addressing modes

4. **Increased design cost**

   * More transistors used for decoding complex instructions

---

## **5\. Instruction Types in CISC**

CISC instructions often include:

**Memory-to-Memory Operations**

 `ADD 2000, 2001  // M[2000] ← M[2000] + M[2001]`

1. 

**Arithmetic/Logic with Multiple Operands**

 `MUL R1, R2, M[2000]  // R1 ← R2 * M[2000]`

2. 

**String and Bit Manipulation**

 `MOVS, CMPS  // Move or compare strings`

3. 

**Subroutine Call and Return**

 `CALL Address`

`RET`

4.   
5. **Complex Addressing**

   * Direct, indirect, indexed, based, relative, register indirect

---

## **6\. Examples of CISC Processors**

* **Intel x86 family** (8086, 80286, Pentium, Core i7)

* **VAX (Digital Equipment Corporation)**

* **IBM System/360**

These processors can execute **high-level instructions directly**, such as string copy, multiply-and-add, or procedure call, in a single instruction.

---

## **7\. Why CISC is Important**

1. **Ease of programming**

   * Complex operations are built-in; fewer instructions needed

2. **Memory-efficient**

   * Programs occupy less memory

3. **Backward compatibility**

   * Supports older software without modification

4. **Suitable for early hardware**

   * When memory was slow and expensive, reducing program size was crucial

---

## **8\. Summary**

* **CISC (Complex Instruction Set Computer)** is a CPU design philosophy that provides **many complex instructions**, often capable of performing multiple tasks in a single instruction.

* Features include **large instruction set, variable instruction length, multiple addressing modes, memory-to-memory operations, and microcode execution**.

* Advantages: fewer instructions per program, ease of programming, memory efficiency.

* Disadvantages: slower execution per instruction, complex hardware, and difficulty in pipelining.

## **Differences Between RISC and CISC**

| Feature | RISC | CISC |
| ----- | ----- | ----- |
| **Instruction Set** | Small, simple, optimized instructions | Large, complex instructions |
| **Instruction Length** | Fixed (usually 32-bit) | Variable (1–15 bytes) |
| **Execution Time** | Most instructions execute in **one clock cycle** | Instructions may take **multiple cycles** |
| **Memory Access** | **Load/Store architecture** – only load and store access memory | Many instructions can directly access memory |
| **Addressing Modes** | Few, simple addressing modes | Many, complex addressing modes |
| **Registers** | Large number of **general-purpose registers** | Fewer registers; relies more on memory |
| **Hardware Complexity** | Simple, easy to pipeline | Complex, requires microcode to execute instructions |
| **Code Size** | Usually larger (more instructions per program) | Usually smaller (complex instructions reduce instruction count) |
| **Pipelining** | Easy to implement | Harder due to variable instruction length and complexity |
| **Execution Philosophy** | “Do simple things very fast” | “Do complex things in fewer instructions” |
| **Examples** | ARM, MIPS, SPARC | Intel x86 series, VAX, IBM System/360 |

---

## **Advantages and Disadvantages**

### **RISC**

**Advantages:**

1. High performance due to single-cycle instructions

2. Simple hardware and easier pipelining

3. Efficient use of registers → reduces memory access

4. Compiler-friendly and scalable architecture

**Disadvantages:**

1. More instructions per program

2. Larger code size

3. Heavily dependent on compiler optimization

---

### **CISC**

**Advantages:**

1. Fewer instructions per program

2. Easier for assembly programming and complex operations

3. Memory-efficient programs (smaller program size)

4. Backward compatibility with older software

**Disadvantages:**

1. Slower execution per instruction

2. Complex hardware → more transistors for control unit

3. Difficult to implement pipelining

---

## **Examples of Usage**

* **RISC CPUs:** ARM (smartphones, embedded systems), MIPS (teaching and embedded), SPARC (servers)

* **CISC CPUs:** Intel x86 series (PCs), VAX (minicomputers), IBM System/360 (mainframes)

---

##  **Summary**

* **RISC** is **simple, fast, and hardware-friendly**, but may require more instructions and larger code.

* **CISC** is **complex, memory-efficient, and programmer-friendly**, but may be slower per instruction and more hardware-intensive.

* The choice between RISC and CISC depends on **application, performance, and hardware design considerations**.

