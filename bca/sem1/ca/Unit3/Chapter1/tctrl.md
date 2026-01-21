# **Timing and Control** 

---

## **1\. Introduction**

**Timing and Control** is the part of the computer that **coordinates and controls all operations** inside the CPU.  
 It ensures that **each operation happens at the correct time and in the correct sequence**.

📌 Without timing and control, the CPU cannot execute instructions properly.

---

## **2\. Definition**

**Timing and Control is the mechanism that generates timing signals and control signals required to execute instructions in an orderly and synchronized manner.**

---

## **3\. Purpose of Timing and Control**

Timing and Control is used to:

* Control the sequence of operations

* Synchronize data transfer between registers

* Control ALU operations

* Manage instruction execution

* Coordinate memory and I/O operations

---

## **4\. Clock Pulse and Timing Signals**

The CPU uses a **clock** to generate timing signals.

### **Clock Pulse**

* A clock pulse is a repetitive square wave signal

* Each pulse represents a **time unit**

📌 All CPU operations are synchronized with clock pulses.

---

## **5\. Timing Signals**

* Timing signals divide instruction execution into **time steps**

* Each time step performs a **micro-operation**

### **Timing Variables**

`T0, T1, T2, T3, ….`

---

## **6\. Control Signals**

Control signals are used to:

* Enable registers

* Select ALU operations

* Control memory read/write

* Control bus operations

📌 Control signals decide **what operation** occurs at each time step.

---

## **7\. Instruction Cycle and Timing**

Instruction execution is divided into stages:

---

### **1\. Fetch Cycle**

| Time | Operation |
| ----- | ----- |
| T0 | AR ← PC |
| T1 | IR ← M\[AR\], PC ← PC \+ 1 |
| T2 | Decode instruction |

---

### **2\. Decode Cycle**

* Opcode is decoded

* Instruction type identified

* Control unit prepares execution

---

### **3\. Execute Cycle**

Depends on instruction type:

#### **Example: ADD Instruction**

| Time | Operation |
| ----- | ----- |
| T3 | AR ← IR(0–11) |
| T4 | DR ← M\[AR\] |
| T5 | AC ← AC \+ DR |

---

## **8\. Timing and Control Unit**

The **Control Unit (CU)** generates timing and control signals.

### **Functions**

* Decodes instruction opcode

* Generates sequence of control signals

* Controls data flow between registers

* Controls ALU and memory operations

---

## **9\. Components of Timing and Control Unit**

### **1\. Instruction Decoder**

* Decodes opcode

* Determines instruction type

---

### **2\. Sequence Counter**

* Generates timing signals (T0, T1, T2…)

* Advances on each clock pulse

---

### **3\. Control Logic Gates**

* Generate control signals using:

  * Opcode

  * Timing signals

  * Flags

---

## **10\. Hardwired Control (Mano Basic Computer)**

* Control signals generated using:

  * Decoders

  * Flip-flops

  * Logic gates

* Faster execution

* Less flexible

📌 Used in the Basic Computer model.

---

## **11\. Timing and Control for Instruction Types**

### **A. Memory-Reference Instructions**

* AND

* ADD

* LDA

* STA

* BUN

* ISZ

---

### **B. Register-Reference Instructions**

* CLA

* CMA

* INC

* HLT

---

### **C. Input-Output Instructions**

* INP

* OUT

* ION

* IOF

---

## **12\. Example: Timing and Control for CLA Instruction**

| Time | Operation |
| ----- | ----- |
| T3 | AC ← 0 |

📌 Register-reference instructions usually complete in **one time step**.

---

## **13\. Control Signals Examples**

* Load AC

* Increment PC

* Read Memory

* Write Memory

* Select ALU operation

---

## **14\. Importance of Timing and Control**

* Ensures correct instruction execution

* Prevents data conflicts

* Synchronizes CPU operations

* Improves reliability and efficiency

---

## **15\. Advantages**

* Proper coordination of operations

* High execution speed

* Accurate instruction sequencing

---

## **16\. Summary**

* Timing and Control manages instruction execution

* Uses clock pulses to generate timing signals

* Control signals perform micro-operations

* Control Unit is the heart of timing and control

