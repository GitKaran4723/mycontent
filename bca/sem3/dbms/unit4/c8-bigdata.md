# **Big Data** 

# **1\. What is Big Data?**

Big Data refers to **extremely large, complex, and rapidly growing datasets** that traditional data management systems (like RDBMS) cannot store, process, or analyze efficiently.

Big Data can include:

* **Structured data** – organized in tables (e.g., banking transactions)

* **Semi-structured data** – flexible schema (e.g., XML, JSON)

* **Unstructured data** – raw formats (e.g., images, videos, logs, social media posts)

Because traditional systems struggle with storage, scalability, and speed, specialized technologies such as **Hadoop, Spark, and NoSQL databases** are used to manage and analyze Big Data.

---

# **2\. Characteristics of Big Data (5 Vs)**

Big Data is commonly defined by **five key characteristics**, known as the **5 Vs**:

### **1\. Volume**

Represents the **huge size** of data generated, measured in terabytes (TB), petabytes (PB), and exabytes (EB).  
 **Example:** Facebook generates petabytes of user data every single day.

### **2\. Velocity**

Refers to the **speed at which data is produced, transmitted, and processed**.  
 **Example:** Stock market data, IoT sensor streams, real-time social media feeds.

### **3\. Variety**

Represents the **diverse types of data**, both structured and unstructured.  
 **Example:** Text, images, audio, video, documents, logs, emails, JSON, SQL tables.

### **4\. Veracity**

Indicates the **quality, accuracy, and trustworthiness** of data.  
 **Example:** Identifying fake news versus authentic information on social media.

### **5\. Value**

Represents the **usefulness** of Big Data—extracting meaningful insights that provide real-world benefits.  
 **Example:** E-commerce platforms analyzing customer behavior to improve recommendations and sales.

---

# **3\. Types of Big Data**

Big Data can be broadly classified into three categories:

### **1\. Structured Data**

* Highly organized and stored in rows and columns

* Easy to store in relational databases

* **Example:** Banking records, student databases, sales transactions

### **2\. Semi-Structured Data**

* Does not follow a strict schema

* Contains tags or markers for separation

* **Example:** JSON, XML, emails, web logs

### **3\. Unstructured Data**

* No fixed structure

* Difficult to store and analyze using traditional methods

* **Example:** Videos, audio files, PDF documents, social media posts

---

# **4\. Hadoop – Overview**

**Hadoop** is an **open-source framework** designed for the distributed storage and processing of Big Data across clusters of machines.

## **Core Components of Hadoop**

### **1\. HDFS (Hadoop Distributed File System)**

* Stores very large datasets across multiple machines

* Splits files into blocks and replicates them across nodes

* Ensures fault tolerance and high reliability

### **2\. MapReduce**

* A programming model for **parallel and distributed processing**

* Divides tasks into smaller sub-tasks (Map), processes them in parallel, and combines results (Reduce)

* Useful for large batch-processing jobs

### **3\. YARN (Yet Another Resource Negotiator)**

* Responsible for **managing cluster resources**

* Handles job scheduling and allocation of tasks

### **4\. Hadoop Ecosystem Tools**

* **Hive** → SQL-like querying on large datasets

* **Pig** → High-level scripting for data analysis

* **HBase** → NoSQL database built on HDFS

* **Sqoop/Flume** → Tools for importing/exporting data between Hadoop and other systems

## **Common Use Cases of Hadoop**

* Large-scale batch data processing

* Data warehousing and analytics

* Processing log files, machine sensor data, clickstream data

---

# **5\. Cassandra – Overview**

**Apache Cassandra** is a highly scalable and distributed NoSQL database designed for handling massive volumes of data with high availability and no single point of failure.

## **Key Features of Cassandra**

### **1\. Decentralized (Peer-to-Peer) Architecture**

* No master-slave structure

* Every node in the cluster is equal, improving fault tolerance

### **2\. AP Model (Availability \+ Partition Tolerance)**

* Follows the **AP** properties of the CAP Theorem

* Ensures high availability even during network partitions

### **3\. Wide-Column Data Store**

* Data stored in rows and columns but with a flexible schema

* Suitable for distributed and high-volume workloads

### **4\. Linear Scalability**

* Adding more nodes directly increases performance

* Ideal for growing applications

### **5\. Fault Tolerance**

* Data is automatically replicated across nodes

* Ensures no data loss even if multiple nodes fail

### **6\. High Write Performance**

* Optimized for fast data ingestion

* Used in systems requiring millions of writes per second

## **When to Use Cassandra?**

* Applications needing **continuous uptime (24/7)**

* Systems involving **high-speed writes**, such as:

  * Sensor data

  * Server logs

  * IoT applications

* Large, globally distributed applications

* Real-time services like messaging or recommendation engines

## **Real-World Use Cases**

* **Netflix** – streaming logs and user activity

* **Instagram** – storing user messages and activity feeds

* **Uber** – trip data, real-time location tracking

---

