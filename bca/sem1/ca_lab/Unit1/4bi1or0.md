**PROGRAM- 4**  
**8085 Program to check whether 4th bit of a number is zero or one. If 4th bit is 1 display FF, if 4th bit is 0 display DD** 

**Code:**

``` asm
LDA 8000H  
ANI 08H  
JZ ZERO  
MVI A,0FFH  
JMP STORE  
ZERO: MVI A,0DDH  
STORE: STA 8001H  
HLT
```


**Input:**

| Address | Data |
| :---- | :---- |
| **8000H** | **06** |
| **8001H** | **0** |

![Input](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769358206/forthpro1ip_cou3eu.png)

**Output:**

| Address | Data |
| :---- | :---- |
| **8000H** | **06** |
| **8001H** | **221** |

![Output](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769358206/forthpro2op_hgxaqm.png)

**Possible Outputs(Depending on Inputs):**

| Input  | Output |
| :---- | :---- |
| **06** | **221 (DDH)** |
| **09** | **255 (FFH)** |

## **🔍 Step-by-Step Logic**

### **1\. `LDA 8000H`**

**Loads the data from memory location 8000H into the accumulator.**

---

### **2\. `ANI 08H`**

**Performs AND operation with 08H (0000 1000₂)**  
 **This masks BIT-4 (by position):**

* **BIT-4 = 0 → result = 00H**

* **BIT-4 = 1 → result ≠ 00H**

  ---

### **3\. `JZ ZERO`**

* **If result is zero → BIT-4 = 0**

* **Program jumps to ZERO**

  ---

### **4\. `MVI A, 0FFH`**

* **Executes when BIT-4 = 1**

* **Loads FFH into accumulator**

  ---

### **5\. `JMP STORE`**

**Jumps to STORE, skipping ZERO block.**

---

### **6\. `ZERO: MVI A, 0DDH`**

* **Executes when BIT-4 = 0**

* **Loads DDH into accumulator**

  ---

### **7\. `STORE: STA 8001H`**

**Stores accumulator content into memory location 8001H.**

---

### **8\. `HLT`**

**Stops program execution.**

---

## **🔹 Core Logic**

**The program checks BIT-4 (by position) of the data stored at memory location 8000H and stores FFH at 8001H if BIT-4 is 1, otherwise stores DDH.**

---

## **🔹 Registers Used**

* **Accumulator (A)**  
   **Used to:**

  * **Load data from memory**

  * **Perform AND operation**

  * **Hold the result to be stored in memory**

---

## **🔹 Mnemonics Used in the Program**

| Mnemonic | Purpose |
| ----- | ----- |
| **`LDA`** | **Load accumulator from memory** |
| **`ANI`** | **Logical AND immediate (bit masking)** |
| **`JZ`** | **Jump if Zero flag is set** |
| **`MVI`** | **Move immediate data to register** |
| **`JMP`** | **Unconditional jump** |
| **`STA`** | **Store accumulator to memory** |
| **`HLT`** | **Halt program execution** |

