# **UNIVERSAL GATES** 

---

## **1\. What are Universal Gates?**

A **universal gate** is a **logic gate that can be used to implement any Boolean function**.  
 Using **only one type of universal gate**, you can create **all other basic logic gates** (AND, OR, NOT) and hence any digital circuit.

There are **two universal gates**:

1. **NAND Gate**

2. **NOR Gate**

---

## **2\. NAND Gate as a Universal Gate**

---

### **2.1 Definition**

A **NAND gate** is a combination of an **AND gate followed by a NOT gate**.  
 Its output is **0 only when all inputs are 1**; otherwise, the output is 1\.

### **2.2 Boolean Expression**

Y = NOT (A \* B)  
 or  
 Y = (A \* B)’

### **2.3 Truth Table**

<pre>
A   B   Y
0   0   1
0   1   1
1   0   1
1   1   0
</pre>


### **2.4 Realizing Other Gates Using NAND**

* **NOT Gate using NAND**  
   Connect both inputs of NAND to the same input:  
   Y = NOT (A \* A) = NOT A

* **AND Gate using NAND**  
   Y = NOT (A NAND B) = A \* B

* **OR Gate using NAND (via De Morgan’s Theorem)**  
   Y = (NOT A) NAND (NOT B) = A \+ B

### **2.5 Applications of NAND Gate**

* Digital IC design

* Memory circuits

* Processor circuits

* Implementing any combinational logic

---

## **3\. NOR Gate as a Universal Gate**

---

### **3.1 Definition**

A **NOR gate** is a combination of an **OR gate followed by a NOT gate**.  
 Its output is **1 only when all inputs are 0**; otherwise, the output is 0\.

### **3.2 Boolean Expression**

Y = NOT (A \+ B)  
 or  
 Y = (A \+ B)’

### **3.3 Truth Table**

<pre>
A   B   Y
0   0   1
0   1   0
1   0   0
1   1   0
</pre>


### **3.4 Realizing Other Gates Using NOR**

* **NOT Gate using NOR**  
   Connect both inputs of NOR to the same input:  
   Y = NOT (A \+ A) = NOT A

* **OR Gate using NOR**  
   Y = NOT (A NOR B) = A \+ B

* **AND Gate using NOR (via De Morgan’s Theorem)**  
   Y = (NOT A) NOR (NOT B) = A \* B

### **3.5 Applications of NOR Gate**

* Control logic circuits

* Digital switching circuits

* Implementing any combinational logic

---

## **4\. Why NAND and NOR are Called Universal Gates**

1. They are **functionally complete** — all other gates (AND, OR, NOT, XOR, XNOR) can be implemented using only NAND or NOR.

2. They are **cost-effective and easy to fabricate** in ICs.

3. Widely used in **VLSI and digital system design**.

---

## **5\. Summary Table – Universal Gates**

| Gate | Boolean Expression | Can Implement |
| ----- | ----- | ----- |
| NAND | (A \* B)’ | NOT, AND, OR, any Boolean function |
| NOR | (A \+ B)’ | NOT, OR, AND, any Boolean function |

---

## **6\. Importance of Universal Gates**

* Simplifies **digital circuit design**

* Reduces **types of gates needed in ICs**

* Forms the foundation of **combinational logic circuits**

