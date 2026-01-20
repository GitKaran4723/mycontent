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

