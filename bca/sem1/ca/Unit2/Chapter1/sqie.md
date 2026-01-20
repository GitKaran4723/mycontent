## **Sequential Circuits and Flip-Flop Input Equations**

### **1\. Sequential Circuits Overview**

* A **sequential circuit** is a circuit whose **output depends not only on the current inputs** but also on **past inputs** (history).

* Unlike **combinational circuits**, which only depend on current inputs, sequential circuits **have memory**.

**Key components:**

* **Flip-Flops** – store binary data (1-bit memory element)

* **Logic gates** – determine next state based on current inputs and stored values

---

### **2\. Flip-Flop Input Equations**

* **Input equations** are **Boolean expressions** used to determine **what to apply at the flip-flop inputs** to get the desired **next state (Q\_next)**.

* They are derived from the **State Transition Table** or **Excitation Table** of the flip-flop.

**Steps to get flip-flop input equations:**

1. **Identify the flip-flop type**

   * SR, JK, D, or T

   * Each type has a **characteristic equation** and **excitation table**

2. **Determine the present state (Q) and desired next state (Q\_next)**

3. **Use the flip-flop’s excitation table** to find what input values will cause the transition

   * **D Flip-Flop:** D = Q\_next

   * **T Flip-Flop:** T = Q ⊕ Q\_next

   * **JK Flip-Flop:** J = Q\_next • Q', K = Q' • Q\_next

4. **Simplify the input equations using Boolean algebra**

---

### **3\. Flip-Flop Excitation Tables**

These tables show the **required input values** for a flip-flop to achieve a desired **next state**.

#### **A. D Flip-Flop Excitation Table**

<pre>
| Q (Present) | Q_next | D (Input) |
|-------------|--------|-----------|
| 0           | 0      | 0         |
| 0           | 1      | 1         |
| 1           | 0      | 0         |
| 1           | 1      | 1         |
</pre>


**Observation:** D = Q\_next

---

#### **B. T Flip-Flop Excitation Table**

| Q (Present) | Q\_next | T (Input) |
| ----- | ----- | ----- |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

**Observation:** T = Q ⊕ Q\_next

---

#### **C. JK Flip-Flop Excitation Table**

| Q (Present) | Q\_next | J | K |
| ----- | ----- | ----- | ----- |
| 0 | 0 | 0 | X |
| 0 | 1 | 1 | X |
| 1 | 0 | X | 1 |
| 1 | 1 | X | 0 |

(X = don't care)

---

### **4\. Using Input Equations**

* Once you have the **next state** from the **state table**, you plug it into the **excitation table** of the chosen flip-flop.

* This gives the **flip-flop input equations**, which are then implemented with **logic gates**.

**Example (D Flip-Flop):**

If your **next state function** is:

Qnext=A⋅B+C‾Q\_{next} = A \\cdot B \+ \\overline{C}Qnext​=A⋅B+C

Then the **D input equation** for a D flip-flop is:

D=Qnext=A⋅B+C‾D = Q\_{next} = A \\cdot B \+ \\overline{C}D=Qnext​=A⋅B+C

* Connect this Boolean function to the **D input** of the flip-flop.

---

### **5\. Summary**

* **Flip-Flop Input Equations**: Determine what value goes into the flip-flop to achieve the **desired next state**.

* Derived using:

  1. **State table / transition table**

  2. **Excitation table of flip-flop**

  3. **Boolean simplification**

* **Purpose:** Enables the sequential circuit to **transition between states correctly**.

