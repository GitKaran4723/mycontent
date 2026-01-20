## **Octal-to-Binary Encoder** 

---

### **1\. What is an Encoder?**

An **encoder** is a **combinational logic circuit** that:

* Converts **active input lines** into a **binary code output**.

* For **2ⁿ input lines**, there are **n output lines**.

* Usually, only **one input is HIGH at a time**; if multiple inputs are active, a **priority encoder** is needed.

**Purpose:**

* Reduce the number of output lines.

* Encode signals from multiple inputs into binary form.

---

### **2\. Octal-to-Binary Encoder – Definition**

An **Octal-to-Binary Encoder** is a circuit that:

* Has **8 inputs**: D₀, D₁, D₂, …, D₇ (representing octal numbers 0–7).

* Has **3 outputs**: A₂, A₁, A₀ (binary code).

**Operation:**

* When one input is HIGH, the output shows the **binary equivalent** of that input number.

* Example:

  * D0 = 1 → Output = 000

  * D1 = 1 → Output = 001

  * D7 = 1 → Output = 111

---

### **3\. Truth Table**

Here’s the **Octal-to-Binary Encoder truth table**:

<pre>
| D0 | D1 | D2 | D3 | D4 | D5 | D6 | D7 | A2 | A1 | A0 |
|----|----|----|----|----|----|----|----|----|----|----|
|  1 |  0 |  0 |  0 |  0 |  0 |  0 |  0 |  0 |  0 |  0 |
|  0 |  1 |  0 |  0 |  0 |  0 |  0 |  0 |  0 |  0 |  1 |
|  0 |  0 |  1 |  0 |  0 |  0 |  0 |  0 |  0 |  1 |  0 |
|  0 |  0 |  0 |  1 |  0 |  0 |  0 |  0 |  0 |  1 |  1 |
|  0 |  0 |  0 |  0 |  1 |  0 |  0 |  0 |  1 |  0 |  0 |
|  0 |  0 |  0 |  0 |  0 |  1 |  0 |  0 |  1 |  0 |  1 |
|  0 |  0 |  0 |  0 |  0 |  0 |  1 |  0 |  1 |  1 |  0 |
|  0 |  0 |  0 |  0 |  0 |  0 |  0 |  1 |  1 |  1 |  1 |
</pre>


**Observation:**

* Only **one input is HIGH** at a time.

* Output lines **A₂, A₁, A₀** give the **binary equivalent** of the active input.

---

### **4\. Boolean Expressions**

The outputs can be expressed using OR operations:

* **A0 = D1 \+ D3 \+ D5 \+ D7**

* **A1 = D2 \+ D3 \+ D6 \+ D7**

* **A2 = D4 \+ D5 \+ D6 \+ D7**

"+" represents **logical OR**.

---

### **5\. Logic Diagram**

* Each output is formed using **OR gates**.

* Inputs are connected to OR gates according to the Boolean expressions above.

* Example:

  * A0 = OR(D1, D3, D5, D7)

  * A1 = OR(D2, D3, D6, D7)

  * A2 = OR(D4, D5, D6, D7)

*(You can insert a diagram here.)*

---

### **6\. Applications**

1. **Keyboard Encoding:** Converts key presses into binary code for microprocessors.

2. **Data Compression:** Reduces the number of output lines.

3. **Digital Systems:** Used in memory address generation or data selection.

4. **Priority Encoders:** For multiple simultaneous inputs, a priority encoder determines the highest-priority input.

---

### **7\. Advantages**

* Reduces the number of output lines (8 → 3).

* Simple combinational design using OR gates.

* Easily extendable for larger encoders (16-to-4, 32-to-5).

---

### **8\. Summary**

* An **Octal-to-Binary Encoder** converts **8 input lines into 3 binary outputs**.

* Only one input should be HIGH at a time.

* Outputs give the **binary equivalent** of the active input.

* Implemented using **OR gates**.

* Widely used in **keyboards, digital systems, and memory interfacing**.

