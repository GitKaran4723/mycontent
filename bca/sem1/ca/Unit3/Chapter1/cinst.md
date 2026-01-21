# **Computer Instructions** 

---

## **1\. Introduction**

A **computer instruction** is a **binary command** that tells the computer **what operation to perform** and **how to perform it**.

📌 A program is a **sequence of computer instructions** stored in memory.

---

## **2\. Definition**

**A computer instruction is a binary code that specifies an operation to be performed and the operands on which the operation acts.**

---

## **3\. Components of a Computer Instruction**

Each computer instruction consists of **two main parts**:

`| Opcode | Operand |`

### **1\. Opcode (Operation Code)**

* Specifies **what operation** to perform

* Examples:

  * ADD – addition

  * SUB – subtraction

  * AND – logical AND

  * JMP – jump

---

### **2\. Operand**

* Specifies:

  * Data

  * Register

  * Memory address

* Some instructions have **no operands**

---

## **4\. Instruction Format**

The **instruction format** defines how bits are arranged in an instruction.

### **General Format**

`| Opcode | Operand / Address |`

Instruction format depends on:

* CPU architecture

* Word length

* Number of registers

* Addressing modes

---

## **5\. Instruction Format in Basic Computer (Mano Model)**

Word length = **16 bits**

`| I | Opcode (3 bits) | Address (12 bits) |`

| Field | Bits | Description |
| ----- | ----- | ----- |
| I | 1 | Addressing mode |
| Opcode | 3 | Operation |
| Address | 12 | Memory address |

---

## **6\. Types of Computer Instructions**

Computer instructions are classified into the following types:

---

## **1\. Data Transfer Instructions**

Used to move data between registers, memory, and I/O.

**Examples:**

* LOAD

* STORE

* MOV

* IN

* OUT

📌 No data processing is done.

---

## **2\. Arithmetic Instructions**

Used to perform arithmetic operations.

**Examples:**

* ADD

* SUB

* MUL

* DIV

* INC

* DEC

---

## **3\. Logical Instructions**

Used to perform logical operations.

**Examples:**

* AND

* OR

* NOT

* XOR

* COMPARE

---

## **4\. Shift and Rotate Instructions**

Used to shift or rotate bits.

**Examples:**

* SHL

* SHR

* ROL

* ROR

---

## **5\. Control Transfer Instructions**

Used to change the sequence of execution.

**Examples:**

* JMP

* CALL

* RET

* BRANCH

📌 Used in loops and conditional execution.

---

## **6\. Input / Output Instructions**

Used for communication with I/O devices.

**Examples:**

* IN

* OUT

* SKI

* SKO

---

## **7\. Instruction Execution Cycle**

Each instruction is executed through the following steps:

### **1\. Fetch**

* Instruction fetched from memory

* Stored in IR

### **2\. Decode**

* Control Unit decodes instruction

### **3\. Execute**

* ALU performs operation

### **4\. Store**

* Result stored in register or memory

📌 This is called the **Fetch–Decode–Execute Cycle**.

---

## **8\. Addressing Modes**

Addressing modes define **how operands are accessed**.

### **Common Addressing Modes**

| Mode | Description |
| ----- | ----- |
| Immediate | Operand is part of instruction |
| Direct | Address given directly |
| Indirect | Address points to another address |
| Register | Operand in register |
| Indexed | Address \+ index register |

---

## **9\. Memory Reference, Register Reference & I/O Instructions (Mano Model)**

### **1\. Memory-Reference Instructions**

Access memory operands  
 Opcode = 000 to 110

**Examples:**

* AND

* ADD

* LDA

* STA

* BUN

---

### **2\. Register-Reference Instructions**

Operate directly on registers  
 Opcode = 111, I = 0

**Examples:**

* CLA

* CMA

* INC

* HLT

---

### **3\. Input-Output Instructions**

Used for I/O operations  
 Opcode = 111, I = 1

**Examples:**

* INP

* OUT

* ION

* IOF

---

## **10\. Importance of Computer Instructions**

* Controls CPU operation

* Defines program behavior

* Enables data processing

* Determines system performance

---

## **11\. Advantages**

* Efficient execution of programs

* Compact binary representation

* Flexible instruction design

---

## **12\. Summary**

* Computer instruction = Opcode \+ Operand

* Instructions control CPU operations

* Various instruction types exist

* Executed through instruction cycle

## **Register-Reference Instructions (Full Form & Explanation)**

| Instruction | Full Form | One-Line Explanation |
| ----- | ----- | ----- |
| **AND** | Logical AND | Performs bit-by-bit AND operation between AC and memory data. |
| **ADD** | Add | Adds memory data to the Accumulator (AC). |
| **LDA** | Load Accumulator | Loads data from memory into the Accumulator. |
| **STA** | Store Accumulator | Stores the contents of the Accumulator into memory. |
| **BUN** | Branch Unconditionally | Transfers control to a specified memory address without any condition. |
| **CLA** | Clear Accumulator | Clears the contents of the Accumulator (AC ← 0). |
| **CMA** | Complement Accumulator | Complements (1’s complement) the contents of the Accumulator. |
| **INC** | Increment Accumulator | Increments the value of the Accumulator by 1\. |
| **HLT** | Halt | Stops the execution of the program. |

📘 **Note:**

* **AND, ADD, LDA, STA, BUN** → *Memory-reference instructions*

* **CLA, CMA, INC, HLT** → *Register-reference instructions*

