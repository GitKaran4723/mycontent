

# Summary of approach (one-line)

We add digits from least significant (units) to most significant (thousands) using `ADC` (add with carry) and `DAA` (Decimal Adjust Accumulator) so BCD carries are handled correctly; final carry (if any) is stored as the 5th digit.

---

# Data layout (fixed addresses used in program)

* **First 4-digit BCD number** (each byte = one BCD digit; LSD first)

  * 8000H → units (digit 0)
  * 8001H → tens  (digit 1)
  * 8002H → hundreds (digit 2)
  * 8003H → thousands (digit 3)

* **Second 4-digit BCD number**

  * 8004H → units
  * 8005H → tens
  * 8006H → hundreds
  * 8007H → thousands

* **Result (5 bytes to allow overflow)** (LSD first)

  * 8010H → units (result digit 0)
  * 8011H → tens
  * 8012H → hundreds
  * 8013H → thousands
  * 8014H → ten-thousands (will be 00 or 01)

> Note: Each memory byte must contain a valid BCD digit 00h–09h. If input digits exceed 9, results are undefined.

---

# Registers used — meaning & role

* **A (Accumulator)** — used to load one digit and hold arithmetic result.
* **B** — temporary storage for the other operand digit before addition.
* **HL (via LDA/STA absolute instructions)** — we use absolute load/store instructions (LDA/STA) so HL pair need not be used as pointers; we use fixed addresses.
* **Flags** — Carry flag is used across digit additions; `DAA` updates the carry appropriately for BCD.

---

# Important instructions & remarks (short table)

| Instruction             |                     Meaning / why used here | Remarks                                                                                                |
| ----------------------- | ------------------------------------------: | ------------------------------------------------------------------------------------------------------ |
| `LDA addr`              |                    Load A from memory[addr] | Used to fetch a digit from absolute address.                                                           |
| `STA addr`              |                   Store A into memory[addr] | Save result digit.                                                                                     |
| `MOV r, A` / `MOV A, r` |       Move between accumulator and register | Save one digit temporarily in B: `MOV B,A`.                                                            |
| `ADC r`                 |             A ← A + r + CY (add with carry) | Adds second digit plus previous carry — required for multi-digit addition.                             |
| `DAA`                   | Decimal Adjust Accumulator after binary add | Converts result in A to correct BCD and sets carry if needed. Must be used after each digit addition.  |
| `STC` / `CMC`           |                Set Carry / Complement Carry | We use `STC` followed by `CMC` to reliably clear carry before starting. (8085 has no direct CLR carry) |
| `HLT`                   |                                    Halt CPU | End of program.                                                                                        |

---

# How the algorithm works (step-by-step)

1. Clear carry (make sure carry = 0 before starting).
2. For each digit position from units → thousands:

   * Load digit of number1 into A.
   * Save it into B.
   * Load corresponding digit of number2 into A.
   * `ADC B` to add (digit2 + digit1 + carry).
   * `DAA` to convert to proper BCD result and set/clear carry.
   * `STA` store the adjusted BCD digit into the result location.
3. After the 4th digit, check carry flag — store 00h or 01h at 8014H accordingly.
4. Halt.

---

# Example (if you want to test)

If memory contains:

* Number1 (8003..8000) = 1  2  3  4  (i.e., 1234 stored as 4 bytes: 04→units,03→hundreds? — careful with order)

  * We store LSD at 8000H: 04h at 8000H, 03? Wait—clear mapping below in code example.

To avoid confusion: **we store digits LSD-first**. So `1234` should be stored as:

* 8000H = 04h (units)
* 8001H = 03h? No — that's wrong: correct digits for 1234 are units=4, tens=3, hundreds=2, thousands=1:

  * 8000H = 04h (units)
  * 8001H = 03h (tens)
  * 8002H = 02h (hundreds)
  * 8003H = 01h (thousands)

If other number is 8765 then:

* 8004H = 05h, 8005H = 06h, 8006H = 07h, 8007H = 08h.

Result will be 9999? Actually 1234 + 8765 = 9999, stored as:

* 8010H=09h, 8011H=09h, 8012H=09h, 8013H=09h, 8014H=00h.

---

# Full commented 8085 program (unpacked BCD, absolute addresses)

```
; ---------------------------------------------------------
; 8085 program : 4-digit BCD addition (unpacked digits)
; Inputs:
;   First number  (4 digits)  stored at 8000H..8003H (LSD → MSD)
;   Second number (4 digits)  stored at 8004H..8007H (LSD → MSD)
; Output:
;   Result (5 digits) stored at 8010H..8014H (LSD → MSD)
;   (8014H will be 00 or 01 depending on overflow)
; ---------------------------------------------------------

        ORG 0000H

START:  
        ; Ensure carry = 0 (clear carry)
        STC             ; set carry = 1
        CMC             ; complement carry -> now carry = 0 (reliable clear)

; --------- DIGIT 0 (units) ----------
        LDA 8000H       ; A = digit1_units
        MOV B, A        ; B = digit1_units (save temporarily)
        LDA 8004H       ; A = digit2_units
        ADC B           ; A = digit2_units + digit1_units + carry
        DAA             ; adjust for BCD, sets carry if sum > 9
        STA 8010H       ; store units result

; --------- DIGIT 1 (tens) -----------
        LDA 8001H       ; A = digit1_tens
        MOV B, A        ; B = digit1_tens
        LDA 8005H       ; A = digit2_tens
        ADC B           ; add with carry from previous digit
        DAA             ; BCD adjust (updates carry)
        STA 8011H       ; store tens result

; --------- DIGIT 2 (hundreds) -------
        LDA 8002H       ; A = digit1_hundreds
        MOV B, A        ; B = digit1_hundreds
        LDA 8006H       ; A = digit2_hundreds
        ADC B           ; add + carry
        DAA
        STA 8012H       ; store hundreds

; --------- DIGIT 3 (thousands) ------
        LDA 8003H       ; A = digit1_thousands
        MOV B, A        ; B = digit1_thousands
        LDA 8007H       ; A = digit2_thousands
        ADC B           ; add + carry
        DAA
        STA 8013H       ; store thousands

; --------- FINAL CARRY (ten-thousands) -
        ; After last DAA, Carry flag = 1 if overflow to 5th digit
        JC  STORE_ONE   ; if carry set -> store 01h
        MVI A, 00H
        STA 8014H
        JMP DONE

STORE_ONE:
        MVI A, 01H
        STA 8014H

DONE:
        HLT

; ---------------------------------------------------------
; End of program
; ---------------------------------------------------------
```

---

# Notes, tips & things to remember

1. **Digit order (LSD first)**: This program expects LSD at the lowest address (8000H) so the carry propagates naturally from low address to higher addresses.
2. **Valid BCD digits only**: Each input byte must be 00h–09h. If any input byte is >09h, `DAA` behaviour might produce incorrect results.
3. **DAA is essential**: After adding two BCD digits (with possible carry), the raw binary result may not be a valid BCD nibble. `DAA` corrects it and sets the carry for the next digit.
4. **Clearing carry**: 8085 does not have a direct `CLC` instruction. `STC` followed by `CMC` reliably makes carry = 0.
5. **Result length**: We stored 5 result bytes (8010H..8014H) so final overflow is captured (0 or 1).
6. **If you prefer packed BCD** (two decimal digits per byte, high nibble/low nibble), the program needs a different handling (bitwise masks and `DAA` used differently). Tell me if you want a packed-BCD version.
7. **Testing**: Use simple inputs first, e.g., 0001 + 0001 → 0002; 9999 + 0001 → 0000 with carry 1 at 8014H (gives 10000).

---

# Short Revision (one-minute recap)

* We add LSD→MSD with `ADC` and `DAA`.
* Inputs: 8000H..8003H and 8004H..8007H (digits 0..3, LSD first).
* Output: 8010H..8014H (5 digits).
* Clear carry at start (`STC` then `CMC`).
* After each digit add use `DAA` to fix BCD and generate carry for next digit.

