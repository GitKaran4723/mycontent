**PROGRAM- 7**  
**8085 Program to find the reverse of an 8-bit number**   
---

Code:

``` asm  
LDA 8000H  
RLC  
RLC  
RLC  
RLC  
STA 8001H  
HLT
```

---

**Input:**

| Address | Data |
| :---- | :---- |
| **8000H** | **54  (36H)** |
| **8001H** | **0** |

![Input](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769449878/sevenprogip_v2tcwn.png)

---

**Output:**

| Address | Data |
| :---- | :---- |
| **8000H** | **54 (36H)** |
| **8001H** | **99 (99H)** |

![Output](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769449878/sevenprogop_kn3oef.png)

---

### **Example:**        **Input at 8000H = 54 (decimal) = 36H**

* ### **After 4 × RLC (Rotate Accumulator Left)** 

* ### **36H → 63H** 

### **Results:**

* ### **Hexadecimal result: 63H** 

* ### **Decimal result: 99** 

### **Stored at:**  **👉 8001H = 63H (99 decimal)**

---

### **🔍 Step-by-Step Logic**

### **1️⃣ `LDA 8000H`**

* **Loads the 8-bit data from memory location 8000H into the Accumulator (A).**

---

### **2️⃣ `RLC` – Rotate Accumulator Left**

* **Rotates all bits of the accumulator left by one position.**

* **The most significant bit (D7):**

  * **Goes to the least significant bit (D0)**

  * **Also goes to the Carry flag**

---

### **3️⃣ `RLC` (second time) – Rotate Accumulator Left**

* **Again rotates the accumulator left by one bit.**

* **Bits shift left circularly one more position.**

---

### **4️⃣ `RLC` (third time) – Rotate Accumulator Left**

* **Performs another left rotation.**

* **Accumulator bits move left again.**

---

### **5️⃣ `RLC` (fourth time) – Rotate Accumulator Left**

* **After four rotate-left operations:**

  * **The upper nibble and lower nibble are interchanged**

**Example:**

**`Original A = XYH`**  
**`After 4 RLCs = YXH`**

---

### **6️⃣ `STA 8001H`**

* **Stores the rotated accumulator content into memory location 8001H.**

---

### **7️⃣ `HLT`**

* **Stops program execution.**

---

## **🔑 Overall Logic (one line)**

**👉 The program rotates the accumulator left four times to swap its upper and lower nibbles and stores the result in memory.**

---

**🔹 Registers used:**

* **Accumulator (A): Holds the data read from memory, performs the rotations, and stores the result back to memory.**

---

**🔹Mnemonics used :**

| Mnemonic | Use |
| ----- | ----- |
| **LDA** | **Load accumulator from memory** |
| **RLC** | **Rotate accumulator left circular** |
| **STA** | **Store accumulator into memory** |
| **HLT** | **Halt the program** |

