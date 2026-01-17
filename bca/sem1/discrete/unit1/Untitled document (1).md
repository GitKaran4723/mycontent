u---

### **1\. Definition Recap**

For two sets (A) and (B):  
\[  
A \\times B \= { (a, b) \\mid a \\in A, b \\in B }  
\]  
Each element is an **ordered pair** ((a, b)), where the order matters.

* **Example:**  
  If (A \= {1, 2}) and (B \= {x, y, z}), then  
  \[  
  A \\times B \= {(1,x),(1,y),(1,z),(2,x),(2,y),(2,z)}  
  \]

---

### **2\. Cartesian Product of More than Two Sets**

We can extend to three or more sets:  
\[  
A \\times B \\times C \= {(a,b,c) \\mid a \\in A, b \\in B, c \\in C}  
\]

* **Example:**  
  (A \= {1,2}, B \= {x,y}, C \= {\\alpha,\\beta})  
  Then  
  \[  
  A \\times B \\times C \= {(1,x,\\alpha),(1,x,\\beta),(1,y,\\alpha),(1,y,\\beta),(2,x,\\alpha),\\dots,(2,y,\\beta)}  
  \]  
* **n-fold Cartesian Product:**  
  For a set (X),  
  \[  
  X^n \= X \\times X \\times \\cdots \\times X \\quad (n\\text{ times})  
  \]  
  This is often used to define **n-dimensional spaces**.

---

### **3\. Properties**

1. **Size:**  
   If (|A| \= m) and (|B| \= n), then (|A \\times B| \= mn)  
   In general: (|A\_1 \\times A\_2 \\times \\cdots \\times A\_n| \= |A\_1||A\_2|\\cdots|A\_n|)  
2. **Non-commutative:**  
   (A \\times B \\neq B \\times A) because ((a,b) \\neq (b,a)) in general.  
3. **Empty Set:**  
   If either set is empty, the Cartesian product is empty:  
   (\\emptyset \\times A \= \\emptyset)  
4. **Associative:**  
   ((A \\times B) \\times C) can be identified with (A \\times (B \\times C)) as sets of ordered triples.

---

### **4\. Applications**

1. **Coordinate Systems:**  
   The Cartesian plane is ( \\mathbb{R} \\times \\mathbb{R} \= \\mathbb{R}^2).  
   In 3D, ( \\mathbb{R}^3 \= \\mathbb{R} \\times \\mathbb{R} \\times \\mathbb{R} ).  
2. **Relations:**  
   Any relation (R) from (A) to (B) is a subset of (A \\times B).  
   * Example: (R \= {(1,x), (2,y)} \\subseteq A \\times B)  
3. **Functions:**  
   A function (f: A \\to B) can be seen as a special subset of (A \\times B) where each (a \\in A) appears exactly once as the first element of a pair.  
4. **Databases:**  
   Cartesian products are used in **SQL joins** to combine tables.

---

### **5\. Visual Representation**

For small sets, you can think of (A \\times B) as a **grid/table**:

|  | x | y | z |
| ----- | ----- | ----- | ----- |
| 1 | (1,x) | (1,y) | (1,z) |
| 2 | (2,x) | (2,y) | (2,z) |

Each cell represents an ordered pair.

-$$--
5+8=13
       $$
       
