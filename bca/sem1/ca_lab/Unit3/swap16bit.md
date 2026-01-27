**PROGRAM \-  14**  
**8085 program for Swapping of two 16-bit numbers**

## ---

**Code:**

``` asm  
LHLD 8000H  
XCHG  
LHLD 8002H  
SHLD 8000H  
XCHG  
SHLD 8002H  
HLT
```

## ---

**Input:**

| Address | Data |
| :---- | :---- |
| **8000H** | **72** |
| **8001H** | **146** |
| **8002H** | **155** |
| **8003H** | **34** |

![Input](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769534830/fourteenprogip_nctwr5.png)

## ---

**Output:**

| Address | Data |
| :---- | :---- |
| **8000H** | **155** |
| **8001H** | **34** |
| **8002H** | **72** |
| **8003H** | **146** |

![Output](https://res.cloudinary.com/dvxz7qw4v/image/upload/v1769534830/fourteenproop_rkg6j1.png)

## ---

## **🔹Example Data Input (Decimal):** 

| Address | Data |
| ----- | ----- |
| **8000H** | **72** |
| **8001H** | **146** |
| **8002H** | **155** |
| **8003H** | **34** |

## ---

## **Step 1: Form 16-bit numbers**

* ## **First number (8001H:8000H) = 146 × 256 \+ 72 = 37376 \+ 72 = 37448** 

* ## **Second number (8003H:8002H) = 34 × 256 \+ 155 = 8704 \+ 155 = 8859** 

## ---

## **Step-by-Step Execution**

1. ## **`LHLD 8000H` → HL = first number = 37448** 

2. ## **`XCHG` → DE = HL = 37448 (first number saved in DE)** 

3. ## **`LHLD 8002H` → HL = second number = 8859** 

4. ## **`SHLD 8000H` → Store HL at 8000H–8001H → memory now holds:** 

   * ## **8000H = 155 (LSB of second number)** 

   * ## **8001H = 34 (MSB of second number)** 

5. ## **`XCHG` → HL = DE = 37448 (first number back in HL)** 

6. ## **`SHLD 8002H` → Store HL at 8002H–8003H → memory now holds:** 

   * ## **8002H = 72 (LSB of first number)** 

   * ## **8003H = 146 (MSB of first number)** 

## **✅ Numbers are swapped in memory.**

7. ## **`HLT` → Stop execution** 

## ---

## **Final Memory (Decimal)**

| Address | Data | Meaning |
| ----- | ----- | ----- |
| **8000H** | **155** | **LSB of second number (now first)** |
| **8001H** | **34** | **MSB of second number (now first)** |
| **8002H** | **72** | **LSB of first number (now second)** |
| **8003H** | **146** | **MSB of first number (now second)** |

## ---

## **🔹Step-by-Step Logic**

1. **`LHLD 8000H`**

   * **Load 16-bit number from 8000H–8001H into HL.**

2. **`XCHG`**

   * **Exchange HL ↔ DE.**

   * **DE now has the first number.**

3. **`LHLD 8002H`**

   * **Load 16-bit number from 8002H–8003H into HL.**

4. **`SHLD 8000H`**

   * **Store HL (second number) at 8000H–8001H.**

   * **Effectively, first number’s place now has second number.**

5. **`XCHG`**

   * **Swap HL ↔ DE again.**

   * **HL now holds first number.**

6. **`SHLD 8002H`**

   * **Store HL (first number) at 8002H–8003H.**

   * **Now numbers are swapped in memory.**

7. **`HLT`**

   * **Stop program.**

---

### **🔹Core Logic (One Line)**

**Swaps two 16-bit numbers stored in memory.**

---

### **🔹Registers Used**

* **HL – holds one number for load/store operations**

* **DE – temporarily holds the other number during swap**

---

### **🔹Mnemonics Used**

| Mnemonic | Function |
| ----- | ----- |
| **LHLD** | **Load 16-bit data from memory to HL** |
| **XCHG** | **Exchange HL and DE** |
| **SHLD** | **Store HL contents to memory** |
| **HLT** | **Halt execution** |

