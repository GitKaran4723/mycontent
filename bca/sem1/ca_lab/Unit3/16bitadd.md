**PROGRAM \- 12**  
**8085 program to find Addition of two 16 –bit numbers.**  
---

**Code:**  

``` asm
LHLD 8000H  
XCHG  
LHLD 8002H  
DAD D  
SHLD 8004H  
JC STORE  
MVI A,00H  
JMP EXIT  
STORE:  MVI A,01H  
EXIT:  STA 8006H  
HLT  
```

---

**Input:**

| Address | Data |
| :---- | :---- |
| **8000H** | **56     (Lower Byte of first 16 bit no)** |
| **8001H** | **64    (Higher Byte of first 16 bit no)** |
| **8002H** | **32    (Lower Bye of second 16 bit no)** |
| **8003H** | **23   (Higher Byte of second 16 bit no)** |
| **8004H** | **0      (Sum of Low Byte)** |
| **8005H** | **0      (Sum of High Byte)** |
| **8006H** | **0       (Carry byte of Addition)** |

![Input](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769534831/twelthprogip_iftk2y.png)

---

**Output:**

| Address | Data |
| :---- | :---- |
| **8000H** | **56     (Lower Byte of first 16 bit no)** |
| **8001H** | **64    (Higher Byte of first 16 bit no)** |
| **8002H** | **32    (Lower Bye of second 16 bit no)** |
| **8003H** | **23   (Higher Byte of second 16 bit no)** |
| **8004H** | **88       (Sum of Low Byte)** |
| **8005H** | **87       (Sum of High Byte)** |
| **8006H** | **0       (Carry byte of Addition)** |

![Output](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769534831/twelthprogop_wonftx.png)

---

## **🔹Example: 8085 Program to Add Two 16-bit Numbers**

### **Input Data (Decimal)**

| Address | Data |
| ----- | ----- |
| **8000H** | **56** |
| **8001H** | **64** |
| **8002H** | **32** |
| **8003H** | **23** |

*   
  **First number = `8001H:8000H = 64*256 + 56 = 16440`**

* **Second number = `8003H:8002H = 23*256 + 32 = 5920`**

---

### **Program Operation**

1. **Load first number → DE**

2. **Load second number → HL**

3. **Add HL \+ DE → HL**

4. **Store sum → 8004H–8005H**

5. **Check carry → store 0 (no carry) or 1 (carry) at 8006H**

---

### **Output Data**

| Address | Data | Meaning |
| ----- | ----- | ----- |
| **8004H** | **88** | **Sum LSB** |
| **8005H** | **87** | **Sum MSB** |
| **8006H** | **0** | **Carry flag** |

*   
  **Sum = 22360 decimal (87H, 58H in memory)**

* **Carry = 0 (no overflow)**

---

**🔹 Step-by-Step Logic**

### **1\. `LHLD 8000H`**

* **Loads 16-bit data from memory into HL pair**

* **Meaning:**

  * **L ← contents of 8000H**

  * **H ← contents of 8001H**

**So now:**

 **`HL = number stored at 8001H:8000H`**

* 

---

### **2\. `XCHG`**

* **Exchanges HL ↔ DE**

**After this:**

 **`DE = first 16-bit number`**  
**`HL = old DE (doesn’t matter now)`**

* 

---

### **3\. `LHLD 8002H`**

* **Loads another 16-bit number into HL**

* **Meaning:**

  * **L ← contents of 8002H**

  * **H ← contents of 8003H**

**Now:**

 **`HL = second 16-bit number`**  
**`DE = first 16-bit number`**

* 

---

### **4\. `DAD D`**

* **Adds DE to HL**

**Operation:**

 **`HL = HL + DE`**

*   
* **If the sum exceeds 16 bits:**

  * **Carry flag (CY) = 1**

* **Otherwise:**

  * **CY = 0**

---

### **5\. `SHLD 8004H`**

* **Stores the 16-bit result from HL into memory**

* **Meaning:**

  * **8004H ← L**

  * **8005H ← H**

**So:**

 **`Sum stored at 8005H:8004H`**

* 

---

### **6\. `JC STORE`**

* **Jump if Carry**

* **If carry flag = 1 (overflow occurred):**

  * **Jump to label `STORE`**

---

### **7\. `MVI A,00H`**

* **Executes only if no carry**

**Loads:**

 **`A = 00H`**

*   
* **Meaning: No overflow**

---

### **8\. `JMP EXIT`**

* **Skips the `STORE` part**

* **Goes directly to `EXIT`**

---

### **9\. `STORE: MVI A,01H`**

* **Executes only if carry occurred**

**Loads:**

 **`A = 01H`**

*   
* **Meaning: Overflow occurred**

---

### **10\. `EXIT: STA 8006H`**

* **Stores accumulator value into memory**

**Meaning:**

 **`8006H = 00H → no carry`**  
**`8006H = 01H → carry occurred`**

* 

---

### **11\. `HLT`**

* **Stops program execution**

---

## **🔹Core Logic (One Line)**

**Adds two 16-bit numbers stored in memory, saves the sum, and stores carry status.**

---

## **🔹Registers Used**

| Register | Purpose |
| ----- | ----- |
| **HL** | **Holds second number and final sum** |
| **DE** | **Holds first number** |
| **A** | **Stores carry result (0 or 1\)** |
| **Flags** | **Carry flag checked** |

---

## **🔹Mnemonics Used**

| Mnemonic | Function |
| ----- | ----- |
| **LHLD** | **Load 16-bit data from memory to HL** |
| **XCHG** | **Exchange HL and DE** |
| **DAD D** | **Add DE to HL** |
| **SHLD** | **Store 16-bit data from HL to memory** |
| **JC** | **Jump if carry** |
| **MVI** | **Move immediate data** |
| **JMP** | **Unconditional jump** |
| **STA** | **Store accumulator to memory** |
| **HLT** | **Stop execution** |

