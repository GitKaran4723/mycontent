# **Entities and Attributes**

## **Entity**
* **Definition:** An Entity is a real-world object or concept that can be clearly identified and stored in a database.  
  * **Entities can be:**  
    * **Physical objects:** Student, Car, Book  
    * **Conceptual objects:** Course, Department, Company  
* **Types of Entities:**  
  * **Strong Entity:** Exists independently and has a primary key  
    * **Example:** Student, Employee  
  * **Weak Entity:** Cannot exist without a related strong entity  
    * **Example:** OrderItem (dependent on Order)

## **Attribute:**

**What is an Attribute?** 

In the Entity-Relationship (ER) Model, an attribute is a property or characteristic that describes an entity. An entity is a real-world object (like a Student, Employee, Book, etc.). Attributes store data values related to the entity.

![Image 1](https://lh3.googleusercontent.com/d/1SRgtXDiEKuw9i7Quv_TP6_CqktKB7jzX)

 Example: For the entity Student, typical attributes might be:

* Roll Number   
* Name   
* Date of Birth    
* Email  
* Phone Number 

**Types of Attributes:**

Attributes are categorized based on their structure, value, and how they relate to the entity. The main types are:

### **1\. Key Attribute**  
The attribute which uniquely identifies each entity in the entity set is called the key attribute. 

**For example:**  
 Roll\_No will be unique for each student.

![Image 2](https://lh3.googleusercontent.com/d/1UkZmR1tWbXd3o2Xse6kqVd0O8TKTcPrp)

 In an ER diagram, the key attribute is represented by an oval with an underline.

### **2\. Composite Attribute**  
An attribute composed of many other attributes is called a composite attribute.

**For example**:  
 the Address attribute of the student Entity type consists of Street, City, State, and Country.  

![Image 3](https://lh3.googleusercontent.com/d/1tlekVhCyS8h6ptAv6uMn68Bo3VelihQr)

In an ER diagram, the composite attribute is represented by an oval comprising of ovals.

### **3\. Multivalued Attribute**  
An attribute consisting of more than one value for a given entity.

**For example;**  
 Phone\_No (can be more than one for a given student).

![Image 4](https://lh3.googleusercontent.com/d/1H0Da0I_ofp2pFYViVCbvcKS2dCypq1ii)

In an ER diagram, a multivalued attribute is represented by a double oval.

### **4\. Derived Attribute**

An attribute that can be derived from other attributes of the entity type is known as a derived attribute. 

**Example:**

 Age (can be derived from DOB).

![Image 5](https://lh3.googleusercontent.com/d/1nRTPNMh3Csixsk-tWq1B2Be0FIPWRkHy)

In an ER diagram, the derived attribute is represented by a dashed oval.

The Complete Entity Type Student with its Attributes can be represented as:

![Image 6](https://lh3.googleusercontent.com/d/1RsvQyXXhtJoJfOirGQwNbpHV96ikA87N)
