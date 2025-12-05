# **📘 Types of Data Models in DBMS**

The main types of data models used in Database Management Systems (DBMS) include:

1. **Hierarchical Data Model**
2. **Network Data Model**
3. **Relational Data Model**
4. **Object-Oriented Data Model**

Each model defines how data is **organized**, **connected**, and **accessed**.

---

## **1️⃣ Hierarchical Data Model 📌**

![Image 1](https://lh3.googleusercontent.com/d/12Z9sXV63w-bAMLbYUmv8Zjb2FoG_1rcv)



### Definition
- Organizes data in a **tree-like structure** using **parent-child relationships**.
- Each parent can have **multiple children**, but each child has **only one parent**.

### 📐 Structure
- Based on a **one-to-many** (1:N) relationship.
- Similar to organizational charts or a file directory system.

### 📊 Example

#### Student Enrollment Table
| Name   | Course-enroll | Grade |
|--------|:-------------:|:-----:|
| Gami   | BCA           | 9.0   |
| Mary   | BBA           | 6.0   |
| Mayen  | B.Com         | 8.0   |

#### Faculty Assignment Table
| Name | Department | Course-taught |
|------|------------|---------------|
| Jake | Commerce   | BBA           |
| John | CS         | BCA           |

---

## **2️⃣ Network Data Model**


![Image 2](https://lh3.googleusercontent.com/d/1sOWO41hOSB-gN-QVEMBRXUm0y8EApseT)

### Definition
- Organizes data using **graph structures**, allowing **many-to-many relationships** through **sets**.

### Structure
- Uses **nodes (records)** and **links (pointers)**.
- Each record can have **multiple parent and child records**.
- Supports **1:1**, **1:M**, and **M:N** relationships.
- Allows **lateral and top-down connections** between nodes.
- Reduces data redundancy by allowing **multiple paths** to the same record.

### Example Structure
- Member **TWO** has one owner (**ONE**).
- Member **FIVE** has two owners (**TWO** and **THREE**).

### **✅ Advantages**
1. **Conceptual Simplicity** – Easy to implement.
2. **Handles More Relationship Types** – Supports 1:1, 1:M, and M:N.
3. **Ease of Data Access** – Multiple pathways improve access.
4. **Data Integrity** – Strong links ensure consistency.
5. **Better Data Independence** – More flexible than hierarchical model.

### **❌ Disadvantages**
1. **System Complexity** – Many pointers complicate structure.
2. **Operational Anomalies** – Insertions, deletions, updates are tricky.
3. **Lack of Structural Independence** – Changes require app-level updates.

---

## **3️⃣ Object-Oriented Data Model**

![Image 3](https://lh3.googleusercontent.com/d/1iWLMczfL3zbR_Z664l2ZMFrE5u2fM-qt)

### **Definition**
- Combines **object-oriented programming** with **database technology**.
- Data is stored as **objects**, similar to Java, C++, etc.

### **Structure**
- Each object contains:
  - **Attributes** (data)
  - **Methods** (functions)
- Supports:
  - **Inheritance**
  - **Encapsulation**
  - **Polymorphism**

### 🔍 Core Concepts

#### 1. **Object**
- Represents real-world entities and scenarios within the database.

#### 2. **Attributes and Methods**
- **Attributes** define characteristics.
- **Methods** define behavior.

#### 3. **Class**
- A collection of similar objects.
- An object is an **instance** of a class.

#### 4. **Inheritance**
- A child class inherits from a parent class and can define its own features.

### ✅ Advantages
- Supports **complex data types** (images, audio, video).
- Ideal for:
  - Multimedia systems
  - CAD/CAM
  - Artificial Intelligence
- Closer mapping to real-world models.

### ❌ Disadvantages
- **Complex implementation**.
- **Limited commercial support**.
- **Slower performance** with large datasets.

---

## **4️⃣ Relational Data Model**

![Image 4](https://lh3.googleusercontent.com/d/10unS6xNj9FMgZxEb_7qTXXHAKGL67SnH)

### Definition
- Represents data in **tables (relations)** with **rows (tuples)** and **columns (attributes)**.

### Structure
- Each table has a **primary key**.
- Tables are linked via **foreign keys**.

### Example
- STUDENT table: ROLL_NO, NAME, ADDRESS, PHONE, AGE

### 🔍 Key Terms

#### 1. **Attribute**
- Properties that define an entity.
- *Example:* ROLL_NO, NAME, ADDRESS

#### 2. **Relation Schema**
- Structure of a relation.
- *Example:* STUDENT (ROLL_NO, NAME, ADDRESS, PHONE, AGE)

#### 3. **Tuple**
- A row representing a single record.

#### 4. **Relation Instance**
- Actual content of a relation at a point in time.

#### 5. **Degree**
- Number of attributes.
- *Example:* STUDENT has a degree of 5.

#### 6. **Cardinality**
- Number of tuples.
- *Example:* STUDENT has 4 rows → cardinality = 4.

#### 7. **Column**
- Represents a single attribute across records.

#### 8. **NULL Values**
- Indicates unknown or unavailable data.
- *Example:* PHONE of student with ROLL_NO = 4 is NULL.

## **🔑 Types of Keys**

### 1. Primary Key
- Uniquely identifies each tuple.
- Must be **unique** and **non-null**.
- *Example:* `ROLL_NO`

### 2. Candidate Key
- Attributes that can uniquely identify tuples.
- One is selected as the primary key.

### 3. Super Key
- Uniquely identifies tuples but may include extra attributes.

### 4. Foreign Key
- Refers to the **primary key of another table**.
- *Example:* `BRANCH_CODE` in `STUDENT` refers to `BRANCH_CODE` in `BRANCH`.

### 5. Composite Key
- Combination of attributes to uniquely identify a tuple.
- *Example:* `FIRST_NAME + LAST_NAME` (if no duplicates exist)


