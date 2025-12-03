# **Set Theory Operators** 

### **1\. Use of UNION operator (with union compatibility)**

**Query:**  
> SELECT Sname AS name FROM Supplier  
UNION  
SELECT Pname AS name FROM Part;

**Output:**

| name |
| ----- |
| Vandana |
| Mike |
| Anklesh |
| Ravi |
| Arun |
| Shilpa |
| Kolkesh |
| Alok |
| SiRaj |
| MaRta |
| aRwin |
| NUT |
| BOLT |
| NETSHAFT |
| WASHER |
| BRACKET |
| CHAIN |
| PIN |
| PLUG |
| SPRING |
| NETHER |

---

### **2\. Use of INTERSECT operator (with union compatibility)**

**Query:**  
> SELECT DISTINCT Sname AS name FROM Supplier  
INNER JOIN Part ON Supplier.Sname \= Part.Pname;

**Output:**  
Empty set (no supplier name matches any part name)

---

### **3\. Use of MINUS operator (EXCEPT in SQL)**

MySQL does NOT support MINUS.  
We simulate using LEFT JOIN \+ NULL filter.

Example: Names in Supplier NOT present in Part.

**Query:**  
> SELECT Sname AS name  
FROM Supplier  
LEFT JOIN Part ON Supplier.Sname \= Part.Pname  
WHERE Part.Pname IS NULL;

**Output:**

| name |
| ----- |
| Vandana |
| Mike |
| Anklesh |
| Ravi |
| Arun |
| Shilpa |
| Kolkesh |
| Alok |
| SiRaj |
| MaRta |
| aRwin |

(All supplier names are unique; none match part names.)

---

### **4\. Cartesian product of two tables**

**Query:**  
> SELECT Supplier.Sname, Part.Pname  
FROM Supplier, Part;

**Output** (sample rows):

| Sname | Pname |
| ----- | ----- |
| Vandana | NUT |
| Vandana | BOLT |
| Vandana | NETSHAFT |
| ... | ... |
| aRwin | SPRING |
| aRwin | NETHER |

Total rows \= (number of suppliers) × (number of parts)  
            \= 11 × 10  
            \= 110 rows

---  
