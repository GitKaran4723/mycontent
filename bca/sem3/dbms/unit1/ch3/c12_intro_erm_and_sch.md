**Introduction to Relational Model and Schema**

1\. What is the Relational Model?

The Relational Model is a foundational concept in database management systems (DBMS), introduced by E.F. Codd in 1970\. It organizes data into tables (called relations) which are easy to understand and use.

Each relation (or table) consists of:

* **Rows (called tuples)** – represent records  
* **Columns (called attributes)** – represent data fields

**Schema**

What is Schema?

A schema is the blueprint or structure that defines how data is organized and stored in a database. It outlines the tables, fields, relationships, views, indexes, and other elements within the database. The schema defines the logical view of the entire database and specifies the rules that govern the data, including its types, constraints, and relationships.

Types of Database Schemas:

**01\. Physical Database Schema**

* A physical schema defines how data is stored in the storage system, including the arrangement of files, indices and other storage structures. It specifies the actual code and syntax needed to create the database structure. Essentially, it determines where and how the data is stored in the physical storage medium.

* The database administrator decides the storage locations and organization of data within the storage blocks. This schema represents the lowest level of abstraction

**02.Logical Database Schema**

* A logical database schema defines the logical structure of the data, including tables, views, relationships, and integrity constraints. It describes how data is organized in tables and how the attributes of these tables are connected. The logical schema ensures that the data is stored in an organized manner, while maintaining data integrity.

* Using Entity-Relationship (ER) modelling, the logical schema outlines the relationships between different data components. It also defines integrity constraints to ensure the quality of data during insertion and updates.  
* This schema represents a higher level of abstraction compared to the physical schema, focusing on logical constraints and how the data is structured, without dealing with the physical storage details.

**🏗️ 3-Tier Schema Architecture in DBMS**

This architecture organizes a database into three distinct levels of abstraction:

| Level | Description |
| :---- | :---- |
| 🔻 **1\. Physical Level** | The lowest level, detailing **how data is physically stored** on media like disks and tapes. |
| 🔷 **2\. Conceptual Level** | Describes **what data is stored** and the relationships between tables. This represents the **logical schema**. |
| 🔹 **3\. External Level** | Provides **different views** of the database tailored for various users, offering **data abstraction**. |

**🔍 Example: University DBMS**

This example illustrates how different users have distinct external views:

| User | View (External Level) |
| :---- | :---- |
| 👨‍🏫 Faculty | Can access student course enrollment and academic records. |
| 🎓 Students | Can view their own academic, financial, and hostel-related information. |

