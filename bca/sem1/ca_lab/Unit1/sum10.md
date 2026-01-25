**PROGRAM \- 5**  
**8085 Program to calculate the sum of first ten natural numbers**

**Code:** 
``` asm
MVI C,0AH  
XRA A  
LOOP: ADD C  
DCR C  
JNZ LOOP  
STA 8000H  
HLT
```

## **🔹 Key Point About Input**

* **No input is required from memory or user.**

* **The counter register C is directly loaded with `0AH` (decimal 10), because the question specifically asks for the sum of the first ten natural numbers.**

* **This makes the program self-contained and fixed for N = 10\.**

**Output:**

| Address | Data |
| :---- | :---- |
| **8000H** | **55** |

 ![Output](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769362540/fifthoutp_cbw7or.png)  

## **🔍 Step-by-Step Logic**

### **1\. `MVI C, 0AH`**

* **Loads the immediate value 0AH (decimal 10\) into register C.**

* **This represents the last natural number (10).**

* **The program will calculate:**  
   **`10 + 9 + 8 + ... + 1`**

---

### **2\. `XRA A`**

* **Performs exclusive OR of A with itself.**

* **Result is always 00H.**

* **Used to clear the accumulator efficiently.**

* **Accumulator A = 00H**

* **This initializes the sum to zero.**

---

### **3\. `LOOP: ADD C`**

* **Adds the content of register C to the accumulator.**

* **Accumulator now stores the running sum.**

* **Example (first iteration):**  
   **`A = 0 + 10 = 10`**

---

### **4\. `DCR C`**

* **Decrements register C by 1\.**

* **After first iteration:**  
   **`C = 09H`**

* **Prepares the next natural number to be added.**

---

### **5\. `JNZ LOOP`**

* **Jump if Zero flag = 0**

* **Zero flag becomes 1 only when C reaches 00H**

* **As long as C ≠ 0, the program loops back to `LOOP`**

* **Ensures the loop runs for values 10 down to 1**

---

### **🔁 Loop Summary**

**The loop executes 10 times, adding:**

**`10 + 9 + 8 + 7 + 6 + 5 + 4 + 3 + 2 + 1`**

---

### **6\. `STA 8000H`**

* **Stores the final sum from accumulator A into memory location 8000H**

* **Final result:**

  * **Decimal: 55**

  * **Hex: 37H**

---

### **7\. `HLT`**

* **Halts program execution.**

## **🔹 Core Logic (One Line)**

**The program calculates the sum of the first ten natural numbers by repeatedly adding numbers 10 to 1 into the accumulator and stores the result at memory location 8000H.**

---

## **🔹 Registers Used**

* **Accumulator (A): Holds the running sum and final result**

* **Register C: Acts as a counter (10 → 1\)**

---

## **🔹 Mnemonics Used**

| Mnemonic | Purpose |
| ----- | ----- |
| **`MVI`** | **Load immediate data into a register** |
| **`XRA`** | **Clear accumulator (A ← 0)(Performs XOR Operation with Accumulator)** |
| **`ADD`** | **Add register contents to accumulator** |
| **`DCR`** | **Decrement register by 1** |
| **`JNZ`** | **Jump if Zero flag is not set (loop control)** |
| **`STA`** | **Store accumulator into memory** |
| **`HLT`** | **Halt the program** |

