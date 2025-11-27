# 8085 Assembly — Divide two 8-bit numbers (repeated subtraction)

```


; Load HL to point at Dividend (address 4001H)
LXI   H, 4001H     ; HL ← 4001

; Load Dividend into A (A will hold remainder as subtraction proceeds)
MOV   A, M         ; A ← [HL] (dividend at 4001)

; Initialize quotient = 0
MVI   C, 00H       ; C ← 00 (quotient counter)

; Move HL to next address to fetch divisor
INX   H            ; HL ← HL + 1  (now HL points to 4002)

; Load Divisor into B
MOV   B, M         ; B ← [HL] (divisor at 4002)

Loop2:  CMP   B            ; compare A with B (A - B sets flags)
JC    Loop1        ; if carry = 1 (A < B) → division finished

SUB   B            ; A ← A - B  (subtract divisor from remainder)
INR   C            ; C ← C + 1  (increment quotient)
JMP   Loop2        ; repeat subtraction

; When A < B we come here — A contains remainder, C contains quotient
Loop1:  STA   4003H        ; store remainder at memory location 4003H
MOV   A, C         ; move quotient into accumulator
STA   4004H        ; store quotient at memory location 4004H

HLT                ; end program
```

---

# Line-by-line explanation (simple)

* `ORG 0000H`
  — Assembler directive: program origin (start address for listing). Not a CPU instruction.

* `LXI H, 4001H`
  — Load HL with 4001H. We use HL to point to memory where the dividend is stored.

* `MOV A, M`
  — Copy memory[HL] into accumulator A. After `LXI H,4001H`, `M` refers to address 4001H, so this loads the **dividend** into A. A will act as the running remainder.

* `MVI C, 00H`
  — Clear the quotient counter (C = 0). Each successful subtraction increments C.

* `INX H`
  — Increment HL so that HL now points to 4002H (the divisor location).

* `MOV B, M`
  — Load the **divisor** into register B from memory[HL] = 4002H.

* `Loop2: CMP B`
  — Compare A with B (computes A − B internally). This sets flags but doesn’t change registers. If A < B then subtraction would borrow — the Carry flag is set.

* `JC Loop1`
  — Jump to Loop1 if Carry = 1 (that is, A < B). If A < B, no more subtraction possible and division finished.

* `SUB B`
  — Subtract B from A and store result in A: A ← A − B. This reduces the remainder.

* `INR C`
  — Increment C (quotient count). Each successful subtraction increases quotient by 1.

* `JMP Loop2`
  — Repeat comparison and subtraction until A < B.

* `Loop1: STA 4003H`
  — Store remainder (A) into memory at 4003H.

* `MOV A, C`
  — Move quotient (C) into accumulator A so we can store it with `STA`.

* `STA 4004H`
  — Store quotient (A) into memory at 4004H.

* `HLT`
  — Halt CPU — program ends.

---

# What ends up where (I/O / Memory map)

* `4001H` — Input: Dividend (8-bit)
* `4002H` — Input: Divisor  (8-bit)
* `4003H` — Output: Remainder (A stored here at end)
* `4004H` — Output: Quotient  (C stored here at end)

---

# Register roles (quick)

* **A** — holds dividend initially and then running remainder during the loop. Final A is remainder.
* **B** — holds divisor (constant during loop).
* **C** — quotient counter (each subtraction increments C).
* **HL** — temporary pointer to memory (used to load dividend and divisor).

---

# Flags used

* **Carry (CY)** — set by `CMP` (and `SUB`): when A < B leads to borrow, CY = 1. We use `JC` to detect A < B and stop subtraction.
* Other flags (Z, S, P) are affected by `SUB`/`CMP` but not used for control here.

---

# Simple worked example

Suppose memory has:

* `[4001H] = 25` (dividend)
* `[4002H] = 4`  (divisor)

Execution:

* A = 25, B = 4, C = 0
* Loop: 25 ≥ 4 → SUB → A = 21, C = 1
  21 ≥ 4 → SUB → A = 17, C = 2
  17 ≥ 4 → SUB → A = 13, C = 3
  13 ≥ 4 → SUB → A = 9,  C = 4
  9  ≥ 4 → SUB → A = 5,  C = 5
  5  ≥ 4 → SUB → A = 1,  C = 6
  1  < 4 → CMP sets CY = 1 → JC Loop1
* Store remainder (A=1) at 4003H, store quotient (C=6) at 4004H.

Result: Quotient = 6, Remainder = 1.

---

# Edge cases & important notes

1. **Divisor = 0**: This program does not check for divide-by-zero. If divisor at 4002H is 0, `CMP B` where B=0 is fine, but `SUB B` will subtract 0 repeatedly and cause an infinite loop (C keeps incrementing until it overflows). Add a check `MVI A,00 / CMP B / JZ DIV_BY_ZERO` if you need to trap this case.

2. **Quotient overflow**: Quotient stored in register C is 8-bit (0–255). If dividend is large and divisor small, quotient may exceed 255 — register C will wrap around. For typical 8-bit ÷ 8-bit with unsigned values, quotient ≤ 255 only if dividend ≤ 65535; but since dividend is 8-bit (0–255) and divisor ≥1, quotient ≤255 — safe. (But if program were modified for multi-byte dividend, watch overflow.)

3. **Signed numbers**: This routine assumes unsigned numbers. For signed division, different handling required.

4. **Performance**: Repeated subtraction is simple but slow for large quotients. For learning and lab exercises it’s fine.

---

# Quick revision (one-minute)

* Loads dividend from 4001H into A, divisor from 4002H into B.
* Repeatedly subtract divisor from A; each subtraction increments C (quotient).
* Stop when A < B (detected by `CMP` + `JC`).
* Store remainder at 4003H and quotient at 4004H.
* Registers: A = remainder, B = divisor, C = quotient, HL = pointer.

