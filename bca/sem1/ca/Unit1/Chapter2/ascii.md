# **Character Encoding Schemes**

## **ASCII, EBCDIC, and UNICODE (Complete Explanation)**

---

## **1\. Introduction to Character Encoding**

### **What is Character Encoding?**

**Character Encoding** is a method used by computers to **represent characters (letters, digits, symbols)** using **binary numbers**.

Since computers understand only **0s and 1s**, each character is assigned a **unique numeric code**, which is then stored or transmitted as binary.

---

### **Why Character Encoding is Needed**

* Store text in **memory**

* Display characters on **screens**

* Transmit data over **networks**

* Ensure **compatibility between systems**

---

## **2\. ASCII (American Standard Code for Information Interchange)**

---

### **2.1 Definition**

**ASCII** is a **7-bit character encoding standard** developed to represent English characters and control symbols.

**ASCII = American Standard Code for Information Interchange**

---

### **2.2 History**

* Developed in **1963**

* Standardized by **ANSI (American National Standards Institute)**

* Widely used in early computers and communication systems

---

### **2.3 Size and Structure**

* Uses **7 bits**

Total possible characters:

 `2⁷ = 128 characters`

* 

Binary values range from:

 `0000000 (0) to 1111111 (127)`

* 

---

### **2.4 ASCII Character Categories**

#### **1\. Control Characters (0–31 and 127\)**

Non-printable characters used to control devices.

| Decimal | Abbreviation | Full Form | Purpose |
| ----- | ----- | ----- | ----- |
| 0 | NUL | Null | End of string |
| 7 | BEL | Bell | Alert sound |
| 8 | BS | Backspace | Cursor move |
| 9 | HT | Horizontal Tab | Tab space |
| 10 | LF | Line Feed | New line |
| 13 | CR | Carriage Return | Line start |
| 27 | ESC | Escape | Control sequences |
| 127 | DEL | Delete | Delete character |

---

#### **2\. Printable Characters (32–126)**

Includes:

* Alphabets (A–Z, a–z)

* Digits (0–9)

* Symbols (+, \-, %, $, etc.)

* Space (32)

---

### **2.5 Extended ASCII**

* Uses **8 bits**

Total characters:

 `2⁸ = 256`

*   
* Codes 128–255 used for:

  * Accented characters

  * Special symbols

* **Not standardized** (varies by system)

---

### **2.6 Advantages of ASCII**

✔ Simple  
 ✔ Efficient for English text  
 ✔ Widely supported

---

### **2.7 Limitations of ASCII**

✖ Cannot represent non-English languages  
 ✖ Limited number of characters  
 ✖ Inadequate for global communication

---

## **3\. EBCDIC (Extended Binary Coded Decimal Interchange Code)**

---

### **3.1 Definition**

**EBCDIC** is an **8-bit character encoding scheme** developed by **IBM**.

**EBCDIC = Extended Binary Coded Decimal Interchange Code**

---

### **3.2 History**

* Introduced in **1964**

* Used mainly in **IBM mainframe systems**

* Derived from **BCD (Binary Coded Decimal)**

---

### **3.3 Size and Structure**

* Uses **8 bits**

Total characters:

 `2⁸ = 256`

* 

---

### **3.4 Character Organization**

Unlike ASCII:

* Characters are **not in sequential order**

* Alphabets are scattered

Example:

* 'A'–'I', 'J'–'R', 'S'–'Z' are in different ranges

---

### **3.5 Control Characters**

Includes:

* NUL (Null)

* LF (Line Feed)

* CR (Carriage Return)

* HT (Horizontal Tab)

---

### **3.6 Advantages of EBCDIC**

✔ Supports more characters than ASCII  
 ✔ Optimized for IBM hardware

---

### **3.7 Limitations of EBCDIC**

✖ Not compatible with ASCII  
 ✖ Complex character ordering  
 ✖ Rare outside IBM systems

---

### **3.8 Usage**

* IBM mainframes

* Legacy banking systems

* Large enterprise servers

---

## **4\. UNICODE (Universal Character Encoding)**

---

### **4.1 Definition**

**UNICODE** is a **universal character encoding standard** designed to represent **every character of every language**.

**UNICODE = Universal Code (not an acronym officially)**

---

### **4.2 Motivation for Unicode**

ASCII and EBCDIC failed to support:

* Non-English languages

* Multiple scripts

* Emojis

* Mathematical symbols

Unicode solves **global language representation**.

---

### **4.3 Unicode Character Set**

* Over **1,100,000 code points**

Written as:

 `U+XXXX`

* 

Example:

* A → U+0041

* अ → U+0905

* 😀 → U+1F600

---

### **4.4 Unicode Terminology (Important)**

| Term | Meaning |
| ----- | ----- |
| Code Point | Unique number assigned to a character |
| Glyph | Visual representation of a character |
| Script | Writing system (Latin, Devanagari) |
| Plane | Group of code points |

---

### **4.5 Unicode Planes**

| Plane | Range | Purpose |
| ----- | ----- | ----- |
| BMP | U+0000–U+FFFF | Basic characters |
| SMP | U+10000–U+1FFFF | Emojis, symbols |
| SIP | U+20000–U+2FFFF | Rare scripts |
| SSP | U+E0000–U+EFFFF | Special use |

---

## **5\. Unicode Encoding Forms (Very Important)**

Unicode defines **how code points are stored in memory**.

---

### **5.1 UTF-8 (Unicode Transformation Format – 8 bit)**

* Variable length: **1–4 bytes**

* ASCII compatible

* Most popular encoding

Example:

* A → 1 byte

* हिंदी → 3 bytes per character

✔ Efficient  
 ✔ Backward compatible  
 ✔ Used on web, Linux, HTML

---

### **5.2 UTF-16**

* Uses **2 or 4 bytes**

* Uses **surrogate pairs**

Used in:

* Windows

* Java

---

### **5.3 UTF-32**

* Fixed **4 bytes**

* Simple but memory inefficient

Used in:

* Internal processing

---

## **6\. Comparison of ASCII, EBCDIC, and UNICODE**

| Feature | ASCII | EBCDIC | UNICODE |
| ----- | ----- | ----- | ----- |
| Full form | American Standard Code for Information Interchange | Extended Binary Coded Decimal Interchange Code | Universal Code |
| Bits used | 7 (8 extended) | 8 | Variable |
| Characters | 128 | 256 | 1M+ |
| Language support | English only | Limited | All languages |
| Compatibility | Universal | IBM only | Universal |
| Usage | Legacy systems | Mainframes | Modern systems |

---

## **7\. Use in Computer Architecture**

| Component | Encoding |
| ----- | ----- |
| Registers | ASCII / Unicode |
| Memory | Unicode (UTF-8/16) |
| File systems | Unicode |
| I/O devices | ASCII / Unicode |
| Networks | UTF-8 |

---

## **8\. Summary (Exam-Ready Points)**

* **ASCII**: 7-bit, English characters

* **EBCDIC**: 8-bit, IBM-specific

* **UNICODE**: Universal, multilingual

* UTF-8 is the **most widely used encoding**

* Unicode ensures **platform and language independence**

---

## **9\. Abbreviations List (Quick Revision)**

| Abbreviation | Full Form |
| ----- | ----- |
| ASCII | American Standard Code for Information Interchange |
| EBCDIC | Extended Binary Coded Decimal Interchange Code |
| Unicode | Universal Code |
| UTF | Unicode Transformation Format |
| ANSI | American National Standards Institute |
| BCD | Binary Coded Decimal |
| BMP | Basic Multilingual Plane |
| SMP | Supplementary Multilingual Plane |
| SIP | Supplementary Ideographic Plane |
| SSP | Supplementary Special-purpose Plane |
| NUL | Null |
| LF | Line Feed |
| CR | Carriage Return |
| HT | Horizontal Tab |

