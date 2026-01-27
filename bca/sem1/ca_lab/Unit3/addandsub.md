**PROGRAM- 11**  
**8085 program to find Addition & Subtraction of two 8 –bit HEX numbers**  
---

**Code:**  

``` asm
LXI H,8000H  
MOV C,M  
MOV E,C  
INX H   
MOV D,M  
MOV A,C  
ADD D  
STA 8002H  
JC CRY  
MVI A,00H  
JMP DCRY  
CRY: MVI A,01H  
DCRY: STA 8004H  
MOV A,E  
SUB D  
STA 8003H  
JC BCRY  
MVI A,00H  
JMP BDCRY  
BCRY: MVI A,01H  
BDCRY: STA 8005H  
HLT  
```

---

**Input:**

| Address | Data |
| :---- | :---- |
| **8000H** | **120 (First 8 bit number)** |
| **8001H** | **35  (Second 8 bit number** |
| **8002H** | **0   (Sum of 8 bit number)** |
| **8003H** | **0  (Subtraction of 8 bit number)** |
| **8004H** | **0  (Carry bit of Addition)** |
| **8005H** | **0  (Borrow bit of Subtraction)** |

![Input](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769534830/Elevenprogip_hb6gw5.png)

---

**Output:**

| Address | Data |
| :---- | :---- |
| **8000H** | **120 (First 8 bit number)** |
| **8001H** | **35  (Second 8 bit number** |
| **8002H** | **155   (Sum of 8 bit number)** |
| **8003H** | **85  (Subtraction of 8 bit number)** |
| **8004H** | **0  (Carry bit of Addition)** |
| **8005H** | **0  (Borrow bit of Subtraction)** |

![Output](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769534830/elevenproop_tz09za.png)

---

## **Example:**

## **🔢 Given Data (Decimal)**

* ## **8000H = 120₁₀ = 78H** 

* ## **8001H = 35₁₀ = 23H** 

## ---

## **➕ ADDITION PART**

### **Operation**

## **`120 + 35 = 155`**

## 

### **In Hex**

## **`78H + 23H = 9BH`**

## 

* ## **Result fits in 8 bits → NO carry** 

### **Stored Results**

| Memory | Value | Meaning |
| ----- | ----- | ----- |
| **8002H** | **9BH (155)** | **Sum** |
| **8004H** | **00H** | **Carry = 0** |

## ---

## **➖ SUBTRACTION PART**

### **Operation**

## **`120 − 35 = 85`**

## 

### **In Hex**

## **`78H − 23H = 55H`**

## 

* ## **First number \> second number → NO borrow** 

### **Stored Results**

| Memory | Value | Meaning |
| ----- | ----- | ----- |
| **8003H** | **55H (85)** | **Difference** |
| **8005H** | **00H** | **Borrow = 0** |

## ---

## **✅ Final Memory Contents**

| Address | Data (Hex) | Data (Decimal) |
| ----- | ----- | ----- |
| **8000H** | **78H** | **120** |
| **8001H** | **23H** | **35** |
| **8002H** | **9BH** | **155** |
| **8003H** | **55H** | **85** |
| **8004H** | **00H** | **Carry** |
| **8005H** | **00H** | **Borrow** |

---

**🔹 Step-by-Step Logic**

### **1️⃣ Load first number**

**`LXI H,8000H`**  
**`MOV C,M`**

* **HL → 8000H**

* **C ← contents of 8000H (first number)**

**`MOV E,C`**

* **Copy first number into E (used later for subtraction)**

---

### **2️⃣ Load second number**

**`INX H`**  
**`MOV D,M`**

* **HL → 8001H**

* **D ← contents of 8001H (second number)**

---

## **➕ ADDITION PART**

**`MOV A,C`**  
**`ADD D`**

* **A ← first number**

* **A = A \+ D (second number)**

* **Result in A**

* **Carry flag (CY) may be set**

**`STA 8002H`**

* **Store sum at 8002H**

**`JC CRY`**

* **If carry = 1, jump to label `CRY`**

**`MVI A,00H`**  
**`JMP DCRY`**

* **No carry → store `00H`**

**`CRY: MVI A,01H`**

* **Carry present → store `01H`**

**`DCRY: STA 8004H`**

* **Store carry flag result at 8004H**

---

## **➖ SUBTRACTION PART**

**`MOV A,E`**  
**`SUB D`**

* **A ← first number**

* **A = A − second number**

* **Result in A**

* **CY = 1 means borrow occurred (8085 rule)**

**`STA 8003H`**

* **Store difference at 8003H**

**`JC BCRY`**

* **If borrow occurred → jump to `BCRY`**

**`MVI A,00H`**  
**`JMP BDCRY`**

* **No borrow → store `00H`**

**`BCRY: MVI A,01H`**

* **Borrow occurred → store `01H`**

**`BDCRY: STA 8005H`**

* **Store borrow flag at 8005H**

---

### **🛑 Program End**

**`HLT`**

* **Stop execution**

---

## **🧠 Summary Table**

| Memory | Meaning |
| ----- | ----- |
| **8000H** | **First number** |
| **8001H** | **Second number** |
| **8002H** | **Sum** |
| **8004H** | **Carry (1 = yes, 0 = no)** |
| **8003H** | **Difference** |
| **8005H** | **Borrow (1 = yes, 0 = no)** |

---

## **💡 Key Concept**

* **JC after ADD → Carry**

* **JC after SUB → Borrow**

* **Carry and borrow are stored separately for clarity.**

---

### **🔹Core Logic (one line)**

**Adds and subtracts two 8-bit numbers stored in memory and saves the result along with carry and borrow separately.**

---

### **🔹Registers Used**

* **H–L → Memory pointer (8000H, 8001H)**

* **C → First number**

* **D → Second number**

* **E → Copy of first number (for subtraction)**

* **A → Accumulator (for add/sub operations)**

---

### **🔹Mnemonics Used** 

| Mnemonic | Meaning / Function |
| ----- | ----- |
| **LXI** | **Load 16-bit immediate data into register pair** |
| **MOV** | **Copy data between registers or memory** |
| **INX** | **Increment register pair by 1** |
| **ADD** | **Add register data to accumulator** |
| **SUB** | **Subtract register data from accumulator** |
| **STA** | **Store accumulator directly to memory** |
| **JC** | **Jump if carry flag is set** |
| **MVI** | **Load 8-bit immediate data into register** |
| **JMP** | **Unconditional jump** |
| **HLT** | **Stop program execution** |

