## **1\. Combinational Circuits**

### **Definition**

A **combinational circuit** is a digital circuit whose **output depends only on the present inputs**, not on any previous inputs or memory.

### **Characteristics**

* No memory elements (no flip-flops or latches)

* Output changes immediately when input changes

* Uses logic gates like AND, OR, NOT, XOR, etc.

### **Examples**

* Half Adder

* Full Adder

* Multiplexer

* Demultiplexer

* Encoder and Decoder

---

## **2\. Half Adder**

### **Definition**

A **Half Adder** is a combinational circuit that **adds two single-bit binary numbers** and produces:

* **Sum (S)**

* **Carry (C)**

It is called *half* adder because it **does not consider carry input from a previous stage**.

### **Inputs and Outputs**

* Inputs:

  * A (first bit)

  * B (second bit)

* Outputs:

  * Sum (S)

  * Carry (C)

---

### **Truth Table of Half Adder**

A   B   SUM(S)   CARRY(C)
0   0     0         0
0   1     1         0
1   0     1         0
1   1     0         1


---

### **Logic Expressions**

* **Sum:**  
   S=A⊕BS = A \\oplus BS=A⊕B  
* **Carry:**  
   C=A⋅BC = A \\cdot BC=A⋅B

---

### **Logic Diagram**

* Sum is implemented using an **XOR gate**

* Carry is implemented using an **AND gate**
![Half Adder Logic Diagram](https://www.electronics-tutorial.net/wp-content/uploads/2015/09/HA.png)

---

### **Limitation of Half Adder**

* Cannot add numbers when a **carry from previous addition** is present

---

## **3\. Full Adder**

### **Definition**

A **Full Adder** is a combinational circuit that **adds three single-bit binary numbers**:

* Two input bits

* One carry input from previous stage

### **Inputs and Outputs**

* Inputs:

  * A

  * B

  * Carry-in (Cin)

* Outputs:

  * Sum (S)

  * Carry-out (Cout)

---

### **Truth Table of Full Adder**

| A | B | Cin | Sum (S) | Carry (Cout) |
| ----- | ----- | ----- | ----- | ----- |
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 0 |
| 0 | 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 | 1 |

---

### **Logic Expressions**

**Sum:**
S = A ⊕ B ⊕ Cin

**Carry:**
Cout = AB + BCin + ACin



![Full Adder Diagram](https://www.poriyaan.in/media/imgPori/images51/Qvr64Nz.jpg)
---

### **Full Adder Using Half Adders**

A full adder can be constructed using:

* **Two Half Adders**

* **One OR gate**

#### **Working:**

1. First Half Adder adds A and B

2. Second Half Adder adds Sum₁ and Cin

3. OR gate combines both carry outputs

---

## **4\. Comparison: Half Adder vs Full Adder**

| Feature | Half Adder | Full Adder |
| ----- | ----- | ----- |
| Inputs | 2 | 3 |
| Carry Input | No | Yes |
| Outputs | Sum, Carry | Sum, Carry |
| Used in Multi-bit Addition | No | Yes |

---

## **5\. Applications**

* Arithmetic Logic Unit (ALU)

* Digital calculators

* Processors

* Binary addition circuits

