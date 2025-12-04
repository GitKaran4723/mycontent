# **MONGO DB (1-5 Queries)**

### **1\. Create a collection and insert documents using insertOne() and insertMany()**

> db.suppliers.insertOne({  
    name: "Geeta",  
    city: "Delhi",  
    phone: 9499887777,  
    color: "red",  
    partname: "P2",  
    price: 450  
})

> db.suppliers.insertMany(\[  
{ name:"Amit",city:"Delhi",phn:9876543210,color:"green",pname:"p1",price:150},  
{ name:"Rita",city:"Mumbai",phn:8765432109,color:"blue",pname:"p3",price:2500},  
{ name:"Sunil",city:"Chennai",phn:7654321098,color:"red",pname:"p1",price:120},  
{ name:"Latha",city:"Delhi",phn:6543210987,color:"green",pname:"p4",price:6000}  
\])

**Output** (insertOne):  
{  
  acknowledged: true,  
  insertedId: ObjectId('693133d6c47cae7ec7ba2d52')  
}

**Output** (insertMany):  
{  
  acknowledged: true,  
  insertedIds: {  
    '0': ObjectId('693134bec47cae7ec7ba2d53')  
  }  
}

{  
  acknowledged: true,  
  insertedIds: {  
    '0': ObjectId('69313508c47cae7ec7ba2d54')  
  }  
}

{  
  acknowledged: true,  
  insertedIds: {  
    '0': ObjectId('69313531c47cae7ec7ba2d55')  
  }  
}

{  
  acknowledged: true,  
  insertedIds: {  
    '0': ObjectId('69313558c47cae7ec7ba2d56')  
  }  
}

---
### **2\. Select all documents in collection**

**Query:**  
> db.suppliers.find({}, { \_id: 0 })

**Output:**  
{  
  name: 'Geeta',  
  city: 'Delhi',  
  phone: 9499887777,  
  color: 'red',  
  partname: 'P2',  
  price: 450  
}

{  
  name: 'Amit',  
  city: 'Delhi',  
  phn: 9876543210,  
  color: 'green',  
  pname: 'p1',  
  price: 150  
}

{  
  name: 'Rita',  
  city: 'Mumbai',  
  phn: 8765432109,  
  color: 'blue',  
  pname: 'p3',  
  price: 2500  
}

{  
  name: 'Sunil',  
  city: 'Chennai',  
  phn: 7654321098,  
  color: 'red',  
  pname: 'p1',  
  price: 120  
}

{  
  name: 'Latha',  
  city: 'Delhi',  
  phn: 6543210987,  
  color: 'green',  
  pname: 'p4',  
  price: 6000  
}

---

### **3\. Find the count of all suppliers**

**Query:**  
> db.suppliers.countDocuments()

**Output:**  
5

---
### **4\. Find all records that have city \= 'Delhi'**

**Query:**  
> db.suppliers.find({ city : "Delhi"},{\_id:0});

**Output:**  
{  
  name: 'Geeta',  
  city: 'Delhi',  
  phone: 9499887777,  
  color: 'red',  
  partname: 'P2',  
  price: 450  
}

{  
  name: 'Amit',  
  city: 'Delhi',  
  phn: 9876543210,  
  color: 'green',  
  pname: 'p1',  
  price: 150  
}

{  
  name: 'Latha',  
  city: 'Delhi',  
  phn: 6543210987,  
  color: 'green',  
  pname: 'p4',  
  price: 6000  
}

---
### **5\. Retrieve all documents that have color equal to 'red' or 'green**'

**Query:**  
> db.suppliers.find({color:{$in:\["red","blue"\]}},{\_id:0})

**Output:**  
{  
  name: 'Geeta',  
  city: 'Delhi',  
  phone: 9499887777,  
  color: 'red',  
  partname: 'P2',  
  price: 450  
}

{  
  name: 'Rita',  
  city: 'Mumbai',  
  phn: 8765432109,  
  color: 'blue',  
  pname: 'p3',  
  price: 2500  
}  
{  
  name: 'Sunil',  
  city: 'Chennai',  
  phn: 7654321098,  
  color: 'red',  
  pname: 'p1',  
  price: 120  
}

---