# **Queries on Set Theory Operators**



**1\. List all parts except 'NUT' and 'BOLT' in ascending order of costs**

**Query:**  
> SELECT Pname, price FROM Part  
WHERE Pname NOT IN ('NUT','BOLT')  
ORDER BY price ASC;

**Output:**

| Pname | price |
| ----- | ----- |
| WASHER | 30.00 |
| NETHER | 220.00 |
| PLUG | 250.00 |
| BRACKET | 400.00 |
| PIN | 400.00 |
| NETSHAFT | 500.00 |
| CHAIN | 500.00 |
| SPRING | 600.00 |

---

**2\. Display all parts that have not been supplied so far**

**Query:**  
> SELECT p.PID, p.Pname, p.price  
FROM Part p  
LEFT JOIN Supplies sp ON p.PID \= sp.PID  
WHERE sp.PID IS NULL;

**Output:**

| PID | Pname | price |
| ----- | ----- | ----- |
| 300005 | BRACKET | 400.00 |

---

**3\. Suppliers who have supplied a 'green' part costing 500 AND a 'red' part costing 400**

**Query:**

> SELECT DISTINCT s.Sname  
FROM Supplier s  
WHERE s.SID IN (  
    SELECT sp.SID  
    FROM Supplies sp  
    JOIN Part p ON sp.PID \= p.PID  
    WHERE p.color \= 'green' AND p.price \= 500  
)  
AND s.SID IN (  
    SELECT sp.SID  
    FROM Supplies sp  
    JOIN Part p ON sp.PID \= p.PID  
    WHERE p.color \= 'red' AND p.price \= 400  
);

**Output:**  
Empty set  
(Explanation: No supplier supplied a red part costing 400 — BRACKET (red,400) was never supplied; only PIN (red,400) was supplied by SID 200009, but that supplier didn't supply any green part priced 500.)

---

**4\. Suppliers who have supplied a 'green' part costing 500 OR a 'red' part costing 400**

**Query:**  
>SELECT DISTINCT s.Sname  
FROM Supplier s  
JOIN Supplies sp ON s.SID \= sp.SID  
JOIN Part p ON sp.PID \= p.PID  
WHERE (p.color \= 'green' AND p.price \= 500\)  
   OR (p.color \= 'red'   AND p.price \= 400\)  
ORDER BY s.SID;

**Output:**

>| Sname | SID | Item Supplied | Quantity |
| ----- | ----- | ----- | ----- |
| Mike | 200002 | NETSHAFT | 500 |
| Arun | 200005 | CHAIN | 500 |
| Shilpa | 200006 | NETSHAFT | 500 |
| MaRta | 200009 | PIN | 400 |

---

**5\. Suppliers who have supplied ALL parts that are 'red' in color**

**Query:**  
\-- count total distinct red parts, then find suppliers whose distinct red-supplied count equals that total  
SET @total\_red \= (SELECT COUNT(DISTINCT PID) FROM Part WHERE color \= 'red');

>SELECT s.Sname  
FROM Supplier s  
JOIN Supplies sp ON s.SID \= sp.SID  
JOIN Part p ON sp.PID \= p.PID  
WHERE p.color \= 'red'  
GROUP BY s.SID, s.Sname  
HAVING COUNT(DISTINCT p.PID) \= @total\_red;

**Output:**  
Empty set  
(Explanation: There are 3 red parts in Part: NUT, BRACKET, PIN. BRACKET (red,400) was not supplied by anyone, so no supplier supplied all three red parts.)

\---

