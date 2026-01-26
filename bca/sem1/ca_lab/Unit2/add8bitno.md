**PROGRAM- 6**  
**Write an assembly language program in 8085 microprocessors to find the sum of digits of an 8-bit number**  
---

Code:  

``` asm
LDA 8000H  
MOV B,A  
ANI 0FH  
MOV C,A  
MOV A,B  
RLC  
RLC  
RLC  
RLC  
ANI 0FH  
ADD C  
STA 8001H  
HLT
```

---

**Input:**

| Address | Data |
| :---- | :---- |
| **8000H** | **98 (62H)** |
| **8001H** | **0** |

![Input](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769449877/sixthprogip_esu2k3.png)

**Output:**

| Address | Data |
| :---- | :---- |
| **8000H** | **98 (62H)** |
| **8001H** | **08** |

![Output](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769449877/sixthprogop_dakhww.png)

---

### **Example:**

* **Number at 8000H = 98 (decimal)**

* **Hex equivalent in accumulator = 62H**

**Now:**

* **Upper nibble = 6**

* **Lower nibble = 2**

* **Sum = 6 + 2 = 8**

**So:**

* **08H is stored at 8001H**

---

## **🔍 Step-by-Step Logic**

### **1️⃣ `LDA 8000H`**

* **Loads the 8-bit data from memory location 8000H into Accumulator (A)**

**Example:**

**`A = [8000H] = XYh`**

**(where X = upper nibble, Y = lower nibble)**

---

### **2️⃣ `MOV B,A`**

* **Copies accumulator contents into register B**

**`B = A`**

**Purpose: save original data for later use**

---

### **3️⃣ `ANI 0FH`**

* **AND accumulator with `00001111`**

* **Clears upper nibble, keeps lower nibble**

**`A = A AND 0Fh`**

**If**

**`A = XYh`**

**After AND:**

**`A = 0Yh`**

---

### **4️⃣ `MOV C,A`**

* **Stores the lower nibble in register C**

**`C = lower nibble`**

---

### **5️⃣ `MOV A,B`**

* **Restores original value back to accumulator**

**`A = XYh`**

---

### **6️⃣ `RLC` (executed 4 times)**

**Each `RLC` rotates accumulator left by 1 bit**

**After 4 RLCs:**

* **Upper nibble moves to lower nibble position**

**Example:**

**`Original A = XYh`**  
**`After 4 RLCs → A = YXh`**

---

### **7️⃣ `ANI 0FH`**

* **Masks upper nibble again**

* **Extracts original upper nibble**

**`A = X`**

---

### **8️⃣ `ADD C`**

* **Adds lower nibble (stored in C) to upper nibble**

**`A = upper nibble + lower nibble`**

---

### **9️⃣ `STA 8001H`**

* **Stores the sum at memory location 8001H**

---

### **🔟 `HLT`**

* **Stops program execution**

---

## **🔍 Overall Logic (In Simple Words)**

**👉 The program:**

1. **Takes an 8-bit number from memory (8000H)**

2. **Separates upper nibble and lower nibble**

3. **Adds them together**

4. **Stores the result at memory location 8001H**

---

### **🔹Core Logic (one line)**

**👉 The program separates the upper and lower nibbles of an 8-bit hex number, adds them, and stores the result in memory.**

---

### **🔹Registers Used**

* **A (Accumulator) – data manipulation and arithmetic**

* **B – stores original data**

* **C – stores lower nibble**

## **🔹 Mnemonics Used**

| **Mnemonic** | **Purpose**                                      |
|:------------:|:-------------------------------------------------|
| **LDA**      | Loads 8-bit data from memory into accumulator    |
| **MOV**      | Copies data between registers                    |
| **ANI**      | Performs AND operation to mask a nibble          |
| **RLC**      | Rotates accumulator left                         |
| **ADD**      | Adds contents of a register to accumulator       |
| **STA**      | Stores accumulator content into memory           |
| **HLT**      | Terminates program execution                     |


