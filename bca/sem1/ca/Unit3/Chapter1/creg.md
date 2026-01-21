# **Computer Registers** 

---

## **1\. Introduction**

A **computer register** is a **small, very fast memory unit located inside the CPU**.  
 Registers temporarily store **data, instructions, addresses, and intermediate results** during program execution.

👉 Registers are the **fastest storage elements** in a computer system.

---

## **2\. Why Computer Registers Are Needed**

* CPU speed is much higher than main memory (RAM)

* Accessing memory for every operation slows execution

* Registers provide **immediate access** to data

* Improve **processing speed and efficiency**

📌 Without registers, instruction execution would be very slow.

---

## **3\. Characteristics of Registers**

* Very high speed

* Very small storage capacity

* Located inside CPU

* Directly connected to ALU and Control Unit

* Cost per bit is high

---

## **4\. Functions of Computer Registers**

Registers are used to:

* Store instructions being executed

* Store operands for ALU operations

* Store memory addresses

* Store intermediate and final results

* Control program execution

---

## **5\. Classification of Registers**

### **A. Based on Visibility**

1. **User-Visible Registers**

2. **Control and Status Registers**

---

## **6\. Common Computer Registers (General CPU)**

---

### **1\. Accumulator (AC)**

* Stores intermediate results of arithmetic and logic operations

* Connected directly to ALU

* Most operations use AC

**Example:**

`ADD X → AC ← AC + X`

---

### **2\. General Purpose Registers (GPR)**

* Used to store data and operands

* Accessible by programmers

* Example: R0, R1, R2

📌 Reduce memory access time

---

### **3\. Program Counter (PC)**

* Stores the address of the **next instruction**

* Automatically increments after each instruction fetch

* Changed during branching and jumps

📌 Ensures sequential execution of instructions

---

### **4\. Instruction Register (IR)**

* Holds the instruction currently being executed

* Control Unit decodes instruction from IR

---

### **5\. Memory Address Register (MAR)**

* Stores address of memory location to be accessed

* Used during memory read/write operations

---

### **6\. Memory Data Register (MDR)**

* Holds data read from memory or to be written to memory

---

### **7\. Stack Pointer (SP)**

* Stores address of the top of the stack

* Used in:

  * Subroutine calls

  * Interrupt handling

  * Recursion

---

### **8\. Index Register (XR)**

* Used for indexed addressing

* Helps in array and loop processing

---

### **9\. Status / Flag Register**

Stores condition flags such as:

* Zero (Z)

* Carry (C)

* Sign (S)

* Overflow (V)

📌 Used in conditional branching

---

## **7\. Registers in Basic Computer (Morris Mano Model)**

| Register | Size | Function |
| ----- | ----- | ----- |
| **AR (Address Register)** | 12 bits | Holds memory address |
| **PC (Program Counter)** | 12 bits | Address of next instruction |
| **DR (Data Register)** | 16 bits | Holds data from memory |
| **AC (Accumulator)** | 16 bits | Arithmetic & logic operations |
| **IR (Instruction Register)** | 16 bits | Current instruction |
| **TR (Temporary Register)** | 16 bits | Temporary storage |
| **INPR** | 8 bits | Input data |
| **OUTR** | 8 bits | Output data |
| **E (Link Register)** | 1 bit | Carry / borrow bit |

---

## **8\. Register Organization**

* Registers are connected using a **common bus system**

* Control Unit controls register transfers

* Multiplexers select register outputs

---

## **9\. Register Transfer Language (RTL)**

RTL is used to describe data movement between registers.

### **Example**

`DR ← M[AR]`  
`AC ← AC + DR`

---

## **10\. Difference Between Registers and Main Memory**

| Feature | Registers | Main Memory |
| ----- | ----- | ----- |
| Speed | Very fast | Slower |
| Location | Inside CPU | Outside CPU |
| Capacity | Very small | Large |
| Cost | High | Lower |

---

## **11\. Advantages of Computer Registers**

* Fast data access

* Faster instruction execution

* Reduces memory access

* Improves CPU performance

---

## **12\. Disadvantages**

* Limited storage capacity

* Expensive hardware

* Complex control circuitry

---

## **13\. Applications of Registers**

* Arithmetic and logic processing

* Program control

* Memory addressing

* Input/Output operations

---

## **14\. Summary**

* Registers are small, fast memory units inside CPU

* Store data, instructions, and addresses temporarily

* Multiple registers exist for different purposes

* Essential for fast and efficient program execution

---

