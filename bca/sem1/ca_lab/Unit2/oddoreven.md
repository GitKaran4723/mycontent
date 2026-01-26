**PROGRAM- 9**  
**8085 Program to check whether a number is ODD or EVEN. If Even no. display DD, if odd no. display FF**  
---

**Code:**  

``` asm
LDA 8000H  
ANI 01H  
JZ EVEN  
ODD:  MVI A,0FFH  
JMP EXIT  
EVEN:  MVI A,0DDH  
EXIT:  STA 8001H  
HLT
```
  
---

**Input:**

| Address | Data |
| :---- | :---- |
| **8000H** | **16** |
| **8001H** | **0** |

![Input](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769449877/ninthprogip_jkwifo.png)

---

**Output:**

| Address | Data |
| :---- | :---- |
| **8000H** | **16** |
| **8001H** | **221 (DDH)** |

![Output](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769449877/ninthprogop_jvowmc.png)

---

### **🔹Example:**

* **Step 1: `LDA 8000H` → Load 16 (10H) into A**

* **Step 2: `ANI 01H` → AND with 01H to check LSB**

  * **10H & 01H = 00H → LSB = 0 → number is even**

* **Step 3: `JZ EVEN` → Jump to `EVEN` label because zero flag is set**

* **Step 4: `MVI A,0DDH` → Load A = DDH (221 decimal) to indicate even number**

* **Step 5: `STA 8001H` → Store A into memory 8001H**

* **Step 6: `HLT` → Program halts**

**Output:**

| Address | Value (Hex) | Value (Decimal) |
| ----- | ----- | ----- |
| **8000H** | **10H** | **16** |
| **8001H** | **DDH** | **221** |

**Logic in one line: Checks if the number is odd or even and stores a code (FFH for odd, DDH for even).**

---

### **🔍 Step-by-Step Logic**

---

### **1️⃣ LDA 8000H**

* **Instruction: `LDA 8000H`**

* **Effect: Load the value stored at memory location `8000H` into the accumulator (A).**

**Purpose: Fetch the input number from memory to check its parity (odd/even).**

---

### **2️⃣ ANI 01H**

* **Instruction: `ANI 01H`**

* **Effect: Perform a bitwise AND of accumulator A with `0000 0001` (binary of 01H).**

* **Only the least significant bit (LSB) is checked.**

**Logic:**

* **If LSB = 0 → number is even**

* **If LSB = 1 → number is odd**

**Result:**

* **Z (zero) flag is set if result = 0 (even), cleared if result = 1 (odd).**

---

### **3️⃣ JZ EVEN**

* **Instruction: `JZ EVEN`**

* **Effect: Jump to label `EVEN` if zero flag is set.**

* **Zero flag is set if the number was even (ANI result = 0).**

**Purpose: Branch to handle even numbers.**

---

### **4️⃣ ODD: MVI A,0FFH**

* **Instruction: `MVI A,0FFH`**

* **Effect: Load accumulator A with `0FFH` (decimal 255).**

**Purpose: Indicate that the input number is odd.**

---

### **5️⃣ JMP EXIT**

* **Instruction: `JMP EXIT`**

* **Effect: Unconditionally jump to label `EXIT` to skip the even case.**

**Purpose: Prevent executing the “EVEN” code after handling odd numbers.**

---

### **6️⃣ EVEN: MVI A,0DDH**

* **Instruction: `MVI A,0DDH`**

* **Effect: Load accumulator A with `0DDH` (decimal 221).**

**Purpose: Indicate that the input number is even.**

---

### **7️⃣ EXIT: STA 8001H**

* **Instruction: `STA 8001H`**

* **Effect: Store the value of accumulator A into memory location `8001H`.**

**Purpose: Save the odd/even indicator in memory.**

---

### **8️⃣ HLT**

* **Instruction: `HLT`**

* **Effect: Stop the program.**

**Purpose: End execution.**

---

### **🔹Core Logic (one line)**

**Checks whether the number stored at 8000H is even or odd by testing the LSB and stores the result at 8001H.**

---

### **🔹One-Line Logic**

**If LSB = 0, store DDH (even); else store FFH (odd) at 8001H.**

---

### **🔹Registers Used**

 **• Accumulator (A)**  
 **• Program Counter (PC)**  
 **• Flag Register (Zero Flag)**

---

### **🔹Mnemonics Used** 

| Mnemonic | Description |
| ----- | ----- |
| **LDA** | **Loads the contents of a specified memory location into the accumulator** |
| **ANI** | **Performs bitwise AND operation between accumulator and immediate data** |
| **JZ** | **Jumps to the specified address if Zero flag is set** |
| **MVI** | **Moves immediate data into a register** |
| **JMP** | **Unconditionally jumps to the specified address** |
| **STA** | **Stores the contents of the accumulator into a specified memory location** |
| **HLT** | **Halts the execution of the program** |

