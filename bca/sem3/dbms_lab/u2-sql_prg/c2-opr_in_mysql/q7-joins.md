# **Joins**   


### **1\. INNER JOIN on two tables**

**Query:**  
> SELECT Supplier.Sname, Part.Pname, Supplies.qty  
FROM Supplier  
INNER JOIN Supplies ON Supplier.SID \= Supplies.SID  
INNER JOIN Part ON Supplies.PID \= Part.PID;

**Output:**

| Sname | Pname | qty |
| ----- | ----- | ----- |
| Vandana | NUT | 50 |
| Mike | NETSHAFT | 10 |
| Mike | PLUG | 5 |
| Anklesh | BOLT | 200 |
| Kolkesh | WASHER | 30 |
| Arun | CHAIN | 15 |
| Shilpa | NETSHAFT | 8 |
| Alok | SPRING | 3 |
| MaRta | PIN | 25 |
| aRwin | NETHER | 11 |

---

### **2\. NATURAL JOIN on two tables**

**Query:**  
> SELECT Sname, SID, qty, date\_supplied  
FROM Supplier  
NATURAL JOIN Supplies;

**Output:**

| Sname | SID | qty | date\_supplied |
| ----- | ----- | ----- | ----- |
| Vandana | 200001 | 50 | 2021-01-10 |
| Mike | 200002 | 10 | 2021-01-12 |
| Mike | 200002 | 5 | 2021-01-10 |
| Anklesh | 200003 | 200 | 2000-12-17 |
| Kolkesh | 204001 | 30 | 2000-05-01 |
| Arun | 200005 | 15 | 2021-01-10 |
| Shilpa | 200006 | 8 | 2021-01-10 |
| Alok | 200007 | 3 | 2021-01-10 |
| MaRta | 200009 | 25 | 2021-01-12 |
| aRwin | 200010 | 11 | 2021-01-10 |

---

### **3\. LEFT OUTER JOIN**

**Query:**  
> SELECT Supplier.Sname, Supplies.PID, Supplies.qty  
FROM Supplier  
LEFT JOIN Supplies ON Supplier.SID \= Supplies.SID;

**Output:**

| Sname | PID | qty |
| ----- | ----- | ----- |
| Vandana | 300001 | 50 |
| Mike | 300003 | 10 |
| Mike | 300008 | 5 |
| Anklesh | 300002 | 200 |
| Ravi | NULL | NULL |
| Arun | 300006 | 15 |
| Shilpa | 300003 | 8 |
| Kolkesh | 300004 | 30 |
| Alok | 300009 | 3 |
| SiRaj | NULL | NULL |
| MaRta | 300007 | 25 |
| aRwin | 300010 | 11 |

---

### **4\. RIGHT OUTER JOIN**

**Query:**  
> SELECT Supplier.Sname, Supplies.PID, Supplies.qty  
FROM Supplier  
RIGHT JOIN Supplies ON Supplier.SID \= Supplies.SID;

**Output:**

| Sname | PID | qty |
| ----- | ----- | ----- |
| Vandana | 300001 | 50 |
| Mike | 300003 | 10 |
| Mike | 300008 | 5 |
| Anklesh | 300002 | 200 |
| Kolkesh | 300004 | 30 |
| Arun | 300006 | 15 |
| Shilpa | 300003 | 8 |
| Alok | 300009 | 3 |
| MaRta | 300007 | 25 |
| aRwin | 300010 | 11 |

---

### **5\. FULL OUTER JOIN**

**Query:**  
> SELECT Supplier.Sname, Supplies.PID, Supplies.qty  
FROM Supplier  
LEFT JOIN Supplies ON Supplier.SID \= Supplies.SID  
UNION  
SELECT Supplier.Sname, Supplies.PID, Supplies.qty  
FROM Supplier  
RIGHT JOIN Supplies ON Supplier.SID \= Supplies.SID;

**Output:**

| Sname | PID | qty |
| ----- | ----- | ----- |
| Vandana | 300001 | 50 |
| Mike | 300003 | 10 |
| Mike | 300008 | 5 |
| Anklesh | 300002 | 200 |
| Ravi | NULL | NULL |
| Arun | 300006 | 15 |
| Shilpa | 300003 | 8 |
| Kolkesh | 300004 | 30 |
| Alok | 300009 | 3 |
| SiRaj | NULL | NULL |
| MaRta | 300007 | 25 |
| aRwin | 300010 | 11 |


