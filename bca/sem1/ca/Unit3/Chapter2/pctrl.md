# **Program Control Instructions** 

---

## **1\. Introduction**

**Program Control Instructions** are used to **change the normal sequential flow of program execution**.

* Normally, instructions are executed **one after another** (sequentially).

* Program control instructions allow:

  1. **Branching:** Jump to another instruction

  2. **Conditional execution:** Execute based on a condition

  3. **Subroutine handling:** Call and return from functions

  4. **Halting execution:** Stop the program

Without program control instructions, a CPU **cannot make decisions, loop, or call subroutines**, which are essential for real programs.

---

## **2\. Types of Program Control Instructions**

Program control instructions are broadly classified into **three categories**:

1. **Unconditional Branch / Jump Instructions**

2. **Conditional Branch / Skip Instructions**

3. **Subroutine Call and Return Instructions**

---

### **2.1 Unconditional Branch / Jump**

* These instructions **change the program counter (PC)** to a new address **without any condition**.

* Execution **jumps directly** to the specified instruction.

**Examples in Basic Computer (Morris Mano):**

| Instruction | Operation | Description |
| ----- | ----- | ----- |
| **BUN Address** | PC ← Address | Branch unconditionally to Address |
| **JMP Address** | PC ← Address | Jump to memory location |

**Flow:**

`Next instruction → PC is replaced → Execution continues at new address`

**Use:** Loops, program branching, unconditional jumps.

---

### **2.2 Conditional Branch / Skip Instructions**

* These instructions **execute the branch or skip only if a specific condition is true**.

* Conditions usually involve **flags or accumulator content**.

**Examples in Basic Computer:**

| Instruction | Condition | Description |
| ----- | ----- | ----- |
| **BSA Address** | Always | Branch to subroutine (stores return address) |
| **SZA** | AC = 0 | Skip next instruction if AC is zero |
| **SNA** | AC ≠ 0 | Skip next instruction if AC is not zero |
| **SZE** | E = 0 | Skip if E (carry/overflow) is 0 |
| **SPO** | AC positive | Skip if AC is positive |

**Mechanism:**

* CPU checks the condition **flag or register content**.

* If true → **PC modified** → execution continues from new instruction.

* If false → **next sequential instruction** executed.

**Use:** Conditional execution, loops, decision-making.

---

### **2.3 Subroutine Call and Return**

Subroutines (functions/procedures) require instructions to:

1. **Call the subroutine**

2. **Return after execution**

**Example Instructions:**

| Instruction | Operation | Description |
| ----- | ----- | ----- |
| **CALL / BSA Address** | Push return address → PC ← Address | Jump to subroutine and save return address |
| **RET / RETURN** | Pop return address → PC ← Address | Return to instruction after subroutine call |

**Flow:**

`Main Program`  
   `CALL Subroutine`  
   `... execution jumps ...`  
   `Subroutine executes`  
   `RETURN`  
`Back to Main Program`

**Importance:**

* Supports **modular programming**

* Allows **code reuse**

* Handles **recursive function calls**

---

### **2.4 Halt / Stop Instruction**

* **HLT (Halt)** stops program execution.

* Used to **end the program** or **stop CPU operations**.

**Example:**

`HLT  // Stop execution`

* CPU **enters idle state** until reset or interrupt occurs.

---

## **3\. Role in CPU Operation**

Program control instructions allow a CPU to:

1. **Make decisions:** Conditional instructions implement if-else logic.

2. **Repeat operations:** Loops are possible using branch instructions.

3. **Call and return from functions:** Enables modular programming.

4. **Stop execution:** Terminate programs safely.

**Without program control instructions**, a computer would **only execute sequential instructions**, unable to respond dynamically.

---

## **4\. Example Program Using Program Control Instructions**

**Problem:** Add numbers from memory locations 2000 to 2005 and store result at 3000

`ORG 1000`  
`LDA 2000      ; Load first number`  
`ADD 2001      ; Add second number`  
`ADD 2002      ; Add third number`  
`ADD 2003      ; Add fourth number`  
`ADD 2004      ; Add fifth number`  
`ADD 2005      ; Add sixth number`  
`STA 3000      ; Store result`  
`HLT           ; Stop program`

* **Sequential execution:** Without jumps, it runs sequentially

* **With loops (using conditional/unconditional branch):** Program can handle **any number of elements** dynamically

---

## **5\. Summary of Program Control Instructions**

| Type | Purpose | Examples |
| ----- | ----- | ----- |
| **Unconditional Branch / Jump** | Jump to another instruction unconditionally | BUN, JMP |
| **Conditional Branch / Skip** | Jump or skip based on condition | SZA, SNA, SZE, SPO |
| **Subroutine Call / Return** | Call functions and return | CALL, BSA, RET |
| **Halt / Stop** | Stop CPU execution | HLT |

**Key Point:** Program control instructions **change the flow of execution**, enabling loops, decisions, subroutines, and program termination.

