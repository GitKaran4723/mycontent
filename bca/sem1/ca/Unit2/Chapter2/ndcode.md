## **NAND Gate Decoder **

---

### **1\. What is a Decoder? (Quick Recap)**

A **decoder** is a **combinational digital circuit** that converts **binary input data into a unique output line**.

* For **n input lines**, it produces **2ⁿ output lines**.

* Only **one output is HIGH (1)** at a time, while all others remain LOW.

* Example: 2-to-4, 3-to-8 line decoders.

---

### **2\. NAND Gate Decoder – Definition**

A **NAND gate decoder** is a decoder that uses **NAND gates instead of AND gates** to generate the outputs.

* The outputs of a NAND decoder are **logic LOW (0) for the selected input combination**, while all other outputs are **logic HIGH (1)**.

* This is the **active LOW** version of a standard AND/OR decoder.

**Key idea:**

* Standard decoders use **AND gates** → active HIGH outputs.

* NAND decoders use **NAND gates** → active LOW outputs.

---

### **3\. Why Use NAND Gates?**

1. **NAND gates are universal gates** – can implement any logic.

2. They are cheaper and faster in integrated circuits.

3. Reduce hardware complexity for large decoders.

4. Provides **active LOW outputs**, useful in certain circuits (e.g., memory chip selection).

---

### **4\. Operation of NAND Decoder**

**Example: 2-to-4 NAND decoder**

* Inputs: A, B

* Outputs: Y₀, Y₁, Y₂, Y₃

**Truth table for 2-to-4 NAND decoder:**

<pre>
| A | B | Y0 | Y1 | Y2 | Y3 |
|---|---|----|----|----|----|
| 0 | 0 | 0  | 1  | 1  | 1  |
| 0 | 1 | 1  | 0  | 1  | 1  |
| 1 | 0 | 1  | 1  | 0  | 1  |
| 1 | 1 | 1  | 1  | 1  | 0  |
</pre>


**Observation:**

* The selected output becomes **LOW (0)**.

* All non-selected outputs remain **HIGH (1)**.

---

### **5\. Boolean Expressions Using NAND Gates**

For a **2-to-4 NAND decoder**, the outputs are:

* Y₀ = (A \+ B)' → NAND of A' AND B'

* Y₁ = (A \+ B')' → NAND of A' AND B

* Y₂ = (A' \+ B)' → NAND of A AND B'

* Y₃ = (A \+ B)' → NAND of A AND B

**Note:** Using De Morgan’s theorem, AND \+ NOT can be replaced with NAND.

---

### **6\. Logic Diagram**

* Each output is implemented using **NAND gates only**.

* Inputs are **inverted as needed** using NAND gates (universal property).

* Active output goes **LOW**, inactive outputs stay **HIGH**.


---

### **7\. Truth Table of 3-to-8 NAND Decoder**

<pre>
| A | B | C | Y0 | Y1 | Y2 | Y3 | Y4 | Y5 | Y6 | Y7 |
|---|---|---|----|----|----|----|----|----|----|----|
| 0 | 0 | 0 | 0  | 1  | 1  | 1  | 1  | 1  | 1  | 1  |
| 0 | 0 | 1 | 1  | 0  | 1  | 1  | 1  | 1  | 1  | 1  |
| 0 | 1 | 0 | 1  | 1  | 0  | 1  | 1  | 1  | 1  | 1  |
| 0 | 1 | 1 | 1  | 1  | 1  | 0  | 1  | 1  | 1  | 1  |
| 1 | 0 | 0 | 1  | 1  | 1  | 1  | 0  | 1  | 1  | 1  |
| 1 | 0 | 1 | 1  | 1  | 1  | 1  | 1  | 0  | 1  | 1  |
| 1 | 1 | 0 | 1  | 1  | 1  | 1  | 1  | 1  | 0  | 1  |
| 1 | 1 | 1 | 1  | 1  | 1  | 1  | 1  | 1  | 1  | 0  |
</pre>


**Observation:**

* Only one output is **LOW (0)** for each input combination.

* Useful for **active LOW memory selection**.

---

### **8\. Applications of NAND Decoder**

1. **Memory chip selection:** Active LOW enables.

2. **Demultiplexing signals** in digital systems.

3. **Address decoding** in computers.

4. **Generating control signals** in microprocessors.

---

### **9\. Advantages**

* Simple design using **universal NAND gates**.

* Active LOW output is suitable for many digital ICs.

* Can be **cascaded** to form larger decoders.

---

### **10\. Summary**

* A **NAND gate decoder** is a **combinational circuit** with **active LOW outputs**.

* Only the selected output goes **LOW**, others stay HIGH.

* It is implemented **entirely using NAND gates**.

* Useful in **memory selection, demultiplexing, and control circuits**.

