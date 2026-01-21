# **Addressing Modes** 

---

## **1\. Introduction**

**Addressing mode** defines **how the operand of an instruction is specified or accessed** by the CPU.

* It tells the **CPU where to find the data** for the instruction.

* Operands can be **in memory, in registers, or as immediate values in the instruction**.

* Proper use of addressing modes **reduces instruction length, improves flexibility, and speeds up execution**.

---

## **2\. Components of an Instruction Related to Addressing**

A typical instruction has:

| Field | Purpose |
| ----- | ----- |
| **Opcode** | Specifies the operation (ADD, LDA, STA, etc.) |
| **Address / Operand Field** | Specifies where to find the data |
| **Mode Bits (optional)** | Indicate the addressing mode |

*   
  **Instruction decoding** depends on both **opcode** and **addressing mode bits**.

---

## **3\. Classification of Addressing Modes**

### **3.1 Immediate Addressing**

* **Operand is part of the instruction itself**

* CPU does not need to access memory

**Format:**

`Opcode | Operand (constant value)`

**Example:**

`MOV R1, #5   // R1 ← 5`

**Advantages:**

* Fast (no memory access)

* Simple for constants

**Disadvantages:**

* Limited by instruction size

---

### **3.2 Direct (Absolute) Addressing**

* **Address field contains the memory location** of the operand

**Format:**

`Opcode | Address`

**Example:**

`LDA 2000   // AC ← M[2000]`

**Advantages:**

* Simple to implement

**Disadvantages:**

* Instruction length increases for large memory

* Less flexible

---

### **3.3 Indirect Addressing**

* **Address field points to memory location that contains the actual operand address**

* Two memory accesses are required

**Example:**

`LDA (2000)   // AC ← M[M[2000]]`

**Advantages:**

* Allows **dynamic memory allocation**

**Disadvantages:**

* Slower (extra memory access)

---

### **3.4 Register Addressing**

* Operand is in a **CPU register**

* No memory access required

**Example:**

`ADD R1, R2   // R2 ← R2 + R1`

**Advantages:**

* Fastest access

* Reduces memory traffic

---

### **3.5 Register Indirect Addressing**

* **Register contains the memory address** of the operand

**Example:**

`MOV R1, (R2)   // R1 ← M[R2]`

**Advantages:**

* Combines speed of register and flexibility of memory

---

### **3.6 Implicit / Implied Addressing**

* Operand is **implicitly specified in the instruction**

* Common in **accumulator-based instructions**

**Example:**

`CLA   // Clear AC`  
`CMA   // Complement AC`

* No explicit operand field is needed

---

### **3.7 Relative Addressing**

* **Operand address is calculated relative to program counter (PC)**

* Used in **branch instructions**

**Example:**

`BUN LABEL   // PC ← PC + Offset`

**Advantages:**

* Supports **program relocation**

* Compact instruction format

---

### **3.8 Indexed Addressing**

* **Effective address = Base address (from instruction) \+ Index register content**

* Useful for **arrays and tables**

**Example:**

`LDA 1000(X)   // AC ← M[1000 + X]`

**Advantages:**

* Efficient for **array operations**

---

## **4\. Summary of Addressing Modes**

| Mode | Operand Location | Access Time | Example |
| ----- | ----- | ----- | ----- |
| Immediate | In instruction | Fastest | `MOV R1, #5` |
| Direct | Memory | Moderate | `LDA 2000` |
| Indirect | Memory → Memory | Slower | `LDA (2000)` |
| Register | CPU Register | Fast | `ADD R1, R2` |
| Register Indirect | Register points to Memory | Moderate | `MOV R1, (R2)` |
| Implicit | No operand field | Fast | `CLA` |
| Relative | Memory relative to PC | Moderate | `BUN LABEL` |
| Indexed | Base \+ Index register | Moderate | `LDA 1000(X)` |

---

## **5\. Importance of Addressing Modes**

1. **Reduce instruction length:** Immediate and relative modes help compact instructions

2. **Increase flexibility:** Various modes allow accessing registers, memory, and constants

3. **Support structured programming:** Indexed addressing helps with arrays and loops

4. **Improve performance:** Register addressing is fast; memory-intensive operations use indirect or indexed modes

---

## **6\. Addressing Modes in Basic Computer (Morris Mano)**

* **Memory-Reference Instructions:**

  * **Direct Addressing:** AC ← M\[Address\]

  * **Indirect Addressing:** AC ← M\[M\[Address\]\]

  * **I (Indirect Bit):** 0 = direct, 1 = indirect

* **Register-Reference Instructions:**

  * Implicit addressing (operates on AC)

* **I/O Instructions:**

  * Operand in I/O device register

