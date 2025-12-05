# **📘 Introduction to ER Model**

The **Entity-Relationship (ER) Model** is a **conceptual framework** used in **database design**. It visually represents the **logical structure** of a database, including:

* **Entities**  
* **Attributes**  
* **Relationships** between entities

This model is primarily used during the **database design phase** to map real-world objects and their interactions.

## **🧩 Key Components of the ER Model**

**🔹 Entity**

* An **object** or **thing** in the real world that can be distinctly identified.  
* **Examples:** Student, Course, Company

**🔸 Attribute**

* A **property** or **characteristic** of an entity.  
* **Examples:** StudentID, CourseName, EmployeeEmail

**🔷 Relationship**

* A **logical connection** between two or more entities.  
* **Example:** A Student **enrolls in** a Course

**📈 Entity-Relationship Diagram (ERD)**

* A **graphical representation** of the ER model.  
* Helps visualize entities, attributes, and relationships.  
* Used to **design the structure** of a relational database before actual implementation.

**✅ Why Use ER Diagrams in DBMS?**

* Easy to **translate** into relational schemas (tables).  
* Simplifies **real-world modeling** of data and its relationships.  
* **Non-technical users** can understand ERDs without knowing the DBMS internals.  
* Helps to model **complex systems** in a visual and intuitive way.

## **🧠 Symbols Used in the ER Model**

| Symbol | Represents |
| ----- | ----- |
| 🔲 **Rectangle** | Entity |
| 🔵 **Ellipse** | Attribute |
| 🔷 **Diamond** | Relationship among entities |
| ➖ **Line** | Links attributes to entities and entities to relationships |
| ⭕ **Double Ellipse** | Multi-valued Attribute (e.g., multiple phone numbers) |
| ⬛ **Double Rectangle** | Weak Entity (depends on another entity for identification) |

![Image 1](https://lh3.googleusercontent.com/d/1KPZNLL0AWKvi5efRTw_L-8OCy6Ptvyh1)