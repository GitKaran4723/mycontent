# **DML Commands**

 **1\. Insert at least 10 records in tables supplier, part and supplies** 

i) Supplier

> INSERT INTO Supplier VALUES  
(200001, 'Vandana', 'local', 'Mumbai', '9876543210'),     
(200002, 'Mike', 'global', 'Delhi', '9123456780'),  
(200003, 'Anklesh', 'local', 'Ahmedabad', '8000123456'),   
(200004, 'Ravi', 'local', 'Delhi', '7890123456'),         
(200005, 'Arun', 'global', 'Agra', '7012345678'),        
(200006, 'Shilpa', 'local', 'Chennai', '7011112222'),  
(204001, 'Kolkesh', 'regional', 'Patna', '7000000001'),   
(200007, 'Alok', 'local', 'Delhi', '7002223333'),       
(200008, 'SiRaj', 'regional', 'Bangalore', '7003334444'),  
(200009, 'MaRta', 'global', 'Kolkata', '7004445555'),  
(200010, 'aRwin', 'regional', 'Hyderabad', '7005556666'); 

**OUTPUT:**

Query OK, 11 rows affected (Supplier)

--- 
ii) Parts

> INSERT INTO Parts VALUES  
(300001, 'NUT', 'red', 50.00),  
(300002, 'BOLT', 'green', 120.00),  
(300003, 'NETSHAFT', 'green', 500.00),  
(300004, 'WASHER', 'blue', 30.00),  
(300005, 'BRACKET', 'red', 400.00),  
(300006, 'CHAIN', 'green', 500.00),  
(300007, 'PIN', 'red', 400.00),  
(300008, 'PLUG', 'yellow', 250.00),  
(300009, 'SPRING', 'green', 600.00),  
(300010, 'NETHER', 'black', 220.00);

**OUTPUT:**

Query OK, 10 rows affected (Part)

---

iii) Supplies

> INSERT INTO Supplies VALUES  
(200001, 300001, 50, '2021-01-10'),  
(200002, 300003, 10, '2021-01-12'),  
(200002, 300008, 5, '2021-01-10'),  
(200003, 300002, 200, '2000-12-17'),  
(204001, 300004, 30, '2000-05-01'),  
(200005, 300006, 15, '2021-01-10'),  
(200006, 300003, 8, '2021-01-10'),  
(200007, 300009, 3, '2021-01-10'),  
(200009, 300007, 25, '2021-01-12'),  
(200010, 300010, 11, '2021-01-10');

**OUTPUT:**

Query OK, 10 rows affected (Supplies)

---

**2\. Show contents of Supplier, Part, Supplies.**

i) Supplier

> SELECT \* FROM Supplier;

**OUTPUT:**  
 

| SID | Sname | branch | city | phone |
| ----- | ----- | ----- | ----- | ----- |
| 200001 | Vandana | local | Mumbai | 9876543210 |
| 200002 | Mike | global | Delhi | 9123456780 |
| 200003 | Anklesh | local | Ahmedabad | 8000123456 |
| 200004 | Ravi | local | Delhi | 7890123456 |
| 200005 | Arun | global | Agra | 7012345678 |
| 200006 | Shilpa | local | Chennai | 7011112222 |
| 204001 | Kolkesh | regional | Patna | 7000000001 |
| 200007 | Alok | local | Delhi | 7002223333 |
| 200008 | SiRaj | regional | Bangalore | 7003334444 |
| 200009 | MaRta | global | Kolkata | 7004445555 |
| 200010 | aRwin | regional | Hyderabad | 7005556666 |

---

ii) Parts

**Query:**  
> SELECT \* FROM Part;

**Output:**  
 

| PID | Pname | color | price |
| ----- | ----- | ----- | ----- |
| 300001 | NUT | red | 50.00 |
| 300002 | BOLT | green | 120.00 |
| 300003 | NETSHAFT | green | 500.00 |
| 300004 | WASHER | blue | 30.00 |
| 300005 | BRACKET | red | 400.00 |
| 300006 | CHAIN | green | 500.00 |
| 300007 | PIN | red | 400.00 |
| 300008 | PLUG | yellow | 250.00 |
| 300009 | SPRING | green | 600.00 |
| 300010 | NETHER | black | 220.00 |

---

iii) Supplies

**Query:**  
> SELECT \* FROM Supplies;

**Output:**

| SID | PID | qty | date\_supplied |
| ----- | ----- | ----- | ----- |
| 200001 | 300001 | 50 | 2021-01-10 |
| 200002 | 300003 | 10 | 2021-01-12 |
| 200002 | 300008 | 5 | 2021-01-10 |
| 200003 | 300002 | 200 | 2000-12-17 |
| 204001 | 300004 | 30 | 2000-05-01 |
| 200005 | 300006 | 15 | 2021-01-10 |
| 200006 | 300003 | 8 | 2021-01-10 |
| 200007 | 300009 | 3 | 2021-01-10 |
| 200009 | 300007 | 25 | 2021-01-12 |
| 200010 | 300010 | 11 | 2021-01-10 |
---

**3\. Find the name and city of all suppliers**

**Query:**  
> SELECT Sname, city FROM Supplier;

**Output:**

| Sname | city |
| ----- | ----- |
| Vandana | Mumbai |
| Mike | Delhi |
| Anklesh | Ahmedabad |
| Ravi | Delhi |
| Arun | Agra |
| Shilpa | Chennai |
| Kolkesh | Patna |
| Alok | Delhi |
| SiRaj | Bangalore |
| MaRta | Kolkata |
| aRwin | Hyderabad |

---

**4\. Find the name and phoneno of all suppliers who stay in 'Delhi'**

**Query:**  
> SELECT Sname, phone FROM Supplier WHERE city \= 'Delhi';

**Output:**

| Sname | phone |
| ----- | ----- |
| Mike | 9123456780 |
| Ravi | 7890123456 |
| Alok | 7002223333 |
 
 ---

**5\. Find all distinct branches of suppliers**

**Query:**  
> SELECT DISTINCT branch FROM Supplier;

**Output:**

| branch |
| ----- |
| local |
| global |
| regional |

---

**6\. Delete the record of the supplier whose SID is 204001**

**Query:**  
> DELETE FROM Supplier WHERE SID \= 204001;

**Output:**  
Query OK, 1 row affected

> SELECT \* FROM Supplier;

| SID | Sname | branch | city | phone |
| ----- | :---: | :---: | :---: | :---: |
|       200001 | Vandana | local | Mumbai | 9876543210 |
| 200002 | Mike | global | Delhi | 9123456780 |
| 200003 | Anklesh | local | Ahmedabad | 8000123456 |
| 200004 | Ravi | local | Delhi | 7890123456 |
| 200005 | Arun | global | Agra | 7012345678 |
| 200006 | Shilpa | local | Chennai | 7011112222 |
| 200007 | Alok | local | Delhi | 7002223333 |
| 200008 | SiRaj | regional | Bangalore | 7003334444 |
| 200009 | MaRta | global | Kolkata | 7004445555 |
| 200010 | aRwin | regional | Hyderabad | 7005556666 |

---

**7\. Delete all records of supplier table**

**Query:**  
> DELETE FROM Supplier;

> SELECT \* FROM Supplier;

**Output:**  
Query OK, 11 rows affected

Empty set (0.00 sec)

---

**8\. Delete all suppliers whose city starts with capital A**

**Query:**  
> DELETE FROM Supplier WHERE city LIKE 'A%';

**Output:**  
Query OK, 2 rows affected

| SID | Sname | branch | city | phone |
| ----- | ----- | ----- | ----- | ----- |
| 200001 | Vandana | local | Mumbai | 9876543210 |
| 200002 | Mike | global | Delhi | 9123456780 |
| 200004 | Ravi | local | Delhi | 7890123456 |
| 200006 | Shilpa | local | Chennai | 7011112222 |
| 204001 | Kolkesh | regional | Patna | 7000000001 |
| 200007 | Alok | local | Delhi | 7002223333 |
| 200008 | SiRaj | regional | Bangalore | 7003334444 |
| 200009 | MaRta | global | Kolkata | 7004445555 |
| 200010 | aRwin | regional | Hyderabad | 7005556666 |
---

**9\. Find the supplier names which have 'lk' in any position**

**Query:**  
> SELECT Sname FROM Supplier WHERE Sname LIKE '%lk%';

**Output:**

| Sname |
| ----- |
| Kolkesh |
---

**10\. Find the supplier names where 'R' is in the second position**

**Query:**  
> SELECT Sname FROM Supplier WHERE Sname LIKE '\_ R%';

**Output:**

| Sname |
| ----- |
| aRwin |

---

**11\. Find the supplier name starting with 'V' and ending with 'A'**

**Query:**  
> SELECT Sname FROM Supplier WHERE Sname LIKE 'V%a';

**Output:**

| Sname |
| ----- |
| Vandana |

---

**12\. Change the city of all suppliers to 'BOMBAY**'

**Query:**  
> UPDATE Supplier SET city='BOMBAY';

**Output:**  
Query OK, 11 rows affected

SELECT Sname, city FROM Supplier;

| Name | City |
| ----- | ----- |
| Vandana | BOMBAY |
| Mike | BOMBAY |
| Anklesh | BOMBAY |
| Ravi | BOMBAY |
| Arun | BOMBAY |
| Shilpa | BOMBAY |
| Kolkesh | BOMBAY |
| Alok | BOMBAY |
| SiRaj | BOMBAY |
| MaRta | BOMBAY |
| aRwin | BOMBAY |

---

**13\. Change the city of supplier 'Vandana' to 'Goa'**

**Query:**  
> UPDATE Supplier SET city='Goa' WHERE Sname='Vandana';

**Output:**  
Query OK, 1 row affected

SELECT Sname, city FROM Supplier WHERE Sname='Vandana';

| Name | Location |
| ----- | ----- |
| Vandana | Goa |

---
