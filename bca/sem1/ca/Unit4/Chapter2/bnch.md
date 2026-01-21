# **Branch Operations in 8085 Microprocessor**

---

## **1\. Introduction**

**Branch instructions** are used to **change the sequence of execution** in a program.

* They allow **conditional or unconditional jumps**, subroutine calls, and returns.

* **Purpose:** Control program flow for loops, conditional execution, and subroutine management.

**Flags Affected:**

* Branch instructions generally **do not affect any flags** themselves.

* **Conditional branches** rely on the current status of flags (Z, CY, S, P, AC) to decide whether to branch.

---

## **2\. Types of Branch Operations**

Branch instructions in 8085 are divided into **3 main types**:

1. **Jump Instructions**

2. **Call Instructions**

3. **Return Instructions**

4. **Restart Instructions**

---

## **3\. Detailed Explanation of Each Type**

---

### **3.1 Jump Instructions**

Jump instructions **change the program counter (PC)** to a specified address, making the program execution jump to another memory location.

#### **1\. Unconditional Jump**

* **Instruction:** `JMP address`

* **Purpose:** Always jump to the specified memory address.

* **Example:**

`JMP 2050H   ; Jump unconditionally to memory location 2050H`

#### **2\. Conditional Jumps**

* Execute jump **only if certain condition (flag) is true**.

* **Instructions:**

| Instruction | Condition | Flag Checked |
| ----- | ----- | ----- |
| `JC addr` | Jump if carry set | CY = 1 |
| `JNC addr` | Jump if carry not set | CY = 0 |
| `JZ addr` | Jump if zero | Z = 1 |
| `JNZ addr` | Jump if not zero | Z = 0 |
| `JP addr` | Jump if positive | S = 0 |
| `JM addr` | Jump if negative | S = 1 |
| `JPE addr` | Jump if parity even | P = 1 |
| `JPO addr` | Jump if parity odd | P = 0 |

**Example:**

`MVI A, 00H`  
`JZ 2050H   ; Jump to 2050H if accumulator is zero`

#### **3\. Jump via Register Pair (Indirect Jump)**

* **Instruction:** `PCHL`

* Loads the **program counter with the contents of H-L pair** for indirect jump.

* Example:

`LXI H, 3000H`  
`PCHL       ; PC = 3000H, jumps to address in H-L`

---

### **3.2 Call Instructions**

Call instructions are used to **execute a subroutine** at a specific memory location.

#### **1\. Unconditional Call**

* **Instruction:** `CALL addr`

* **Purpose:** Jump to subroutine at address `addr`.

* **Mechanism:**

  1. Push **return address** (next instruction) onto **stack**.

  2. Jump to subroutine.

**Example:**

`CALL 2050H  ; Call subroutine at 2050H`

#### **2\. Conditional Call**

* Execute subroutine **only if condition (flag) is true**.

* **Instructions:** `CC`, `CNC`, `CZ`, `CNZ`, `CP`, `CM`, `CPE`, `CPO`

* Example:

`MVI A, 00H`  
`CZ 2050H    ; Call subroutine at 2050H if Z=1`

---

### **3.3 Return Instructions**

Return instructions are used to **return from a subroutine**.

#### **1\. Unconditional Return**

* **Instruction:** `RET`

* Pops the **return address** from stack and resumes execution.

**Example:**

`RET   ; Return from subroutine`

#### **2\. Conditional Return**

* Return from subroutine **only if a specific condition (flag) is true**.

* **Instructions:** `RC`, `RNC`, `RZ`, `RNZ`, `RP`, `RM`, `RPE`, `RPO`

**Example:**

`MVI A, 00H`  
`RZ   ; Return if Zero flag is set`

---

### **3.4 Restart Instructions (RST)**

* **Purpose:** Call a subroutine located at **fixed memory locations** (0, 8, 10H, ..., 38H).

* **Instruction format:** `RST n` (n = 0 to 7\)

* **Memory locations:** RST0 → 00H, RST1 → 08H, RST2 → 10H, …, RST7 → 38H

* **Mechanism:**

  1. Push **current PC** onto stack

  2. Jump to fixed memory location

**Example:**

`RST 1   ; Call subroutine at 08H`

* **RST instructions are shorter** (1 byte) and faster than CALL.

---

## **4\. Addressing Modes Used in Branch Instructions**

| Instruction Type | Addressing Mode | Example |
| ----- | ----- | ----- |
| JMP, CALL | Direct | `JMP 2050H`, `CALL 3000H` |
| Conditional Jumps/Calls | Direct | `JZ 2050H`, `CZ 2050H` |
| PCHL | Register Indirect | `PCHL` |
| RST | Implied / Fixed | `RST 5` |

---

## **5\. Summary Table of Branch Instructions**

| Instruction | Operation | Type | Condition | Example |
| ----- | ----- | ----- | ----- | ----- |
| JMP addr | Unconditional jump | Jump | — | `JMP 2050H` |
| JC addr | Jump if carry set | Jump | CY=1 | `JC 2050H` |
| JNC addr | Jump if carry not set | Jump | CY=0 | `JNC 2050H` |
| JZ addr | Jump if zero | Jump | Z=1 | `JZ 2050H` |
| JNZ addr | Jump if not zero | Jump | Z=0 | `JNZ 2050H` |
| CALL addr | Call subroutine | Call | — | `CALL 2050H` |
| CC addr | Call if carry | Call | CY=1 | `CC 2050H` |
| RET | Return from subroutine | Return | — | `RET` |
| RC | Return if carry | Return | CY=1 | `RC` |
| RST n | Restart | Restart | — | `RST 2` |
| PCHL | Jump indirect via H-L | Jump | — | `PCHL` |

---

## **6\. Key Points**

1. **Unconditional branches** always change program flow.

2. **Conditional branches** depend on the **status of flags** (Z, CY, S, P).

3. **Call instructions** are used for subroutines; **RET** returns execution to calling point.

4. **RST instructions** are **shortcuts for fixed-address subroutine calls**.

5. Branch instructions **do not alter flags**; they only use flags to decide execution in conditional cases.

