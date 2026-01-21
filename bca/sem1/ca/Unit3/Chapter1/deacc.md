# **Design of Accumulator Logic** 

---

## **1\. Introduction**

The **Accumulator (AC)** is a **primary register in the CPU** used to **store intermediate results of arithmetic and logic operations**.

* It is **part of the ALU** (Arithmetic Logic Unit).

* AC interacts with other registers like **DR (Data Register)**, **E (Link)**, and the **Control Unit (CU)**.

* It simplifies the **design of ALU and instruction execution**.

---

## **2\. Functions of the Accumulator**

The accumulator is designed to perform the following tasks:

1. **Store intermediate results** of arithmetic operations (ADD, SUB, INC).

2. **Store results of logical operations** (AND, OR, NOT, XOR).

3. **Temporary storage for data transfer** between memory and CPU.

4. **Participate in conditional operations**, e.g., zero-check, overflow detection.

5. Interface with **input/output operations** in I/O instructions.

---

## **3\. Accumulator Register Design**

### **3.1 Basic Components**

| Component | Function |
| ----- | ----- |
| **AC (Accumulator)** | 16-bit register that stores intermediate results |
| **E (Link / Carry bit)** | 1-bit register used for carry/overflow in operations |
| **ALU** | Performs arithmetic/logic operations using AC and DR |
| **Control Lines** | LDAC, CLAC, E (Link) for load/clear/transfer operations |
| **Bus Interface** | Transfers data to/from DR, memory, or input-output registers |

---

### **3.2 Internal Architecture**

The AC logic is designed with **two main parts**:

1. **Register part** – Holds current contents of AC (16 bits).

2. **ALU interface** – Connects AC with DR for arithmetic/logic operations.

**Diagram (Conceptual)**

     `+------------------+`  
      `|       AC         |`  
      `|------------------|`  
      `|  16-bit Register |`  
      `+------------------+`  
            `|   ^`  
   `LDAC ----+   +---- ALU Output`  
   `CLAC --------- Clear Signal`  
            `|`  
            `+--> E (Link / Carry)`

---

### **3.3 Micro-Operations of AC**

The **Accumulator performs micro-operations** as controlled by the **Control Unit**:

| Micro-Operation | Description |
| ----- | ----- |
| **AC ← AC \+ DR** | Add contents of DR to AC; store carry in E |
| **AC ← AC AND DR** | Logical AND operation between AC and DR |
| **AC ← AC OR DR** | Logical OR operation |
| **AC ← AC’** | Complement AC |
| **AC ← AC \+ 1** | Increment AC |
| **AC ← 0** | Clear accumulator |
| **E ← Carry** | Store carry bit from arithmetic operation |
| **AC ← INPR** | Input data from input register |
| **OUTR ← AC** | Send AC content to output register |

---

## **4\. AC and E Interaction (Carry / Link)**

* The **E bit (Link)** stores the **carry-out** from the **most significant bit (MSB)** of AC during arithmetic operations.

* Example: **ADD operation**

`AC = 1111 1111 1111 1111 (65535)`  
`DR = 0000 0000 0000 0001 (1)`  
`Result = 0000 0000 0000 0000 (0)`  
`Carry → E = 1`

* AC stores the **lower 16 bits**, E stores **overflow/carry**.

---

## **5\. Control Signals for Accumulator**

The **Control Unit** uses **specific signals** to operate AC:

| Control Signal | Function |
| ----- | ----- |
| **LDAC** | Load data into AC from DR or memory |
| **CLAC** | Clear AC to zero |
| **E (Link)** | Store carry or transfer link |
| **ADD** | Trigger addition in ALU with AC and DR |
| **AND** | Trigger logical AND operation |
| **COM** | Complement AC |
| **INC** | Increment AC |

---

## **6\. Data Flow in AC Logic**

1. **Data Transfer from Memory to AC (LDA)**

`Memory → DR → AC`

2. **Arithmetic Operation (ADD)**

`DR + AC → AC, carry → E`

3. **Logical Operation (AND)**

`DR AND AC → AC`

4. **Output Operation (OUT)**

`AC → OUTR → Output device`

5. **Increment / Clear Operation**

`AC + 1 → AC`  
`AC ← 0 → AC`

---

## **7\. Timing of AC Operations**

**Example: ADD Operation**

| Time Step | Micro-Operation |
| ----- | ----- |
| T3 | AR ← IR(Address) → Get memory address |
| T4 | DR ← M\[AR\] → Fetch data from memory |
| T5 | AC ← AC \+ DR, E ← Carry → Store result |

**Example: AND Operation**

| Time Step | Micro-Operation |
| ----- | ----- |
| T3 | AR ← IR(Address) |
| T4 | DR ← M\[AR\] |
| T5 | AC ← AC AND DR |

---

## **8\. Role of AC in Instruction Execution**

* **Memory-Reference Instructions:** AC stores operands and results (e.g., ADD, AND, LDA)

* **Register-Reference Instructions:** AC modified directly (e.g., CLA, CMA, INC)

* **I/O Instructions:** AC temporarily stores input data or sends output data

**AC is central to CPU operations**, acting as both **source and destination** for almost all computations.

---

## **9\. Advantages of Accumulator Logic Design**

* Simplifies **ALU design** – only one main operand (AC) used for operations

* Reduces **register complexity**

* Efficient for **fetch-decode-execute cycles**

* Can handle **arithmetic, logical, I/O, and branch operations**

* Supports **overflow detection** via E (Link)

---

## **10\. Summary**

* The **Accumulator (AC)** is a 16-bit register for storing intermediate results.

* Works with **Data Register (DR)**, **E bit**, and **ALU**.

* Executes **arithmetic, logical, increment, clear, complement, and I/O operations**.

* Controlled by **control signals from the Control Unit**.

* Central to **instruction execution in the Basic Computer**.

