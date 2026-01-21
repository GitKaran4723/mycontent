# **Basic Computer Organization and Design**

## **1\. Introduction**

Computer Organization deals with **how a computer works internally**—how different hardware components are structured and how they interact to execute programs.

* **Computer Architecture** → *What* the computer does (instruction set, addressing modes)

* **Computer Organization** → *How* the computer does it (hardware implementation)

---

## **2\. Functional Units of a Computer**

A computer system consists of **five basic functional units**:

### **1\. Input Unit**

* Accepts data and instructions from the user

* Converts them into binary form

* Sends them to memory or CPU

**Examples:** Keyboard, Mouse, Scanner

---

### **2\. Output Unit**

* Converts binary results into human-readable form

* Displays or prints output

**Examples:** Monitor, Printer

---

### **3\. Memory Unit**

Stores:

* Data

* Instructions

* Intermediate results

* Final results

#### **Types of Memory**

| Memory Type | Characteristics |
| ----- | ----- |
| **Primary Memory** | Fast, volatile |
| RAM | Read/write, volatile |
| ROM | Permanent, non-volatile |
| **Secondary Memory** | Slow, non-volatile (HDD, SSD) |

---

### **4\. Arithmetic Logic Unit (ALU)**

Performs:

* Arithmetic operations: `+ - × ÷`

* Logical operations: `AND, OR, NOT, XOR`

* Comparisons: `< > =`

---

### **5\. Control Unit (CU)**

* Directs all operations of the computer

* Fetches instructions from memory

* Decodes instructions

* Controls data flow between units

---

## **3\. Central Processing Unit (CPU)**

The CPU is the **brain of the computer**.

### **Components of CPU**

1. **ALU**

2. **Control Unit**

3. **Registers**

---

## **4\. Registers**

Registers are **high-speed storage locations inside the CPU**.

### **Common Registers**

| Register | Function |
| ----- | ----- |
| **PC (Program Counter)** | Holds address of next instruction |
| **IR (Instruction Register)** | Holds current instruction |
| **MAR** | Holds memory address |
| **MDR** | Holds data from memory |
| **Accumulator (AC)** | Stores ALU results |
| **General Purpose Registers** | Temporary data storage |

---

## **5\. Instruction Cycle**

Execution of each instruction follows a fixed cycle:

### **Steps**

1. **Fetch** – Instruction fetched from memory

2. **Decode** – Instruction decoded by CU

3. **Execute** – ALU performs operation

4. **Store** – Result stored in memory/register

This is called the **Fetch–Decode–Execute Cycle**.

---

## **6\. Instruction Format**

An instruction consists of:

`| Opcode | Operand / Address |`

* **Opcode** → Operation to be performed

* **Operand** → Data or address

### **Example**

`ADD R1, R2`

---

## **7\. Addressing Modes**

Defines how operands are accessed.

### **Common Addressing Modes**

| Mode | Description |
| ----- | ----- |
| Immediate | Operand is part of instruction |
| Direct | Address directly specified |
| Indirect | Address points to another address |
| Register | Operand in register |
| Indexed | Address \+ index register |

---

## **8\. System Bus Structure**

A **bus** is a communication pathway.

### **Types of Buses**

1. **Data Bus** – Transfers data

2. **Address Bus** – Transfers memory addresses

3. **Control Bus** – Transfers control signals

---

## **9\. Memory Organization**

Memory is organized as a sequence of **addressable locations**.

* Each location has a unique address

* Size depends on:

  * Number of address lines

  * Word length

---

## **10\. Input–Output Organization**

I/O devices communicate with CPU using:

### **I/O Techniques**

1. **Programmed I/O**

2. **Interrupt-driven I/O**

3. **Direct Memory Access (DMA)**

---

## **11\. Hardwired vs Microprogrammed Control**

| Feature | Hardwired Control | Microprogrammed Control |
| ----- | ----- | ----- |
| Speed | Faster | Slower |
| Flexibility | Low | High |
| Complexity | High | Lower |

---

## **12\. Basic Computer Design (Mano Model)**

A basic computer (as per M. Morris Mano) includes:

* 16-bit word length

* Common bus system

* ALU

* Control logic

* Registers

### **Instruction Types**

1. Memory-reference

2. Register-reference

3. Input-output

---

## **13\. Summary**

* Computer organization explains **internal structure**

* CPU executes instructions using registers, ALU, and CU

* Data flows through buses

* Instructions follow a fixed execution cycle

* Efficient design improves performance

# **Instruction Codes**  

## **1\. What is an Instruction Code?**

An **instruction code** is a **binary pattern** stored in memory that tells the computer **what operation to perform** and **on which data**.

➡ In simple words:  
 **Instruction Code = Command given to the CPU**

---

## **2\. Components of an Instruction Code**

Every instruction code has **two main parts**:

`| Opcode | Operand |`

### **1\. Opcode (Operation Code)**

* Specifies **what operation** is to be performed

* Examples:

  * ADD → addition

  * SUB → subtraction

  * AND → logical AND

  * JMP → jump

### **2\. Operand**

* Specifies **data**, **register**, or **memory address**

* Can be:

  * A memory location

  * A register

  * An immediate value

---

## **3\. Instruction Code Format**

The instruction format depends on:

* Word length

* Number of registers

* Addressing modes

### **General Format**

`| Opcode | Address / Operand |`

---

## **4\. Instruction Code Format in Basic Computer (Mano Model)**

### **Word Length: 16 bits**

`| I | Opcode (3 bits) | Address (12 bits) |`

| Field | Bits | Description |
| ----- | ----- | ----- |
| I | 1 | Addressing mode bit |
| Opcode | 3 | Operation code |
| Address | 12 | Memory address |

---

## **5\. Meaning of I Bit**

| I Bit | Meaning |
| ----- | ----- |
| 0 | Direct addressing |
| 1 | Indirect addressing |

---

## **6\. Instruction Code Classification**

Instruction codes are classified into **three types**:

### **1\. Memory-Reference Instructions**

### **2\. Register-Reference Instructions**

### **3\. Input-Output Instructions**

---

## **7\. Memory-Reference Instructions**

Used to access **memory data**.

### **Opcode Range**

`000 to 110`

### **Common Memory-Reference Instructions**

| Opcode | Instruction | Function |
| ----- | ----- | ----- |
| 000 | AND | AC ← AC ∧ M |
| 001 | ADD | AC ← AC \+ M |
| 010 | LDA | AC ← M |
| 011 | STA | M ← AC |
| 100 | BUN | PC ← Address |
| 101 | BSA | Call subroutine |
| 110 | ISZ | Increment & skip if zero |

📌 **Example**

`ADD 500`

Adds content of memory location 500 to AC.

---

## **8\. Register-Reference Instructions**

Operate directly on **CPU registers**.

### **Opcode**

`111 and I = 0`

### **Format**

`| 0 | 111 | Register Operation |`

### **Common Register-Reference Instructions**

| Instruction | Operation |
| ----- | ----- |
| CLA | AC ← 0 |
| CLE | E ← 0 |
| CMA | AC ← ¬AC |
| INC | AC ← AC \+ 1 |
| SPA | Skip if AC positive |
| SNA | Skip if AC negative |
| SZA | Skip if AC zero |
| HLT | Halt computer |

---

## **9\. Input-Output Instructions**

Used for communication with **I/O devices**.

### **Opcode**

`111 and I = 1`

### **Format**

`| 1 | 111 | I/O Operation |`

### **Common I/O Instructions**

| Instruction | Function |
| ----- | ----- |
| INP | Input to AC |
| OUT | Output from AC |
| SKI | Skip if input flag set |
| SKO | Skip if output flag set |
| ION | Enable interrupts |
| IOF | Disable interrupts |

---

## **10\. Instruction Code Execution (Example)**

### **Example Instruction**

`LDA 250`

### **Steps**

1. Instruction fetched from memory

2. Decoded by control unit

3. Address 250 accessed

4. Data loaded into AC

---

## **11\. Direct vs Indirect Instruction Code**

### **Direct Addressing (I = 0\)**

`Address field → Actual data location`

### **Indirect Addressing (I = 1\)**

`Address field → Points to another address`

📌 **Example**

`ADD @300`

---

## **12\. Importance of Instruction Codes**

* Foundation of program execution

* Enables CPU to understand programs

* Controls data movement and processing

* Determines system performance

---

## **13\. Advantages**

* Compact binary representation

* Fast execution

* Flexible instruction design

---

## **14\. Summary**

* Instruction code = Opcode \+ Operand

* Format depends on architecture

* Three main instruction types:

  * Memory reference

  * Register reference

  * I/O

* I bit decides addressing mode

---

### **📘 Exam Tip**

**“Instruction code is a binary code stored in memory that specifies an operation and the location of operands.”**

