# **Memory-Reference Instructions** 

---

## **1\. Introduction**

**Memory-Reference Instructions (MRI)** are a type of instruction in which the **operand is stored in memory**.

* They are the most common instructions in a computer.

* Operate on **data or addresses stored in memory**.

* Execution involves accessing memory via **Memory Address Register (AR)** and **Memory Data Register (DR)**.

📌 These instructions are also called **Memory-Reference Instructions** because they **reference memory addresses directly or indirectly**.

---

## **2\. General Format (Basic Computer – Mano Model)**

* Word Length: 16 bits

* Fields in instruction:

`| I | Opcode (3 bits) | Address (12 bits) |`

| Field | Description |
| ----- | ----- |
| **I** | Indirect Addressing Bit (0 = direct, 1 = indirect) |
| **Opcode** | Specifies operation (e.g., ADD, AND, LDA, STA, BUN, ISZ) |
| **Address** | 12-bit memory address of operand |

---

## **3\. Types of Memory-Reference Instructions**

Memory-Reference Instructions are classified into:

| Instruction Type | Description |
| ----- | ----- |
| **AND** | Logical AND AC with memory content |
| **ADD** | Add memory content to AC |
| **LDA** | Load memory content into AC |
| **STA** | Store AC content into memory |
| **BUN** | Branch unconditionally to a memory address |
| **BSA** | Branch and save return address |
| **ISZ** | Increment memory content and skip next instruction if zero |

---

## **4\. Addressing Modes**

Memory-Reference Instructions can use:

### **A. Direct Addressing (I = 0\)**

* Operand is **directly stored in memory** at the given address.

* Example:

`ADD 305`

* AC ← AC \+ M\[305\]

### **B. Indirect Addressing (I = 1\)**

* Address field points to a memory location that contains the **actual address of operand**.

* Example:

`ADD I 305`

* Suppose M\[305\] = 500

* Then AC ← AC \+ M\[500\]

---

## **5\. List of Memory-Reference Instructions (Mano Basic Computer)**

| Instruction | Function | Opcode (3 bits) |
| ----- | ----- | ----- |
| **AND** | AC ← AC AND M\[Address\] | 000 |
| **ADD** | AC ← AC \+ M\[Address\] | 001 |
| **LDA** | AC ← M\[Address\] | 010 |
| **STA** | M\[Address\] ← AC | 011 |
| **BUN** | PC ← Address | 100 |
| **BSA** | Save return address & branch | 101 |
| **ISZ** | M\[Address\] ← M\[Address\]+1; Skip next if zero | 110 |

---

## **6\. Execution Steps (Micro-Operations)**

Memory-reference instructions typically execute in **three phases**:

### **A. Fetch Phase**

| Time | Micro-Operation |
| ----- | ----- |
| T0 | AR ← PC |
| T1 | IR ← M\[AR\], PC ← PC \+ 1 |
| T2 | Decode IR |

---

### **B. Indirect Addressing Cycle (if I = 1\)**

| Time | Micro-Operation |
| ----- | ----- |
| T3 | AR ← M\[AR\] → Get effective address from memory |

---

### **C. Execute Phase (depends on opcode)**

#### **1\. AND Instruction**

| Time | Micro-Operation |
| ----- | ----- |
| T4 | DR ← M\[AR\] |
| T5 | AC ← AC AND DR |

#### **2\. ADD Instruction**

| Time | Micro-Operation |
| ----- | ----- |
| T4 | DR ← M\[AR\] |
| T5 | AC ← AC \+ DR |

#### **3\. LDA Instruction**

| Time | Micro-Operation |
| ----- | ----- |
| T4 | DR ← M\[AR\] |
| T5 | AC ← DR |

#### **4\. STA Instruction**

| Time | Micro-Operation |
| ----- | ----- |
| T4 | DR ← AC |
| T5 | M\[AR\] ← DR |

#### **5\. BUN Instruction**

| Time | Micro-Operation |
| ----- | ----- |
| T4 | PC ← AR |

#### **6\. BSA Instruction**

| Time | Micro-Operation |
| ----- | ----- |
| T4 | M\[AR\] ← PC |
| T5 | PC ← AR \+ 1 |

#### **7\. ISZ Instruction**

| Time | Micro-Operation |
| ----- | ----- |
| T4 | M\[AR\] ← M\[AR\] \+ 1 |
| T5 | If M\[AR\] = 0 then PC ← PC \+ 1 |

---

## **7\. Timing and Control**

* Memory-reference instructions require **3–5 clock cycles** depending on:

  * Direct or indirect addressing

  * Operation type

* Controlled by **timing signals T0, T1, …**

* Micro-operations are synchronized with **clock pulses**.

---

## **8\. Flow of Memory-Reference Instruction Execution**

`Fetch → (Indirect Addressing if I=1) → Execute → Store/Branch`

* **Fetch:** Get instruction from memory to IR

* **Indirect Addressing:** Find effective address (if I = 1\)

* **Execute:** Perform operation using AC, DR, or PC

* **Store/Branch:** Save results or branch

---

## **9\. Importance of Memory-Reference Instructions**

* Most **program instructions are memory-reference**.

* Enable **arithmetic, logic, and control operations**.

* Efficient handling of data in memory.

---

## **10\. Summary**

* Memory-reference instructions **operate on memory operands**.

* Instruction format: `I + Opcode + Address`

* Supports **direct and indirect addressing**.

* Includes: **AND, ADD, LDA, STA, BUN, BSA, ISZ**

* Micro-operations involve **AR, DR, AC, and PC**.

* Fundamental to CPU operation and program execution.

