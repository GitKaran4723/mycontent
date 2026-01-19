# **Error Detecting and Correcting Codes**

---

## **1\. Need for Error Control in Computer Architecture**

In computer systems, data errors may occur due to:

* Electrical noise in **system buses**

* **Memory cell leakage** or manufacturing defects

* **Cosmic radiation** affecting RAM bits

* High-speed operation and voltage scaling

* Long-term storage degradation

Since errors can cause **system crashes, wrong computations, or data corruption**, computer architecture uses **error detecting and correcting codes** at **hardware level**.

---

## **2\. Where EDC and ECC are used in a Computer System**

| Component | Error Control Used |
| ----- | ----- |
| Main Memory (RAM) | Hamming Code, SECDED |
| Cache Memory | Parity / ECC |
| System Buses | Parity, CRC |
| Secondary Storage (Disk/SSD) | CRC, Reed–Solomon |
| Processor Registers | Parity |
| I/O Devices | CRC, Checksum |

---

## **3\. Error Detecting Codes in Computer Architecture**

Error detecting codes **identify errors** but rely on **re-execution or retransmission**.

---

### **3.1 Parity Bit (Most Common in Hardware)**

#### **Concept:**

* One extra bit added to each word

* Ensures even or odd number of 1s

#### **Example:**

`Data word (8 bits): 10101100`  
`Parity bit (even):  1`  
`Stored word:        101011001`

#### **Usage in Architecture:**

* Cache tags

* CPU registers

* Address and data buses

#### **Advantages:**

✔ Simple hardware  
 ✔ Low cost

#### **Limitation:**

✖ Cannot detect even number of bit errors  
 ✖ No correction

---

### **3.2 Parity on System Buses**

* Used during data transfer between:

  * CPU ↔ Memory

  * CPU ↔ I/O devices

* If parity fails:

  * Bus error interrupt is generated

---

### **3.3 Cyclic Redundancy Check (CRC)**

#### **Usage:**

* Disk controllers

* Network interface cards

* I/O subsystems

#### **Architectural Role:**

* Ensures **data integrity** during block transfers

* Implemented in hardware using shift registers

✔ Detects burst errors  
 ✖ Not used for correction in memory due to complexity

---

## **4\. Error Correcting Codes in Computer Architecture**

Error correcting codes are **crucial for memory reliability**.

---

### **4.1 Hamming Code (Memory ECC)**

#### **Why Hamming Code?**

* Memory errors are usually **single-bit**

* Hamming code corrects **1-bit errors**

#### **Working Principle:**

* Add multiple parity bits

* Parity bits stored with each memory word

#### **Formula:**

`2^r ≥ k + r + 1`

where  
 `k` = data bits, `r` = parity bits

#### **Example:**

* 64-bit data → 8 parity bits → 72-bit memory word

---

### **4.2 SECDED (Single Error Correction, Double Error Detection)**

Used in **modern ECC RAM**.

#### **How:**

* Hamming code \+ 1 overall parity bit

#### **Capabilities:**

✔ Corrects single-bit errors  
 ✔ Detects double-bit errors

#### **Architectural Advantage:**

* Prevents silent data corruption

* Triggers machine check exception on double error

---

## **5\. Memory Architecture with ECC**

### **5.1 ECC Memory Organization**

`| Data Bits (64) | ECC Bits (8) |`

* ECC bits stored in extra memory chips

* Memory controller:

  * Generates ECC during write

  * Checks & corrects during read

---

### **5.2 Memory Read with ECC**

1. Data \+ ECC read from memory

2. Syndrome is computed

3. If:

   * Syndrome = 0 → no error

   * Syndrome ≠ 0 → error detected

4. Single-bit error → corrected on the fly

---

### **5.3 Performance Impact**

* Slight increase in:

  * Memory cost

  * Access latency

* Trade-off for higher reliability

---

## **6\. Cache Memory and Error Control**

* **L1 Cache** → parity (fast, low overhead)

* **L2/L3 Cache** → ECC (higher reliability)

Reason:

* Cache errors affect CPU directly

* Larger caches have higher probability of errors

---

## **7\. Storage Systems and Error Correction**

### **7.1 Hard Disks and SSDs**

* Use **CRC \+ Reed–Solomon / LDPC**

* Errors corrected at **controller level**

### **7.2 RAID Systems**

* RAID adds redundancy

* Uses parity and ECC across disks

---

## **8\. Impact on System Reliability**

Error control improves:

* **MTBF (Mean Time Between Failures)**

* System uptime

* Data integrity in servers and supercomputers

Used heavily in:

* Servers

* Data centers

* Aerospace systems

* Banking systems

---

## **9\. Error Detection vs Error Correction (Architecture View)**

| Aspect | Detection | Correction |
| ----- | ----- | ----- |
| Hardware cost | Low | Higher |
| Delay | Minimal | Slightly higher |
| Usage | Buses, caches | Main memory |
| Example | Parity, CRC | Hamming, SECDED |

---

## **10\. Summary (Exam-Ready)**

* Error detecting and correcting codes are **essential architectural features**

* **Parity** → used for fast detection

* **Hamming/SECDED** → used for reliable memory

* **CRC/Reed–Solomon** → used in storage and I/O

* ECC is implemented in **memory controllers and cache controllers**

