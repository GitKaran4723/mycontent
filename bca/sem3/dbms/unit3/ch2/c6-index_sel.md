

# **Basic Examples of Index Selection**

Index selection refers to choosing which fields (columns) in a table should have indexes to improve performance. A good index speeds up searches, but unnecessary indexes increase storage cost and slow down updates.  
 Below are basic examples that explain when and why we choose particular indexes.

---

# **1\. Index on Primary Key**

**Example:**  
 A table `Students` has a primary key `RollNo`.

CREATE INDEX idx\_rollno ON Students(RollNo);

**Reason for selection:**

* Primary keys are frequently used to identify individual records.

* Searching by primary key is very common.

* Index is automatically created in most DBMS.

**When to choose:**  
 Always.

---

# **2\. Index on Foreign Key**

**Example:**  
 A table `Orders` has a foreign key `CustomerID`.

CREATE INDEX idx\_customerid ON Orders(CustomerID);

**Reason for selection:**

* Used often in joins (JOIN Customers ON Orders.CustomerID).

* Improves performance for parent-child relationships.

**When to choose:**  
 When foreign keys are used frequently in joins or filters.

---

# **3\. Index on Columns Used in WHERE Clause**

**Example:**  
 A table `Employees` is often queried like:

SELECT \* FROM Employees WHERE Dept \= 'IT';

Creating an index:

CREATE INDEX idx\_dept ON Employees(Dept);

**Reason for selection:**

* Columns frequently used in WHERE conditions give faster filtering.

* Reduces table scan time.

**When to choose:**  
 Whenever a column appears often in filters.

---

# **4\. Index on Columns Used in Range Queries**

**Example:**

SELECT \* FROM Sales WHERE SaleDate BETWEEN '2024-01-01' AND '2024-12-31';

Create an index on `SaleDate`:

CREATE INDEX idx\_saledate ON Sales(SaleDate);

**Reason:**

* B-Tree indexes are very efficient for range searches.

* Helps avoid full table scans.

**When to choose:**  
 For date columns, numeric ranges, or ordered scans.

---

# **5\. Composite Index (Multi-column Index)**

**Example:**

SELECT \* FROM Products WHERE Category \= 'Electronics' AND Brand \= 'Sony';

Composite index:

CREATE INDEX idx\_cat\_brand ON Products(Category, Brand);

**Reason:**

* Speeds up queries using multiple columns together.

* Useful when both fields appear often in the same WHERE clause.

**Important Rule:**  
 Composite index works best when the leftmost column is used in the query.

---

# **6\. Index on Frequently Sorted Columns**

**Example:**

SELECT \* FROM Customers ORDER BY LastName;

Creating an index:

CREATE INDEX idx\_lastname ON Customers(LastName);

**Reason:**

* Index helps database return sorted results faster.

* Avoids expensive sorting operations.

**When to choose:**  
 When a column is used often in ORDER BY or GROUP BY.

---

# **7\. Avoid Indexing Low-Selectivity Columns**

**Example:**  
 Column `Gender` with only two values (Male/Female).

Indexing:

CREATE INDEX idx\_gender ON People(Gender);

**Why it’s NOT useful:**

* Many rows have the same value.

* Index doesn’t help much and wastes space.

**Lesson:**  
 Index columns that have many distinct values, not few.

---

# **8\. Index on Unique or High Selectivity Columns**

**Example:**  
 Column `Email` in a User table.

CREATE UNIQUE INDEX idx\_email ON Users(Email);

**Reason:**

* Email is unique or nearly unique.

* Index makes searches extremely fast.

---

# **Summary of When to Select an Index**

Choose to index a column when it is:

* A primary key or foreign key

* Used often in WHERE conditions

* Involved in range queries

* Frequently used for sorting (ORDER BY)

* Used in joins

* High selectivity (many unique values)

Avoid indexing:

* Columns with very few distinct values

* Columns updated very frequently

* Very small tables (index adds overhead)

---

