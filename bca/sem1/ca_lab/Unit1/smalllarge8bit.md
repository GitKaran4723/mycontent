**PROGRAM- 2**

1.  **Write a Program to find the largest of two numbers**    
     
   

**Code:**  
```asm
LXI H,8000H
MOV C,M
INX H
MOV B,M
MOV A,C
CMP B
JNC STORE
MOV A,B
STORE: STA 8002H
HLT
```

**Input:**

| Address | Data |
| :---- | :---- |
| **8000H** | **54** |
| **8001H** | **115** |
| **8002H** | **0** |

![Input11](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769241220/SECONDPROG1STIP_u1izmx.png)

**Output:**

| Address | Data |
| :---- | :---- |
| **8000H** | **54** |
| **8001H** | **115** |
| **8002H** | **115** |

 ![Output11](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769241220/SECONDPROG1STAOP_w1iqqc.png)

## **🧠 Step-by-Step Logic**

### **1️⃣ `LXI H,8000H`**

* **Loads 8000H into the HL register pair**

* **HL → points to memory location 8000H**

---

### **2️⃣ `MOV C,M`**

* **Copies the data from memory location 8000H into register C**

* **C ← \[8000H\]**

---

### **3️⃣ `INX H`**

* **Increments the HL register pair by 1**

* **HL now points to 8001H**

---

### **4️⃣ `MOV B,M`**

* **Copies the data from memory location 8001H into register B**

* **B ← \[8001H\]**

---

### **5️⃣ `MOV A,C`**

* **Moves the content of register C into Accumulator**

* **A ← C (first number)**

---

### **6️⃣ `CMP B`**

* **Compares the content of Accumulator (A) with register B**

* **Internally performs: A − B**

* **Result is not stored, only flags are affected**

**👉 Key flag here:**

* **Carry flag (CY)**

  * **CY = 0 → A ≥ B**

  * **CY = 1 → A \< B**

---

### **7️⃣ `JNC STORE`**

* **Jump if No Carry**

* **If A ≥ B, control jumps to label `STORE`**

---

### **8️⃣ `MOV A,B`**

* **Executed only if A \< B**

* **Moves the value in B (larger number) into Accumulator**

---

### **9️⃣ `STORE: STA 8002H`**

* **Stores the content of Accumulator into memory location 8002H**

* **The larger number is stored at 8002H**

---

### **🔟 `HLT`**

* **Stops program execution**

---

## **📌 Final Result**

| Memory Location | Purpose |
| ----- | ----- |
| **8000H** | **First number** |
| **8001H** | **Second number** |
| **8002H** | **Larger number (output)** |

### **🧩 Core Logic (One Line**

**The program compares two numbers at memory locations 8000H and 8001H and stores the larger number at 8002H.**

### **✅  Registers Used in this program**

| Register | Purpose |
| :---: | :---: |

| A (Accumulator) | Holds one of the numbers temporarily and stores the larger number before storing to memory |
| :---- | :---- |

| B | Holds the second number (from 8001H) for comparison |
| :---- | :---- |

| C | Holds the first number (from 8000H) temporarily |
| :---- | :---- |

| H-L pair (HL) | Used as a memory pointer to access 8000H and 8001H |
| :---- | :---- |

**b. Write an 8085 Program to find the smallest of two numbers** 

**Code:**  
**LXI H,8000H**  
**MOV C,M**  
**INX H**   
**MOV B,M**  
**MOV A,C**  
**CMP B**  
**JC STORE**  
**MOV A,B**  
**STORE: STA 8002H**  
**HLT**

**Input:**

| Address | Data |
| :---- | :---- |
| **8000H** | **100** |
| **8001H** | **250** |
| **8002H** | **0** |

![Input21](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769250819/s2ip_njv6rh.png)

**Output:** 

| Address | Data |
| :---- | :---- |
| **8000H** | **100** |
| **8001H** | **250** |
| **8002H** | **100** |

![Input22](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769250819/s2op_mmlrx0.png)

## **🔹 Step-by-Step Logic**

### **1️⃣ `LXI H,8000H`**

* **Loads HL register pair with address 8000H**

* **HL now points to 8000H (first number)**

---

### **2️⃣ `MOV C,M`**

* **Copy data from memory pointed by HL (M) into register C**

* **C ← \[8000H\] (first number)**

---

### **3️⃣ `INX H`**

* **Increment HL by 1**

* **HL now points to 8001H (second number)**

---

### **4️⃣ `MOV B,M`**

* **Copy data from memory pointed by HL into register B**

* **B ← \[8001H\] (second number)**

---

### **5️⃣ `MOV A,C`**

* **Move data from C into Accumulator A**

* **A ← C (first number)**

---

### **6️⃣ `CMP B`**

* **Compare Accumulator (A) with B**

* **Internally does A − B and sets flags**

* **Carry flag (CY) is set if A \< B, reset if A ≥ B**

---

### **7️⃣ `JC STORE`**

* **Jump if Carry = 1 → i.e., if A \< B**

* **If first number \< second number, jump to STORE (no need to change A)**

* **If first number ≥ second number, continue to next instruction**

---

### **8️⃣ `MOV A,B`**

* **Executed only if first number ≥ second number**

* **Move B (second number, smaller) into Accumulator**

* **Now A has the smaller number**

---

### **9️⃣ `STORE: STA 8002H`**

* **Store the Accumulator (smaller number) into memory location 8002H**

---

### **🔟 `HLT`**

* **Stop execution**

## **🧩 Core Logic (One Line)**

**The program compares two numbers at memory locations 8000H and 8001H and stores the smaller number at 8002H.**

---

## **📝 Registers Used**

| Register | Purpose |
| ----- | ----- |
| **A** | **Accumulator – holds a number and smaller value before storing** |
| **B** | **Holds second number (8001H)** |
| **C** | **Holds first number (8000H)** |
| **HL** | **Points to memory locations 8000H & 8001H**  |

### **📘 Mnemonics Used in this program (8085)**

| Mnemonic | Operation Performed |
| ----- | ----- |
| **LXI H, address** | **Load HL register pair with address** |
| **MOV C,M** | **Copy memory (pointed by HL) to C** |
| **INX H** | **Increment HL register pair** |
| **MOV B,M** | **Copy memory (pointed by HL) to B** |
| **MOV A,C** | **Copy C to Accumulator A** |
| **CMP B** | **Compare A with B** |
| **JC label** | **Jump if Carry = 1** |
| **JNC label** | **Jump if Carry = 0** |
| **MOV A,B** | **Copy B to Accumulator A** |
| **STA address** | **Store Accumulator to memory** |
| **HLT** | **Halt execution** |

