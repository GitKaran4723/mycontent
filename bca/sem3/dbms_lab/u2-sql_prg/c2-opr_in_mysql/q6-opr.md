# **Queries on Operators**  


**1\. Find the pname, phoneno and cost of parts which have cost \>= 200 AND \<= 600**

**Query:**  
>SELECT p.Pname, s.phone, p.price  
FROM Part p  
JOIN Supplies sp ON p.PID \= sp.PID  
JOIN Supplier s ON sp.SID \= s.SID  
WHERE p.price \>= 200 AND p.price \<= 600;

**Output:**

| Pname | phone | price |
| ----- | ----- | ----- |
| NETSHAFT | 9123456780 | 500.00 |
| NETSHAFT | 7011112222 | 500.00 |
| CHAIN | 7012345678 | 500.00 |
| PIN | 7004445555 | 400.00 |
| PLUG | 9123456780 | 250.00 |
| SPRING | 7002223333 | 600.00 |
| NETHER | 7005556666 | 220.00 |

---

**2\. Find the sname, SID and branch of suppliers who are in 'local' branch or 'global' branch**

**Query:**  
>SELECT Sname, SID, branch FROM Supplier WHERE branch IN ('local','global');

**Output:**

| Sname | SID | branch |
| ----- | ----- | ----- |
| Vandana | 200001 | local |
| Mike | 200002 | global |
| Anklesh | 200003 | local |
| Ravi | 200004 | local |
| Arun | 200005 | global |
| Shilpa | 200006 | local |
| Alok | 200007 | local |
| MaRta | 200009 | global |

---

**3\. Find the pname, phoneno and cost of parts for which cost is BETWEEN 200 AND 600**

**Query:**  
> SELECT p.Pname, s.phone, p.price  
FROM Part p  
JOIN Supplies sp ON p.PID \= sp.PID  
JOIN Supplier s ON sp.SID \= s.SID  
WHERE p.price BETWEEN 200 AND 600;

**Output:**

| Pname | phone | price |
| ----- | ----- | ----- |
| NETSHAFT | 9123456780 | 500.00 |
| NETSHAFT | 7011112222 | 500.00 |
| CHAIN | 7012345678 | 500.00 |
| PIN | 7004445555 | 400.00 |
| PLUG | 9123456780 | 250.00 |
| SPRING | 7002223333 | 600.00 |
| NETHER | 7005556666 | 220.00 |

---

**4\. Find the pname and color of parts, which has the word 'NET' anywhere in its pname**

**Query:**  
> SELECT Pname, color FROM Part WHERE Pname LIKE '%NET%';

**Output:**

| Pname | color |
| ----- | ----- |
| NETSHAFT | green |
| NETHER | black |

---

**5\. Find the PID and pname of parts with pname either 'NUT' or 'BOLT'**

**Query:**  
> SELECT PID, Pname FROM Part WHERE Pname IN ('NUT','BOLT');

**Output:**

| PID | Pname |
| ----- | ----- |
| 300001 | NUT |
| 300002 | BOLT |

---

**6\. List the suppliers who supplied parts on '2000-05-01', '2021-01-12', '2000-12-17', '2021-01-10'**

**Query:**  
> SELECT DISTINCT s.Sname, s.SID  
FROM Supplier s  
JOIN Supplies sp ON s.SID \= sp.SID  
WHERE sp.date\_supplied IN ('2000-05-01','2021-01-12','2000-12-17','2021-01-10')  
ORDER BY s.SID;

**Output:** 
 

| Sname | SID |
| ----- | ----- |
| Vandana | 200001 |
| Mike | 200002 |
| Anklesh | 200003 |
| Arun | 200005 |
| Shilpa | 200006 |
| Alok | 200007 |
| MaRta | 200009 |
| aRwin | 200010 |
| Kolkesh | 204001 |

---

**7\. Find all the distinct costs of parts**

**Query:**  
> SELECT DISTINCT price FROM Part ORDER BY price;

**Output:**

| price |
| ----- |
| 30.00 |
| 50.00 |
| 120.00 |
| 220.00 |
| 250.00 |
| 400.00 |
| 500.00 |
| 600.00 |

---
