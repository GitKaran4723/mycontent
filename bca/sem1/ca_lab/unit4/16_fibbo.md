# 1) Goal (what the program does)

Generate the first N terms of the Fibonacci series (F0, F1, F2, …) and store them consecutively in memory starting at address 8000H.
Example: if N = 10 the stored sequence will be: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34 (each as an 8-bit number; note: 8-bit overflow after 255).

---

# 2) The assembly program (mnemonics only — easy to read & modify)

```
; -----------------------------
; Fibonacci series - 8085
; Store N terms starting at memory 8000H
; Change MVI B, 0Ah to set N (decimal)
; -----------------------------

MVI B, 0Ah        ; B = N (number of terms to generate)  ; change 0Ah (10 decimal) as needed
MVI C, 00H        ; C = F0 = 0
MVI D, 01H        ; D = F1 = 1
LXI H, 8000H      ; HL points to memory where sequence will be stored

MOV M, C          ; [HL] <- F0  (store first term)
INX H             ; HL = HL + 1
MOV M, D          ; [HL] <- F1  (store second term)
INX H             ; advance pointer after storing second term

; We already stored two terms, so decrement counter by 2
DCR B
DCR B

FIB_LOOP:MOV A, C ; A = previous term (F(n-2))
ADD D             ; A = C + D  -> this is F(n) (sum of last two)
MOV M, A          ; store F(n) at [HL]
INX H             ; HL = HL + 1  (advance store pointer)

MOV C, D          ; shift: previous <- current  (C = old D)
MOV D, A          ; current  <- new sum      (D = A)

DCR B             ; decrement remaining count
JNZ FIB_LOOP      ; if B != 0, generate next term

HLT               ; halt
```

**How to change how many numbers are generated:** edit `MVI B, 0Ah` to the decimal number of terms you want (0Ah = 10). Remember the program decrements B twice after storing the first two terms, so B should be ≥ 2 for meaningful results. If you want to accept N at runtime, you can replace `MVI B, 0Ah` with an input routine (not shown here).

**Limitations:** this stores 8-bit Fibonacci values. Fibonacci numbers grow fast — after F(12) or so they may exceed 255 and wrap around. To generate larger Fibonacci values you must implement 16-bit arithmetic (use HL as a pair) — I can show that if you want.

---

# 3) Meaning of the numbers & registers (plain explanation)

* **N (stored in B):** how many Fibonacci terms to produce. Example `MVI B,0Ah` => produce 10 terms.
* **F0, F1 (C and D):** C holds the older term (F(n-2)), D holds the current term (F(n-1)). We compute next term = C + D.
* **Accumulator A:** used to hold the sum after `ADD D`. We then store `A` to memory and move it into D for the next iteration.
* **HL pair:** used as the memory pointer where the generated sequence is saved. `LXI H, 8000H` sets the start address to 8000H (modify if you prefer another memory area).
* **Memory storage:** each Fibonacci number is stored as one byte at consecutive addresses [8000H], [8001H], [8002H], …

---

# 4) Mnemonics → What they mean & short remarks (table)

| Mnemonic        |                                                Plain meaning (what it does) | Remarks / flags affected                                                             |
| --------------- | --------------------------------------------------------------------------: | ------------------------------------------------------------------------------------ |
| `MVI r, data`   |                Move immediate: put the 8-bit value `data` into register `r` | Loads register with constant. No flags changed.                                      |
| `LXI rp, addr`  |               Load register pair with 16-bit address (e.g., `LXI H, 8000H`) | Sets HL (or BC / DE). No flags changed. Byte order is low then high in machine code. |
| `MOV dest, src` | Copy contents of `src` register into `dest` (or `MOV M, r` copies r → [HL]) | Simple register-to-register or register-to-memory move. No flags changed.            |
| `INX rp`        |                  Increment register pair (e.g., `INX H` increments HL by 1) | No flags changed. Used to advance memory pointer.                                    |
| `DCR r`         |                                                   Decrement register r by 1 | Affects Sign/Zero/Parity; does NOT affect Carry.                                     |
| `ADD r`         |                                 Add register r to accumulator A (A ← A + r) | Affected flags: Z,S,P,AC,CY. Use to compute sum.                                     |
| `JNZ addr`      |                Jump to address if Zero flag = 0 (i.e., previous result ≠ 0) | Conditional loop control.                                                            |
| `HLT`           |                                            Halt CPU until reset / interrupt | Program ends.                                                                        |
| `ORG addr`      |               Assembler directive — set listing origin (not an instruction) | Optional for assembler; not machine opcode.                                          |

> Remark on `MOV M, r`: `M` refers to memory at address in HL. So `MOV M, D` copies register D into memory[HL]. `MOV A, C` copies C into A (accumulator).

---

# 5) Step-by-step execution walk-through (very simple)

1. Put N in B. Put 0 into C and 1 into D (the first two Fibonacci numbers). Point HL to memory area (8000H).
2. Store F0 and F1 to memory, increment HL twice.
3. Reduce the remaining count (B) by two (we already wrote two numbers).
4. Loop: compute sum = C + D (in A). Store sum at [HL]. Move window: C ← D, D ← sum. Decrement counter B. If B ≠ 0 repeat.
5. Halt when done.


---

# 6) Common variations & enhancements

* **Input N at runtime:** replace `MVI B, 0Ah` with a routine to read from port/keyboard or memory.
* **16-bit Fibonacci:** if you need values beyond 255, represent numbers as 16-bit pairs (use DE and HL for data, use `DAD` or add with carry). I can provide full 16-bit version if needed.
* **Store start address elsewhere:** change `LXI H, 8000H` to any safe RAM location in your system.

---
