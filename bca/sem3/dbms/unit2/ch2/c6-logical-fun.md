## **🧠 SQL Logical Operators**

### **🔹 Definition**

## SQL Logical Operators are special keywords used in SQL queries to **combine, compare, or negate multiple conditions**.  They help control how data is filtered, making it possible to retrieve **very specific and meaningful results**.  Each operator evaluates conditions as **TRUE**, **FALSE**, or **UNKNOWN**, depending on the logic applied.

## Logical operators are usually used in the **WHERE**, **HAVING**, or **JOIN** clauses.

## 

## ---

### **📋 Sample Employee Table**

| emp\_id | emp\_name | emp\_city | emp\_country |
| ----- | ----- | ----- | ----- |
| 101 | Asha | Allahabad | India |
| 102 | Rahul | Patna | India |
| 103 | Meena | Varanasi | India |
| 104 | John | London | UK |
| 105 | Priya | Pune | India |

## ---

### **🔸 1\. AND Operator**

## The **AND** operator is used to combine two or more conditions in a query so that **all of them must be true** for a record to be included in the result.  It acts like a logical intersection — it narrows down results by enforcing stricter conditions.

## **Example:**  To get employees who live in ‘Allahabad’ **and** belong to ‘India’, both conditions must hold true simultaneously.

## SELECT \* FROM employee

## WHERE emp\_city \= 'Allahabad' AND emp\_country \= 'India';

## 

## **Explanation:**  Here, the query checks for two conditions — city and country. Only those records where both conditions are true are displayed.  If even one condition is false, the row is excluded from the result.

## **Use Case:**  When filtering records that must satisfy **multiple criteria at once**.

## ---

### **🔸 2\. OR Operator**

## The **OR** operator is used when you want to retrieve data that meets **at least one** of several conditions.  Unlike AND, which narrows down data, OR **broadens** the scope by returning rows if **any** of the specified conditions are true.

## **Example:**

## SELECT \* FROM employee

## WHERE emp\_city \= 'Varanasi' OR emp\_country \= 'India';

## 

## **Explanation:**  The query retrieves employees who are either from Varanasi or from India.  Even if one condition is true, that record is included in the output.

## **Use Case:**  Used when you want results that match **any** of multiple conditions.

## ---

### **🔸 3\. NOT Operator**

## The **NOT** operator reverses or negates the logical result of a condition.  It returns rows where the condition is **false**.  This is useful for **excluding** certain data from query results.

## **Example:**

## SELECT \* FROM employee

## WHERE NOT emp\_city \= 'Patna';

## 

## **Explanation:**  This query fetches all records **except** those where the employee’s city is Patna.  The NOT keyword flips the logic of the condition that follows it.

## **Use Case:**  To eliminate or filter out unwanted data from the output.

## ---

### **🔸 4\. IN Operator**

## The **IN** operator checks whether a value matches **any** value within a specified list.  It is a more concise and readable way to represent multiple **OR** conditions.

## **Example:**

## SELECT \* FROM employee

## WHERE emp\_city IN ('Allahabad', 'Patna');

## 

## **Explanation:**  This query selects all employees who are from either Allahabad or Patna.  Instead of writing multiple OR statements, IN simplifies the syntax.

## **Use Case:**  Best suited when matching a value against a **known list** of possible values.

## ---

### **🔸 5\. LIKE Operator**

## The **LIKE** operator allows **pattern-based matching** in text fields.  It is used to search for values that fit a particular **pattern or substring**, rather than an exact match.

## Two wildcard symbols are used with LIKE:

* ## `%` → Represents zero or more characters. 

* ## `_` → Represents exactly one character. 

## **Example:**

## SELECT \* FROM employee

## WHERE emp\_city LIKE 'P%';

## 

## **Explanation:**  This retrieves all employees whose city names begin with the letter ‘P’.  It matches values like “Patna”, “Pune”, or “Paris”.

## **Use Case:**  Used in **pattern searches**, such as names, emails, or address lookups.

## ---

### **🔸 6\. BETWEEN Operator**

## The **BETWEEN** operator checks if a value falls **within a specified range** (inclusive of both boundaries).  It can be applied to numbers, dates, or even text values.

## **Example:**

## SELECT \* FROM employee

## WHERE emp\_id BETWEEN 101 AND 104;

## 

## **Explanation:**  This query returns records of employees whose ID values range from 101 to 104, including both 101 and 104\.  It makes range filtering simple and readable.

## **Use Case:**  Ideal for filtering **numerical ranges, date ranges**, or any ordered data.

## ---

### **🔸 7\. ALL Operator**

## The **ALL** operator compares a single value to **all values** returned by a subquery.  The comparison returns TRUE **only if the condition holds true for every value** in the subquery.

## **Example:**

## SELECT \* FROM employee

## WHERE emp\_id \> ALL (SELECT emp\_id FROM employee WHERE emp\_city \= 'Varanasi');

## 

## **Explanation:**  Here, the main query retrieves employees whose emp\_id is greater than **all** employee IDs from Varanasi.  If even one value in the subquery doesn’t meet the condition, it returns FALSE.

## **Use Case:**  Used for **universal comparisons** — when a condition must hold for all results from a subquery.

## ---

### **🔸 8\. ANY Operator**

## The **ANY** operator (similar to SOME) compares a value to the **set of values** returned by a subquery.  It returns TRUE if **the condition is true for any one** of those values.

## **Example:**

## SELECT \* FROM employee

## WHERE emp\_id \= ANY (SELECT emp\_id FROM employee WHERE emp\_city \= 'Varanasi');

## 

## **Explanation:**  If at least one employee in the subquery matches the emp\_id in the main query, the condition becomes TRUE.

## **Use Case:**  Used when a condition only needs to be **partially true** (for one or more values).

## ---

### **🔸 9\. EXISTS Operator**

## The **EXISTS** operator tests whether a **subquery returns any rows**.  It returns TRUE if the subquery returns at least one record, otherwise FALSE.

## **Example:**

## SELECT emp\_name FROM employee

## WHERE EXISTS (SELECT emp\_id FROM employee WHERE emp\_city \= 'Patna');

## 

## **Explanation:**  If there are employees in Patna, the condition becomes TRUE, and the query returns all employee names.  If no such records exist, it returns an empty result.

## **Use Case:**  Often used in **correlated subqueries** to check for the existence of related data.

## ---

### **🔸 10\. SOME Operator**

## The **SOME** operator works exactly like **ANY** — both are interchangeable in SQL.  It compares a value to a set of values returned by a subquery and returns TRUE if the condition holds for **at least one** value.

## **Example:**

## SELECT \* FROM employee

## WHERE emp\_id \< SOME (SELECT emp\_id FROM employee WHERE emp\_city \= 'Patna');

## 

## **Explanation:**  This retrieves employees whose emp\_id is **less than any** emp\_id of employees from Patna.  Even if one value satisfies the condition, it returns TRUE.

## **Use Case:**  Used when performing comparisons involving **partial matches** from subqueries.

⚖️ **Summary Table**

| Operator | Function | Returns TRUE When | Example Use |
| ----- | ----- | ----- | ----- |
| AND | Combines multiple conditions | All conditions are TRUE | emp\_city='Delhi' AND emp\_country='India' |
| OR | Combines conditions | Any condition is TRUE | emp\_city='Delhi' OR emp\_city='Pune' |
| NOT | Negates condition | Condition is FALSE | NOT emp\_city='Delhi' |
| IN | Checks within list | Value matches any list item | IN ('Pune','Delhi') |
| LIKE | Pattern match | Text matches pattern | LIKE 'A%' |
| BETWEEN | Range filter | Value in range | BETWEEN 100 AND 200 |
| ALL | Compare with all subquery values | All satisfy condition | \= ALL(subquery) |
| ANY | Compare with any subquery value | At least one satisfies | \= ANY(subquery) |
| EXISTS | Checks row presence | Subquery returns ≥1 row | EXISTS(subquery) |
| SOME | Same as ANY | At least one satisfies | \< SOME(subquery) |

