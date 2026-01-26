**PROGRAM- 10**  
 **8085 program to count a number of ones in the given 8-bit number**  
---

**Code:**  

``` asm
LDA 8000H  
MVI C,08H  
MVI D,00H  
LOOP:  RAR  
JC COUNT  
DCR C  
JNZ LOOP  
JMP DISP  
COUNT:  INR D  
DCR C  
JNZ LOOP  
DISP: MOV A,D  
STA 8001H  
HLT  
```

---

**Input:**

| Address | Data |
| :---- | :---- |
| **8000H** | **21** |
| **8001H** | **0** |

![Input](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769449878/tenthprogip_exoibz.png)

---

**Output:**

| Address | Data |
| :---- | :---- |
| **8000H** | **21** |
| **8001H** | **03** |

![Output](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769449878/tenthprogop_dhd4dz.png)

---

### **Example (8000H = 21 decimal) :**

* **8000H = 21 (15H) = 00010101**  
* **Program checks 8 bits**  
* **Bit-1 found at 1st, 3rd, and 5th positions**  
* **Count register D = 03H**  
* **8001H = 03H (3 decimal)**

---

### **🔍 Step-by-Step Logic**

### **1\. Load data**

**`LDA 8000H`**

**• Load the 8-bit data from memory location 8000H into accumulator A.**

---

### **2\. Initialize counters**

**`MVI C,08H`**

**• Load 08H into register C**  
 **• Acts as a loop counter for 8 bits.**

**`MVI D,00H`**

**• Clear register D**  
 **• Used to count number of 1s.**

---

### **3\. Rotate right through carry**

**`LOOP: RAR`**

**• Rotates accumulator right by one bit**  
 **• LSB moves into Carry flag**

---

### **4\. Check Carry flag**

**`JC COUNT`**

**• If Carry = 1, the rotated bit was 1**  
 **• Jump to COUNT**

---

### **5\. If Carry = 0**

**`DCR C`**  
**`JNZ LOOP`**

**• Decrement bit counter C**  
 **• If all 8 bits not checked, repeat loop**

---

### **6\. If Carry = 1 (COUNT)**

**`COUNT: INR D`**

**• Increment register D**  
 **• Increases count of 1s**

**`DCR C`**  
**`JNZ LOOP`**

**• Decrement bit counter**  
 **• Loop until all 8 bits are processed**

---

### **7\. Display / store result**

**`DISP: MOV A,D`**

**• Move the final count of 1s from D to A**

**`STA 8001H`**

**• Store the count at memory location 8001H**

---

### **8\. Stop execution**

**`HLT`**

**• Halt the program**

---

### **🔹Core Logic (One Line)**

**Counts the number of set bits (1s) in the 8-bit data stored at memory location 8000H and stores the count at 8001H.**

---

### **🔹Registers Used**

 **• A (Accumulator) – holds data and rotation result**  
 **• C – loop counter (8 bits)**  
 **• D – stores count of 1s**  
 **• Flag Register – Carry flag used to detect bit value**  
 **• Program Counter (PC)**

---

### **🔹Mnemonics Used** 

| Mnemonic | Description |
| ----- | ----- |
| **LDA** | **Loads data from memory into accumulator** |
| **MVI** | **Loads immediate data into a register** |
| **RAR** | **Rotates accumulator right through carry** |
| **JC** | **Jumps if Carry flag is set** |
| **INR** | **Increments register by 1** |
| **DCR** | **Decrements register by 1** |
| **JNZ** | **Jumps if Zero flag is not set** |
| **JMP** | **Unconditional jump** |
| **MOV** | **Copies data from one register to another** |
| **STA** | **Stores accumulator contents to memory** |
| **HLT** | **Halts program execution** |

