## **1\. What is a Flip-Flop?**

A **Flip-Flop** is a **bistable multivibrator**, which is an electronic circuit that has **two stable states**.

* It can **store one bit of data (0 or 1\)**.

* Flip-flops are the **basic building blocks of sequential logic circuits** like memory, registers, and counters.

**Types of Flip-Flops**

1. SR Flip-Flop (Set-Reset)

2. D Flip-Flop (Data or Delay)

3. JK Flip-Flop

4. T Flip-Flop (Toggle)

**Key Features of a Flip-Flop**

1. **Two stable states** – can store either 0 or 1\.

2. **Inputs** – control signals that determine whether to set, reset, or toggle the state.

3. **Outputs** – Q (main output) and Q' (complement output).

4. **Memory element** – retains the state until changed by an input.  
   

---

## **2\. SR Flip-Flop (Set-Reset Flip-Flop)**

The **SR Flip-Flop** is the simplest type of flip-flop. It is also called **SR latch**.

### **Definition**

An **SR Flip-Flop** is a bistable device with **two inputs: S (Set) and R (Reset)** and **two outputs: Q and Q’**.

* **Set (S)** → Makes Q = 1

* **Reset (R)** → Makes Q = 0

* **Q** → Current state

* **Q’** → Complement of Q (always opposite of Q)

![Diagram of SR-Flipflop](https://media.geeksforgeeks.org/wp-content/uploads/20240513153126/Untitled-Diagram---2024-05-13T153118202.webp)

---

### **3\. Inputs and Outputs**

| Symbol | Meaning |
| ----- | ----- |
| S | Set input |
| R | Reset input |
| Q | Output (current state) |
| Q' | Complement of Q |

---

### **4\. Operation of SR Flip-Flop**

| S | R | Q (Next State) | Q’ (Next State) | Description |
| ----- | ----- | ----- | ----- | ----- |
| 0 | 0 | Q (No change) | Q’ (No change) | Memory state (retains previous value) |
| 0 | 1 | 0 | 1 | Reset: Q is cleared to 0 |
| 1 | 0 | 1 | 0 | Set: Q is set to 1 |
| 1 | 1 | Invalid | Invalid | Forbidden state (not allowed) |

**Explanation:**

1. **S=0, R=0:** No change in state; the flip-flop “remembers” its previous value.

2. **S=1, R=0:** Sets Q=1, Q’=0.

3. **S=0, R=1:** Resets Q=0, Q’=1.

4. **S=1, R=1:** S=1, R=1: Both outputs would become 0 (invalid), which is undefined behavior.

**Truth Table of SR Flip-Flop:**

![Truth Table Of SR Flipflop](https://media.geeksforgeeks.org/wp-content/uploads/20230602210012/sr6.png)











**Functional Table of SR Flip-flop:**


![Function Table of SR Flipflop](https://media.geeksforgeeks.org/wp-content/uploads/20230602210243/sr8.png)

---

### **5\. Implementation**

* **Using NOR gates:** Active-high logic.

* **Using NAND gates:** Active-low logic.

* Can be implemented with **cross-coupled gates** so that the output feeds back to inputs to maintain memory.

---

### **6\. Key Points / Properties**

1. **Bistable device** – holds one bit of data.

2. **Two outputs** – Q and Q’ (always complementary).

3. **Memory capability** – retains previous state when S=R=0.

4. **Forbidden state** – S=R=1 (for NOR-based) or S=R=0 (for NAND-based).

5. **Basis for other flip-flops** – JK, D, and T flip-flops are derived from SR Flip-Flop.

---

### **7\. Applications of SR Flip-Flop**

* Temporary storage (1-bit memory)

* Control circuits (e.g., turning devices on/off)

* Part of sequential circuits like **counters, registers, and shift registers**


## **D Flip-Flop (Data or Delay Flip-Flop)**

### **1\. Definition**

A **D Flip-Flop** is a **bistable memory device** that stores the value of the **data input (D)** at a **specific edge of the clock signal** (rising or falling).

* Called a **Delay Flip-Flop** because the output **Q follows the input D only at the clock edge**.

* Derived from the **SR Flip-Flop**, but with **no invalid state**.

---

### **2\. Inputs and Outputs**

| Symbol | Meaning |
| ----- | ----- |
| D | Data input (value to be stored) |
| CLK | Clock input (controls when D is stored) |
| Q | Output (stored data) |
| Q' | Complement output (opposite of Q) |

---

### **3\. Working Principle**

* The D Flip-Flop **samples the input D** at the **clock edge** and stores it.

* **Output Q and Q’** change **only at the triggering clock edge**.

* **Outputs remain constant** between clock edges, regardless of changes in D.

**D Flip-Flop Image:**

![D Flip-Flop Image](https://media.geeksforgeeks.org/wp-content/uploads/20250407160315528101/22.webp)









**Truth Table of D Flip-Flop:**

![D Flip-Flop Truth Table](https://media.geeksforgeeks.org/wp-content/uploads/20230526160600/hioja.png)







---

### **4\. Truth Table**

| D | Q (Previous) | Q' (Current) | Description |
| ----- | ----- | ----- | ----- |
| 0 | 1 | 0 | Stores 0 at clock edge |
| 1 | 1 | 1 | Stores 1 at clock edge |
| 0 | 0 | 0 | Stores 0 at clock edge |
| 1 | 0 | 1 | Stores 1 at clock edge |

✅ **Explanation:**

* Q = value before clock edge

* Q’ = value after clock edge

* D Flip-Flop **updates Q’ = D** at the clock edge

---

### **5\. Characteristic Equation**

Q′=DQ' = DQ′=D

* Output **directly follows input D** at the clock edge.

---

### **6\. Implementation**

#### **A. Using SR Flip-Flop**

* Connect **D → S input**

* Connect **NOT D → R input**

* Eliminates forbidden state of SR flip-flop (S=R=1)

#### **B. Using Logic Gates**

* Built with **NAND or NOR gates** and **edge-triggering circuitry**

* Modern ICs often use **master-slave D flip-flops** for edge-triggered operation

---

### **7\. Edge-Triggering**

* Responds only to **rising edge (↑) or falling edge (↓)** of the clock

* Prevents glitches and ensures **precise timing** in sequential circuits

---

### **8\. Applications**

1. **Registers** – storing multi-bit data

2. **Shift registers** – serial-to-parallel and parallel-to-serial conversion

3. **Counters** – sequential counting circuits

4. **Memory cells** – in RAM or flip-flop-based storage

5. **Debouncing switches** – capturing stable input states

6. **Synchronization circuits** – aligning asynchronous signals to a clock

---

### **9\. Key Points / Summary**

* Stores **1-bit data** at **clock edge**

* **Avoids invalid states** unlike SR flip-flop

* Can be implemented using **SR flip-flop with inverter**, **logic gates**, or **ICs**

* Widely used in **digital sequential circuits** for memory, data storage, and timing control

* **Characteristic equation:** `Q' = D`

## **JK Flip-Flop**

### **1\. Definition**

A **JK Flip-Flop** is a **bistable memory device** that overcomes the **invalid state of an SR flip-flop**.

* Inputs: **J (Set), K (Reset), CLK**

* Output **Q** changes based on **J and K** at the **clock edge**.

* When **J = K = 1**, the output **toggles** (changes to its complement).

It is widely used in **counters and sequential circuits** because of its toggle capability.

---

### **2\. Inputs and Outputs**

| Symbol | Meaning |
| ----- | ----- |
| J | Set input |
| K | Reset input |
| CLK | Clock input |
| Q | Current output |
| Q’ | Complement output |

---

### **3\. Working Principle**

* **J = 0, K = 0** → No change (memory)

* **J = 0, K = 1** → Reset Q = 0

* **J = 1, K = 0** → Set Q = 1

* **J = 1, K = 1** → Toggle Q (Q → Q’)

Unlike SR flip-flop, **J = K = 1 is a valid state**.


**JK Flip-Flop Diagram and Truth Table:**
![JK Flip-Flop Diagram](https://media.geeksforgeeks.org/wp-content/uploads/20240912114055/JK-Flip-Flop.png)



---

### **4\. Truth Table**

| J | K | Q (Previous) | Q’ (Current) | Description |
| ----- | ----- | ----- | ----- | ----- |
| 0 | 0 | 0 | 0 | No change |
| 0 | 0 | 1 | 1 | No change |
| 0 | 1 | 0 | 0 | Reset Q = 0 |
| 0 | 1 | 1 | 0 | Reset Q = 0 |
| 1 | 0 | 0 | 1 | Set Q = 1 |
| 1 | 0 | 1 | 1 | Set Q = 1 |
| 1 | 1 | 0 | 1 | Toggle Q |
| 1 | 1 | 1 | 0 | Toggle Q |

---

### **5\. Characteristic Equation**

Q′=JQ‾+K‾QQ' = J\\overline{Q} \+ \\overline{K}QQ′=JQ​+KQ

* If J = K = 1 → Q' = Q̄ (toggle)

* If J = 0, K = 0 → Q’ = Q (no change)

---

### **6\. Implementation**

* Can be implemented from an **SR flip-flop** using additional logic to handle **J = K = 1 toggle**

* Often available as **IC JK flip-flops** (like 7476\)

---

### **7\. Edge-Triggering**

* JK Flip-Flops can be **level-triggered or edge-triggered**

* Edge-triggered versions are widely used to **prevent race conditions**

---

### **8\. Applications**

1. **Counters** – most common use due to toggle function

2. **Shift registers**

3. **Frequency dividers** – toggling output halves frequency

4. **Memory storage** – stores single-bit data

5. **Control circuits** – sequential operations

---

### **9\. Key Points**

* Solves **invalid state problem** of SR flip-flop

* **J = K = 1** → toggles output

* Widely used in **sequential logic design**

* Characteristic equation: `Q' = JQ’ + K’Q`

## **T Flip-Flop (Toggle Flip-Flop)**

### **1\. Definition**

A **T Flip-Flop** (Toggle Flip-Flop) is a **bistable memory device** that **toggles its output** on each clock pulse when the **T input is 1**.

* It is essentially a **JK Flip-Flop with J = K = T**.

* When **T = 0**, the output **remains unchanged**.

* It is widely used in **counters and frequency dividers** because of its toggling behavior.

**Block Diagram of T Flip-Flop:**


![T Flip-Flop](https://media.geeksforgeeks.org/wp-content/uploads/20250407130300749137/t3.png)

---

### **2\. Inputs and Outputs**

| Symbol | Meaning |
| ----- | ----- |
| T | Toggle input |
| CLK | Clock input |
| Q | Current output |
| Q’ | Complement output |

---

### **3\. Working Principle**

* **T = 0** → No change (output remains the same)

* **T = 1** → Output **toggles** (Q → Q’) on each clock edge

✅ Key Point: T Flip-Flop is **edge-triggered**, so output changes only **at clock edges**.


**T Flip-Flop Truth Table:**

![T Flip-Flop Diagram](https://media.geeksforgeeks.org/wp-content/uploads/20250407142240378264/t2.jpg)

---

### **4\. Truth Table**

| T | Q (Previous) | Q’ (Current) | Description |
| ----- | ----- | ----- | ----- |
| 0 | 0 | 0 | No change |
| 0 | 1 | 1 | No change |
| 1 | 0 | 1 | Toggle (0 → 1\) |
| 1 | 1 | 0 | Toggle (1 → 0\) |

---

### **5\. Characteristic Equation**

Q′=T⊕QQ' = T \\oplus QQ′=T⊕Q

* Where `⊕` denotes XOR operation

* Shows that **if T = 1, Q toggles**; if T = 0, **Q remains unchanged**

---

### **6\. Implementation**

#### **A. Using JK Flip-Flop**

* Connect **J = K = T**

* This converts JK Flip-Flop into a T Flip-Flop

#### **B. Using D Flip-Flop**

* Connect **D = Q’ XOR T**

* Ensures **toggle behavior** at each clock pulse

---

### **7\. Edge-Triggering**

* T Flip-Flops are **usually edge-triggered**

* Ensures output **changes only on the clock edge**, avoiding glitches

---

### **8\. Applications**

1. **Binary Counters** – T Flip-Flops are the basic building blocks

2. **Frequency Dividers** – toggling output halves the clock frequency

3. **Shift Registers** – stores and shifts data

4. **Control Circuits** – sequential operations in digital systems

5. **Memory Storage** – stores single-bit data

---

### **9\. Key Points**

* T Flip-Flop **toggles output** when T = 1

* T = 0 → output remains the same

* Can be derived from **JK Flip-Flop (J = K = T)**

* Commonly used in **counters and frequency dividers**

* **Characteristic equation:** `Q' = T ⊕ Q`

---

✅ **Summary of T Flip-Flop Behavior**

* **T = 0:** Output unchanged

* **T = 1:** Output toggles

* Very simple but **fundamental for sequential logic design**

