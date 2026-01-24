**PROGRAM- 1**  
 **Write an 8085 Program to swap two 8-bit numbers**

Code:

```asm
LDA 8000H
MOV B,A
LDA 8001H
STA 8000H
MOV A,B
STA 8001H
HLT
```


**Input:**

| Address | Data |
| :---- | :---- |
| **8000H** | **15** |
| **8001H** | **10** |

![Diagram](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769238682/firstprog8085_oyo7dy.png)

**Output:** 

| Address | Data |
| :---- | :---- |
| **8000H** | **10** |
| **8001H** | **15** |

![Output](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769238682/firstprogop8085_qihby1.png)

**Logic of Code:**

### **🧠 Step-by-Step Logic**

#### **1️⃣ `LDA 8000H`**

* **Loads the data at memory location 8000H into the Accumulator (A)**

* **A ← \[8000H\]**

---

#### **2️⃣ `MOV B,A`**

* **Copies the content of Accumulator A into register B**

* **This is done to temporarily save the value from 8000H**

* **B ← A**

**👉 *Register B acts like a temporary storage.***

---

#### **3️⃣ `LDA 8001H`**

* **Loads the data at memory location 8001H into the Accumulator**

* **A ← \[8001H\]**

---

#### **4️⃣ `STA 8000H`**

* **Stores the content of Accumulator A into memory location 8000H**

* **\[8000H\] ← A**

**👉 Now 8000H contains the original data of 8001H**

---

#### **5️⃣ `MOV A,B`**

* **Moves the saved value from register B back into Accumulator**

* **A ← B**

**👉 This restores the original value of 8000H into A**

---

#### **6️⃣ `STA 8001H`**

* **Stores the Accumulator content into memory location 8001H**

* **\[8001H\] ← A**

**👉 Now 8001H contains the original data of 8000H**

---

#### **7️⃣ `HLT`**

* **Stops program execution**

### **🧩 Core Logic (One Line)**

**Save first value → load second → store second in first → restore saved value → store in second**

### **✅  Registers Used in this program**

* **Accumulator (A) – main data register**

* **Register B – temporary storage**

* **Program Counter (PC) – points to next instruction (automatic)**

### **📘 Mnemonics Used in this program (8085)**

| Mnemonic | Full Form | Operation Performed |
| ----- | ----- | ----- |
| **LDA** | **Load Accumulator Direct** | **Loads data from a specified memory location into Accumulator** |
| **MOV** | **Move** | **Copies data from one register to another** |
| **STA** | **Store Accumulator Direct** | **Stores data from Accumulator into a specified memory location** |
| **HLT** | **Halt** | **Stops the execution of the program** |

