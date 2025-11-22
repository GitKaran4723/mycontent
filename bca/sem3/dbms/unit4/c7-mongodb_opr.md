# **MongoDB Operators** 

MongoDB provides a rich set of **operators** that allow users to perform filtering, comparison, logical evaluation, array manipulation, updates, and aggregation.  
 These operators act as special keywords used inside queries, update commands, and aggregation pipelines to control how data is searched, compared, updated, and processed.

---

# **1\. Comparison Operators**

Comparison operators are used to compare field values with specific conditions.  
 These work similarly to comparison operators in SQL (`=`, `<`, `>`, `!=`, etc.).

| Operator | Meaning | Example |
| ----- | ----- | ----- |
| **$eq** | Matches values equal to a specified value | `{ age: { $eq: 25 } }` → Users with age \= 25 |
| **$ne** | Matches values not equal to a specified value | `{ age: { $ne: 25 } }` |
| **$gt** | Greater than | `{ age: { $gt: 20 } }` |
| **$gte** | Greater than or equal to | `{ age: { $gte: 20 } }` |
| **$lt** | Less than | `{ age: { $lt: 30 } }` |
| **$lte** | Less than or equal to | `{ age: { $lte: 30 } }` |
| **$in** | Matches any value in the given array | `{ city: { $in: ["Delhi", "Mumbai"] } }` |
| **$nin** | Excludes values present in the array | `{ city: { $nin: ["Delhi", "Mumbai"] } }` |

**Use Case:** Filtering documents based on numeric or categorical criteria.

---

# **2\. Logical Operators**

Logical operators allow combining multiple conditions in a single query.

| Operator | Meaning | Example |
| ----- | ----- | ----- |
| **$and** | Returns documents that satisfy **all** specified conditions | `{ $and: [ { age: { $gt: 18 } }, { city: "Delhi" } ] }` |
| **$or** | Returns documents that match **at least one** condition | `{ $or: [ { age: 18 }, { city: "Delhi" } ] }` |
| **$not** | Inverts the result of a condition | `{ age: { $not: { $gt: 30 } } }` |
| **$nor** | Returns documents that **match none** of the conditions | `{ $nor: [ { age: 18 }, { city: "Delhi" } ] }` |

**Use Case:** Complex filtering using AND, OR, NOT logic.

---

# **3\. Element Operators**

Element operators help check whether a field exists or what its data type is.

| Operator | Meaning | Example |
| ----- | ----- | ----- |
| **$exists** | Checks if a field exists or not | `{ email: { $exists: true } }` |
| **$type** | Checks the data type of a field | `{ age: { $type: "int" } }` |

**Use Case:** Validating document structure and field existence.

---

# **4\. Evaluation Operators**

Evaluation operators enable pattern matching and expression-based filtering.

| Operator | Meaning | Example |
| ----- | ----- | ----- |
| **$regex** | Matches text using regular expressions | `{ name: { $regex: "^A" } }` → Names starting with A |
| **$expr** | Allows using aggregation expressions in queries | `{ $expr: { $gt: ["$salary", "$expenses"] } }` |
| **$text** | Performs text-search on indexed fields | `{ $text: { $search: "developer" } }` |

**Use Case:** Advanced filtering like text search and field comparisons.

---

# **5\. Array Operators**

Array operators work with array fields inside MongoDB documents.

| Operator | Meaning | Example |
| ----- | ----- | ----- |
| **$all** | Matches arrays containing **all** specified elements | `{ tags: { $all: ["mongodb", "database"] } }` |
| **$elemMatch** | Returns documents where **at least one** array element meets the condition | `{ scores: { $elemMatch: { $gt: 80, $lt: 90 } } }` |
| **$size** | Matches arrays of a specific size | `{ tags: { $size: 3 } }` |

**Use Case:** Searching values inside arrays or filtering based on array size.

---

# **6\. Update Operators**

Update operators modify documents inside collections. They are used with `updateOne()`, `updateMany()`, and `findOneAndUpdate()`.

| Operator | Meaning | Example |
| ----- | ----- | ----- |
| **$set** | Updates or adds a field | `{ $set: { age: 30 } }` |
| **$unset** | Removes a field from a document | `{ $unset: { email: "" } }` |
| **$inc** | Increments a numeric field | `{ $inc: { age: 1 } }` |
| **$mul** | Multiplies the value of a field | `{ $mul: { salary: 2 } }` |
| **$rename** | Renames a field | `{ $rename: { "oldName": "newName" } }` |
| **$push** | Adds a value to an array | `{ $push: { tags: "newTag" } }` |
| **$pull** | Removes specific value(s) from an array | `{ $pull: { tags: "mongodb" } }` |
| **$addToSet** | Adds an item only if it doesn’t already exist | `{ $addToSet: { tags: "uniqueTag" } }` |

**Use Case:** Updating specific fields, managing arrays, incrementing counters.

---

# **7\. Aggregation Operators**

Aggregation operators are used in the **aggregation pipeline**, which is MongoDB’s framework for data analysis and transformation.

| Operator | Meaning | Example |
| ----- | ----- | ----- |
| **$sum** | Calculates sum of numeric values | `{ $group: { _id: null, total: { $sum: "$salary" } } }` |
| **$avg** | Computes average | `{ $group: { _id: null, avgAge: { $avg: "$age" } } }` |
| **$max** | Finds maximum value | `{ $group: { _id: null, maxSalary: { $max: "$salary" } } }` |
| **$min** | Finds minimum value | `{ $group: { _id: null, minSalary: { $min: "$salary" } } }` |
| **$group** | Groups documents based on a field | Group by department, category, etc. |
| **$match** | Filters documents (similar to `find()`) | Used in pipelines to select specific records |
| **$project** | Selects or reshapes fields | `{ $project: { name: 1, salary: 1 } }` |

**Use Case:** Reports, analytics, dashboards, grouping, and summarizing data.

