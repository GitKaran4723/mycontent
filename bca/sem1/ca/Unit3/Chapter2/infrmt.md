# **Instruction Formats** 

---

## **1\. Introduction**

**Instruction format** refers to the **layout or structure of bits in a machine-level instruction**.

* Instructions are stored in **memory as binary codes**.

* The CPU needs to **decode instructions** to know the operation and operands.

* An instruction format defines **how the opcode, address, and other fields are arranged**.

📌 Proper instruction format design affects **CPU efficiency, instruction length, addressing flexibility, and memory usage**.

---

## **2\. Components of an Instruction**

A typical instruction consists of **two main parts**:

| Field | Purpose |
| ----- | ----- |
| **Opcode** | Specifies the **operation to perform** (e.g., ADD, LDA, STA) |
| **Operand / Address** | Specifies **where the data is** (memory/register) or **immediate value** |
| **Additional fields (optional)** | Can include **register specifiers, mode bits, or condition flags** |

**General Structure:**

`| Opcode | Operand / Address | Additional Bits (optional) |`

---

## **3\. Instruction Formats**

Instruction formats vary by **CPU architecture**. Key types:

### **3.1 Zero-Address Instructions (Stack-Based)**

* Used in **stack machines** (like some early computers).

* Operands are **implicitly on top of the stack**.

* **No address field** is required.

**Example:**

`ADD`

* Meaning: Pop two operands from stack, add them, push result back.

**Features:**

* **Compact** instructions

* Operands are **implicitly in stack**

* Example CPU: **PDP-11, Stack Machines**

---

### **3.2 One-Address Instructions (Accumulator-Based)**

* One **explicit address field**, usually a memory address or register.

* CPU uses **Accumulator (AC)** as implicit operand.

**Format:**

`| Opcode | Address |`

**Example:**

`ADD 2000  // AC ← AC + M[2000]`

* **AC** is used automatically as one operand.

**Pros:**

* Simple

* Shorter instructions

**Cons:**

* Requires **frequent memory access**

---

### **3.3 Two-Address Instructions**

* Two explicit addresses or registers in the instruction.

* One is **source**, one is **destination**.

**Format:**

`| Opcode | Source Address | Destination Address |`

**Example:**

`MOV R1, R2  // R2 ← R1`  
`ADD R1, R3  // R3 ← R3 + R1`

* CPU does not need AC; **both operands specified**.

**Pros:**

* Reduces memory access compared to one-address format

* More flexible

---

### **3.4 Three-Address Instructions**

* Three explicit addresses or registers: **two sources and one destination**.

**Format:**

`| Opcode | Source1 | Source2 | Destination |`

**Example:**

`ADD R1, R2, R3  // R3 ← R1 + R2`

* **All operands explicitly specified**.

**Pros:**

* Maximum flexibility

* Less memory access per instruction

**Cons:**

* Instruction length is longer

---

### **3.5 Zero / One / Two / Three Address Summary**

| Format | \#Operands | Example | Advantage | Disadvantage |
| ----- | ----- | ----- | ----- | ----- |
| Zero-Address | 0 | ADD | Short, simple | Requires stack |
| One-Address | 1 | ADD 2000 | Simple, uses AC | Frequent memory access |
| Two-Address | 2 | ADD R1, R2 | Flexible | Longer instructions |
| Three-Address | 3 | ADD R1, R2, R3 | Very flexible | Instruction length large |

---

## **4\. Instruction Length**

* **Instruction length** depends on the number of address fields:

  * **Zero-address:** shortest (e.g., 8–16 bits)

  * **Three-address:** longest (e.g., 32 bits or more)

* Trade-off: **Instruction length vs. memory access vs. CPU simplicity**

---

## **5\. Addressing Modes in Instruction Formats**

Instruction format also specifies the **addressing mode**, i.e., how the operand is interpreted:

| Addressing Mode | Explanation | Example |
| ----- | ----- | ----- |
| Immediate | Operand is part of instruction | `MOV R1, #5` |
| Direct | Address field gives memory location | `LDA 2000` |
| Indirect | Address field points to memory address containing operand | `LDA (2000)` |
| Register | Operand is in register | `ADD R1, R2` |
| Register Indirect | Register holds memory address | `ADD (R1)` |

*   
  Addressing mode is often indicated by **mode bits in the instruction**.

---

## **6\. Examples of Instruction Formats**

### **6.1 Basic Computer (Morris Mano) Example**

* **Memory-Reference Instructions:** 16 bits

`| Opcode (4 bits) | Address (12 bits) |`

* **Register-Reference Instructions:**

`| Opcode (16 bits, only lower 12 bits used for operation code) |`

* **I/O Instructions:**

`| Opcode (Device + Operation code) |`

### **6.2 Stack Machine Example**

* Instruction is **1 word** (8–16 bits)

* No address fields

* Operands are **top elements of stack**

---

## **7\. Importance of Instruction Format**

1. Determines **CPU complexity**

2. Impacts **instruction length and memory usage**

3. Defines **how many operands can be used per instruction**

4. Affects **execution speed**: more explicit operands → fewer memory accesses

---

## **8\. Summary**

* **Instruction format** defines the **layout of opcode, operand fields, and additional bits**.

* Types: **Zero-address, One-address, Two-address, Three-address**

* Instruction format works together with **addressing modes** to specify **how operands are accessed**.

* Choice of instruction format impacts **speed, flexibility, and memory usage**.

