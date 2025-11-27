# ✅ **8085 Program – First 10 Even & First 10 Odd Numbers**

### 📌 **Storage Plan**

* Store EVEN numbers starting at **8000H**
* Store ODD  numbers starting at **8010H**

(10 numbers each → 10 bytes + 10 bytes)

---

# ✅ **PROGRAM**

```
; --------------------------------------------
; Program to generate first 10 EVEN & ODD numbers
; EVEN stored from 8000H
; ODD  stored from 8010H
; --------------------------------------------

MVI B, 0AH        ; B = 10 numbers (counter)
MVI C, 00H        ; C = current even number (start 0)
LXI H, 8000H      ; HL points to even numbers memory

EVEN_LOOP:MOV M, C    ; store even number
INX H             ; next memory
INR C             ; increase to next even number step 1
INR C             ; increase to next even number step 2  (C += 2)
DCR B             ; one even number stored
JNZ EVEN_LOOP     ; repeat for 10 values

; ---- Now generate ODD numbers ----

MVI B, 0AH        ; B = 10 numbers
MVI C, 01H        ; C = first odd number = 1
LXI H, 8010H      ; start address for odd numbers

ODD_LOOP:MOV M, C          ; store odd number
INX H             ; next memory
INR C             ; next odd number step 1
INR C             ; next odd number step 2  (C += 2)
DCR B             ; decrement counter
JNZ ODD_LOOP      ; loop

HLT               ; stop
```

---

# ✅ **WHAT THE REGISTERS MEAN (very simple)**

| Register | Meaning                                     |
| -------- | ------------------------------------------- |
| **B**    | Counter (10 numbers)                        |
| **C**    | Holds current even/odd number               |
| **HL**   | Memory pointer where numbers will be stored |
| **M**    | Means memory at [HL]                        |

---

# ✅ **NUMBERS GENERATED**

### **Even numbers stored:**

0, 2, 4, 6, 8, 10, 12, 14, 16, 18

### **Odd numbers stored:**

1, 3, 5, 7, 9, 11, 13, 15, 17, 19

---

# ✅ **MNEMONICS (Meaning) — Easy Table**

| Mnemonic        | Meaning                               | Why used here                                   |
| --------------- | ------------------------------------- | ----------------------------------------------- |
| **MVI r, data** | Load register with immediate data     | Set counter (10), C = starting number           |
| **LXI H, addr** | Load HL pair with 16-bit address      | Set storage location                            |
| **MOV M, r**    | Store register value into memory [HL] | Store number                                    |
| **INX H**       | Increment HL pair                     | Move to next memory slot                        |
| **INR r**       | Increment register by 1               | Build next number (we do 2 increments to add 2) |
| **DCR r**       | Decrement register                    | Reduce counter                                  |
| **JNZ label**   | Jump if Zero flag = 0                 | Continue loop until 10 numbers done             |
| **HLT**         | Stop processor                        | End program                                     |

---

