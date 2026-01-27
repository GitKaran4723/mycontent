**PROGRAM-  13**  
**8085 program to find Subtraction of two 16 –bit numbers**  
---

**Code:**  

``` asm
LHLD 8000H  
XCHG  
LHLD 8002H  
MOV A,E  
SUB L  
MOV E,A  
MOV A,D  
SBB H  
MOV D,A  
MOV L,E  
MOV H,D  
JC CRY  
MVI A,00H  
JMP STORE  
CRY:  MVI A,01H  
STORE: STA 8006H  
SHLD 8004H  
HLT  
```

---

**Input:**

| Address | Data |
| :---- | :---- |
| **8000H** | **60    (Lower Byte of first 16 bit no)** |
| **8001H** | **68    (Higher Byte of first 16 bit no)** |
| **8002H** | **36    (Lower Byte of second 16 bit no)** |
| **8003H** | **27   (Higher Byte of second 16 bit no)** |
| **8004H** | **0      (Subtraction of Low Byte)** |
| **8005H** | **0      (Subtraction of High Byte)** |
| **8006H** | **0       (Borrow byte of Subtraction)** |

![Input](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769534831/thirteenprogip_vswrha.png)

---

**Output:**

| Address | Data |
| :---- | :---- |
| **8000H** | **60    (Lower Byte of first 16 bit no)** |
| **8001H** | **68    (Higher Byte of first 16 bit no)** |
| **8002H** | **36    (Lower Byte of second 16 bit no)** |
| **8003H** | **27   (Higher Byte of second 16 bit no)** |
| **8004H** | **24      (Subtraction of Low Byte)** |
| **8005H** | **41     (Subtraction of High Byte)** |
| **8006H** | **0       (Borrow byte of Subtraction)** |

![Output](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769534831/thirteenprogop_ozlraf.png)

---

## **🔹Example: 8085 Program to Subtract Two 16-bit Numbers**

## **Given Data (Decimal)**

| Address | Data |
| ----- | ----- |
| **8000H** | **60** |
| **8001H** | **68** |
| **8002H** | **36** |
| **8003H** | **27** |

---

## **Step 1: Form 16-bit numbers**

**`First number = MSB*256 + LSB = 68*256 + 60 = 17408 + 60 = 17468 ✅`**  
**`Second number = 27*256 + 36 = 6912 + 36 = 6948 ✅`**

---

## **Step 2: Subtract numbers**

**`17468 − 6948 = 10520 ✅`**

---

## **Step 3: Convert result to MSB/LSB for memory**

* **Divide 10520 by 256:**

**`MSB = 10520 ÷ 256 = 41 remainder ?`**  
**`256*41 = 10496`**  
**`LSB = 10520 − 10496 = 24 ✅`**

**✔️ So memory format (decimal):**

| Address | Data | Meaning |
| ----- | ----- | ----- |
| **8004H** | **24** | **LSB (10520 decimal)** |
| **8005H** | **41** | **MSB (10520 decimal)** |
| **8006H** | **0** | **Borrow (no borrow)** |

**✅ That matches what you said: LSB = 24, MSB = 41\.**

---

### **Final Answer (Decimal)**

* **Result = 10520**

* **Memory: 8004H = 24, 8005H = 41, 8006H = 0**

---

**🔹 Step-by-Step Logic**

### **1\. `LHLD 8000H`**

* **Loads first 16-bit number into HL**

  * **L ← 8000H**

  * **H ← 8001H**

---

### **2\. `XCHG`**

* **Exchanges HL ↔ DE**

* **First number is now in DE**

---

### **3\. `LHLD 8002H`**

* **Loads second 16-bit number into HL**

---

### **4\. `MOV A,E`**

* **Copies lower byte of first number into accumulator**

  * **A ← E**

---

### **5\. `SUB L`**

* **Subtracts lower byte of second number from A**

  * **A = E − L**

* **Borrow (if any) is stored in Carry flag**

---

### **6\. `MOV E,A`**

* **Stores lower-byte subtraction result in E**

---

### **7\. `MOV A,D`**

* **Loads upper byte of first number into A**

---

### **8\. `SBB H`**

* **Subtracts upper byte of second number with borrow**

  * **A = D − H − CY**

---

### **9\. `MOV D,A`**

* **Stores upper-byte result in D**

---

### **10\. `MOV L,E`**

* **Moves lower-byte result to L**

---

### **11\. `MOV H,D`**

* **Moves upper-byte result to H**

* **Now HL contains final 16-bit result**

---

### **12\. `JC CRY`**

* **If borrow occurs, jump to `CRY`**

---

### **13\. `MVI A,00H`**

* **Executed if no borrow**

* **A = 00H**

---

### **14\. `JMP STORE`**

* **Skips `CRY`**

---

### **15\. `CRY: MVI A,01H`**

* **Executed if borrow occurs**

* **A = 01H**

---

### **16\. `STORE: STA 8006H`**

* **Stores borrow status in memory**

  * **00H → no borrow**

  * **01H → borrow occurred**

---

### **17\. `SHLD 8004H`**

* **Stores subtraction result (HL) at:**

  * **8004H → LSB**

  * **8005H → MSB**

---

### **18\. `HLT`**

* **Stops program execution**

---

## **🔹Core Logic (One Line)**

**Subtracts two 16-bit numbers, stores the result, and saves borrow status.**

---

## **🔹Registers Used**

* **HL – holds second number and stores result**

* **DE – holds first number**

* **A – used for subtraction and storing borrow**

* **Flags – carry flag used for borrow**

---

## **🔹Mnemonics Used**

| Mnemonic | Function |
| ----- | ----- |
| **LHLD** | **Load 16-bit data from memory to HL** |
| **XCHG** | **Exchange HL and DE** |
| **MOV** | **Copy data between registers** |
| **SUB** | **Subtract without borrow** |
| **SBB** | **Subtract with borrow** |
| **JC** | **Jump if carry (borrow)** |
| **MVI** | **Move immediate data to register** |
| **STA** | **Store accumulator to memory** |
| **SHLD** | **Store HL contents to memory** |
| **HLT** | **Halt program** |

