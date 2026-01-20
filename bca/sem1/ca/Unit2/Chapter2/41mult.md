## **4-to-1 Line Multiplexer (MUX) – Full Explanation**

---

### **1\. What is a Multiplexer?**

A **Multiplexer (MUX)** is a **combinational circuit** that:

* Selects **one input** from multiple input lines and forwards it to a **single output line**.

* Acts like a **digital “selector switch”**.

* Reduces the number of data lines needed in digital systems.

**Key Terms:**

* **Inputs (Data lines)**: Lines carrying the information (e.g., D0, D1, D2, D3).

* **Select Lines**: Control lines that choose which input to send to output (e.g., S0, S1).

* **Output**: Single line carrying the selected input.

**Basic Idea:**

* The select lines act like the address of the input line that needs to be transmitted to the output.

---

### **2\. 4-to-1 Multiplexer Definition**

A **4-to-1 multiplexer** has:

* **4 data inputs**: D0, D1, D2, D3

* **2 select lines**: S1 and S0

* **1 output**: Y

**Operation:**

* The **2-bit select input** determines which of the 4 inputs is connected to the output.

* Only the **selected input** is transferred to the output; others are ignored.

---

### **3\. Truth Table**

| S1 | S0 | Y |
| ----- | ----- | ----- |
| 0 | 0 | D0 |
| 0 | 1 | D1 |
| 1 | 0 | D2 |
| 1 | 1 | D3 |

**Observation:**

* The output **Y = selected input line**.

* The select lines act as a **binary address** for the input.

---

### **4\. Boolean Expression**

The output can be expressed as:

Y=S1‾ S0‾D0+S1‾S0D1+S1S0‾D2+S1S0D3Y = \\overline{S1}\\,\\overline{S0} D0 \+ \\overline{S1} S0 D1 \+ S1 \\overline{S0} D2 \+ S1 S0 D3Y=S1S0D0+S1S0D1+S1S0D2+S1S0D3

Where:

* S1‾\\overline{S1}S1 = NOT of S1

* S0‾\\overline{S0}S0 = NOT of S0

* "+" = OR operation

* Multiplication = AND operation

**Explanation:**

* Only the term corresponding to the selected input is **active**; others are 0\.

---

### **5\. Logic Diagram**

* Each input line is ANDed with the combination of select lines that **select that input**.

* The outputs of all AND gates are ORed to produce the final output Y.

**Structure:**

* **4 AND gates** → each for D0–D3

* **2 NOT gates** → to generate S1‾\\overline{S1}S1 and S0‾\\overline{S0}S0

* **1 OR gate** → combines the outputs of all AND gates to produce Y

---

### **6\. Working Example**

Suppose:

* D0 = 1, D1 = 0, D2 = 1, D3 = 0

* S1 = 1, S0 = 0

Then:

* Output Y = S1 S0 D3 \+ … (evaluate Boolean)

* Only D2 is selected because S1S0 = 10 → Y = D2 = 1

---

### **7\. Applications of 4-to-1 MUX**

1. **Data Selection:** Choosing one of several data sources to send to a single line.

2. **Arithmetic Operations:** Used in ALUs to select different arithmetic operations.

3. **Signal Routing:** In communication systems to route signals efficiently.

4. **Memory Selection:** Selecting memory data or I/O ports in microprocessors.

---

### **8\. Advantages**

* Reduces the number of required data lines.

* Simple combinational logic implementation.

* Can be easily expanded (e.g., 8-to-1, 16-to-1 MUX).

---

### **9\. Summary**

* **4-to-1 MUX**: 4 inputs, 2 select lines, 1 output

* **Output = selected input** based on select lines

* Boolean expression: Y=S1‾S0‾D0+S1‾S0D1+S1S0‾D2+S1S0D3Y = \\overline{S1}\\overline{S0}D0 \+ \\overline{S1}S0D1 \+ S1\\overline{S0}D2 \+ S1S0D3Y=S1S0D0+S1S0D1+S1S0D2+S1S0D3

* Used for **data selection, signal routing, memory interfacing, and ALU operations**

