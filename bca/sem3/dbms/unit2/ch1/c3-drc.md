# **📘 Relational Calculus**

### **🧩 Definition:**

Relational Calculus is a non-procedural query language used in databases to retrieve data from relations (tables).  
 Unlike Relational Algebra, which describes how to retrieve the data (procedural), Relational Calculus focuses on what data to retrieve (non-procedural).

**In simple terms —**  
 👉 *Relational Algebra* \= How to get the data  
 👉 *Relational Calculus* \= What data is required

Queries in relational calculus are expressed as logical formulas based on predicate logic, describing the properties of the desired result set.

---

## **⚙️ Types of Relational Calculus**

There are two types:

1. Tuple Relational Calculus (TRC)

2. Domain Relational Calculus (DRC)

---

## **🧾 1\. Tuple Relational Calculus (TRC)**

### **🔹 Definition:**

Tuple Relational Calculus works on tuples (rows) of a relation.  
 It uses tuple variables to represent rows and retrieves tuples that satisfy a given condition.

### **🔹 Syntax:** **{t ∣ P(t)}**    **Where:**

* t → tuple variable

* P(t) → predicate (logical condition that must be true for t)

### **🔹 Explanation:**

The result of a TRC expression is a set of tuples that satisfy the condition ( P(t) ).

---

### **🧠 Example:**

**Table: Employees**

| Employee\_ID | Name | Salary | Department\_ID |
| ----- | ----- | ----- | ----- |
| 101 | Ram | 60000 | D1 |
| 102 | Sita | 48000 | D2 |
| 103 | Raju | 75000 | D1 |

---

**Query:**  
 **Find the names of all employees who earn more than ₹50,000 per year.**

**TRC Expression:**  
> {t ∣ Employees(t)∧t.Salary\>50000}

**Result:**

| Name |
| ----- |
| Ram |
| Raju |

**📝 Explanation:**  
 The query retrieves all tuples `t` from the Employees table where the `Salary` attribute of `t` is greater than 50,000.

---

### **🧩 Example 2: Using Existential Quantifier (∃)**

**Query:**  
 Find loan numbers of all loans having an amount greater than or equal to 10,000.

**TRC Expression:**  
> {t ∣∃s∈Loan(t.Loan\_number=s.Loan\_number∧s.Amount≥10000)}

**Result:**

| Loan Number |
| ----- |
| L33 |
| L35 |
| L98 |

**🧠 Explanation:**  
 The existential quantifier ∃ (there exists) is used to check if there exists a tuple `s` in Loan relation satisfying the given condition.

---

## **🧾 2\. Domain Relational Calculus (DRC)**

### **🔹 Definition:**

Domain Relational Calculus works on domain values (attributes) instead of entire tuples.  
 Each variable represents an attribute rather than a whole row.

### 

### **🔹 Syntax:**

> **{⟨a1​,a2​,...,an​⟩ ∣ P(a1​,a2​,...,an​)}**

**Where:**

* a₁, a₂, …, aₙ → domain variables representing attributes

* P → predicate (logical condition)

---

### **🧠 Example:**

**Table: Employees**

| Emp\_ID | Name | Salary | Dept\_ID |
| ----- | ----- | ----- | ----- |
| 101 | Ram | 60000 | D1 |
| 102 | Sita | 48000 | D2 |
| 103 | Raju | 75000 | D1 |

**Query:**  
 Retrieve the names of employees who earn more than ₹50,000.

**DRC Expression:**

{⟨Name,Salary⟩|∃Emp\_ID,Dept\_ID(Employees(Emp\_ID,Name,Salary,Dept\_ID)∧Salary\>50000)}  
**Result:**

| Name | Salary |
| ----- | ----- |
| Ram | 60000 |
| Raju | 75000  |

**📝 Explanation:**  
 The DRC focuses on specific attributes (Name, Salary) and retrieves only those satisfying the given condition.

---

## **🧮 Example Based on Banking Database**

### **Tables:**

**Customer**

| Customer\_Name | Street | City |
| ----- | ----- | ----- |
| Saurabh | A7 | Patiala |
| Mehak | B6 | Jalandhar |
| Sumiti | D9 | Ludhiana |
| Ria | A5 | Patiala |

**Loan**

| Loan\_Number | Branch\_Name | Amount |
| ----- | ----- | ----- |
| L33 | ABC | 10000 |
| L35 | DEF | 15000 |
| L49 | GHI | 9000 |
| L98 | DEF | 65000 |

---

### **Example 1:**

**Find the Loan Number, Branch Name, and Amount of all loans ≥ 10000\.**

**TRC Expression:**

{t ∣ t∈Loan∧t.Amount≥10000}

 **Result:**

| Loan\_Number | Branch\_Name | Amount |
| ----- | ----- | ----- |
| L33 | ABC | 10000 |
| L35 | DEF | 15000 |
| L98 | DEF | 65000 |

---

### **Example 2:**

**Find the Loan Numbers of loans with amount ≥ 10000\.**

**TRC Expression:**  
{t ∣ t∈Loan∧t.Amount≥10000}

**Result:**

| Loan\_Number |
| ----- |
| L33 |
| L35 |
| L98 |

---

## 

## 

## 

## **🔍 Difference Between TRC and DRC**

| Basis of Difference | Tuple Relational Calculus (TRC) | Domain Relational Calculus (DRC) |
| ----- | ----- | ----- |
| Definition | TRC is a non-procedural query language that works with tuples (rows) to retrieve data satisfying a given condition. | DRC is a non-procedural query language that works with domains (attributes) to retrieve data based on specific attribute values. |
| Level of Operation | Operates on entire tuples from a relation. | Operates on individual domains (fields) of a relation. |
| Variables Represent | Tuple variables represent rows in a relation. | Domain variables represent individual attributes (columns). |
| Syntax | \`{ t | P(t) }\` where *t* is a tuple variable and *P(t)* is a condition. |
| Result | Returns a set of tuples (rows) that satisfy the condition. | Returns a set of attribute values (specific columns) that satisfy the condition. |
| Example | \`{ t | Employee(t) ∧ t.Salary \> 50000 }\` → Returns all tuples of employees earning above ₹50,000. |
| Focus | Focuses on tuples and the conditions applied on them. | Focuses on attribute values and logical relationships among them. |
| Ease of Understanding | Easier for tuple-based thinking; close to table structure. | More mathematical and abstract; focuses on domains. |
| Type of Output | Produces complete rows (tuples). | Produces only specific attributes (columns). |
| Relation to SQL | SQL’s `SELECT * FROM ... WHERE` resembles TRC. | SQL’s `SELECT column_name FROM ... WHERE` resembles DRC. |

## 

## **🧠 In Summary**

* Relational Calculus describes what data is needed rather than how to obtain it.

* It is non-procedural and based on mathematical logic.

* TRC focuses on tuples, while DRC focuses on domains (attributes).

* SQL (Structured Query Language) is actually a practical implementation of Relational Calculus concepts.

---

