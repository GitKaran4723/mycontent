# **Queries on GROUP BY, HAVING AND ORDER BY Clauses**  


### **1\. Display total price of parts of each color**

**Query:**  
> SELECT color, SUM(price) AS total\_price  
FROM Part  
GROUP BY color;

**Output:**

| color | total\_price |
| ----- | ----- |
| red | 850.00 |
| green | 1720.00 |
| blue | 30.00 |
| yellow | 250.00 |
| black | 220.00 |

---

### **2\. Find the branch and the number of suppliers in that branch for branches which have more than 2 suppliers**

**Query:**  
> SELECT branch, COUNT(\*) AS suppliers\_count  
FROM Supplier  
GROUP BY branch  
HAVING COUNT(\*) \> 2;

**Output:**

| branch | suppliers\_count |
| ----- | ----- |
| local | 5 |
| global | 3 |
| regional | 3 |

---

### **3\. Find all parts sorted by pname in ascending order and price in descending order**

**Query:**  
> SELECT Pname, price  
FROM Part  
ORDER BY Pname ASC, price DESC;

**Output:**

| Pname | price |
| ----- | ----- |
| BOLT | 120.00 |
| BRACKET | 400.00 |
| CHAIN | 500.00 |
| NETHER | 220.00 |
| NETSHAFT | 500.00 |
| NUT | 50.00 |
| PIN | 400.00 |
| PLUG | 250.00 |
| SPRING | 600.00 |
| WASHER | 30.00 |

---

### **4\. Find the branch and the number of suppliers in that branch**

**Query:**  
> SELECT branch, COUNT(\*) AS num\_suppliers  
FROM Supplier  
GROUP BY branch;

**Output:**

| branch | suppliers\_count |
| ----- | ----- |
| local | 5 |
| global | 3 |
| regional | 3 |

---

