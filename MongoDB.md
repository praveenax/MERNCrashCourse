### **MongoDB Cheatsheet**

#### **1. Database Basics**

- **Show Databases**:

  ```bash
  show dbs
  ```

  Lists all databases.

- **Create/Use Database**:

  ```bash
  use database_name
  ```

  Switch to the specified database. If it doesn’t exist, MongoDB will create it when data is inserted.

- **Show Collections**:
  ```bash
  show collections
  ```
  Lists all collections in the current database.

---

#### **2. CRUD Operations (Create, Read, Update, Delete)**

##### **Create Documents (Insert)**

- **Insert One Document**:

  ```javascript
  db.collection_name.insertOne({ name: "John", age: 30 });
  ```

- **Insert Many Documents**:
  ```javascript
  db.collection_name.insertMany([
    { name: "John", age: 30 },
    { name: "Jane", age: 25 },
  ]);
  ```

##### **Read Documents (Find)**

- **Find One Document**:

  ```javascript
  db.collection_name.findOne({ name: "John" });
  ```

- **Find All Documents**:

  ```javascript
  db.collection_name.find();
  ```

- **Find Documents with Query**:

  ```javascript
  db.collection_name.find({ age: { $gt: 25 } }); // Find documents where age > 25
  ```

- **Limit Results**:

  ```javascript
  db.collection_name.find().limit(5); // Get only 5 documents
  ```

- **Sort Results**:
  ```javascript
  db.collection_name.find().sort({ age: -1 }); // Sort by age in descending order
  ```

##### **Update Documents**

- **Update One Document**:

  ```javascript
  db.collection_name.updateOne({ name: "John" }, { $set: { age: 31 } });
  ```

- **Update Many Documents**:

  ```javascript
  db.collection_name.updateMany(
    { age: { $gt: 25 } },
    { $set: { status: "active" } }
  );
  ```

- **Replace One Document**:
  ```javascript
  db.collection_name.replaceOne(
    { name: "John" },
    { name: "John", age: 31, city: "NY" }
  );
  ```

##### **Delete Documents**

- **Delete One Document**:

  ```javascript
  db.collection_name.deleteOne({ name: "John" });
  ```

- **Delete Many Documents**:
  ```javascript
  db.collection_name.deleteMany({ age: { $lt: 25 } });
  ```

---

#### **3. Query Operators**

- **Comparison Operators**:

  ```javascript
  $eq; // Equal to
  $ne; // Not equal to
  $gt; // Greater than
  $gte; // Greater than or equal to
  $lt; // Less than
  $lte; // Less than or equal to
  ```

- **Logical Operators**:

  ```javascript
  $or; // Logical OR
  $and; // Logical AND
  $not; // Logical NOT
  ```

- **Element Operators**:

  ```javascript
  $exists: true; // Check if field exists
  ```

- **Array Operators**:
  ```javascript
  $in: ["value1", "value2"]; // Matches any of the values
  $size: 2; // Matches arrays with 2 elements
  ```

---

#### **4. Indexes**

- **Create an Index**:

  ```javascript
  db.collection_name.createIndex({ name: 1 }); // 1 for ascending, -1 for descending
  ```

- **List Indexes**:

  ```javascript
  db.collection_name.getIndexes();
  ```

- **Drop an Index**:
  ```javascript
  db.collection_name.dropIndex("name_1");
  ```

---

#### **5. Aggregation Framework**

##### **Basic Aggregation Example**

- **Group Documents**:

  ```javascript
  db.collection_name.aggregate([
    { $group: { _id: "$status", total: { $sum: 1 } } },
  ]);
  ```

- **Match and Group**:
  ```javascript
  db.collection_name.aggregate([
    { $match: { status: "active" } },
    { $group: { _id: "$status", count: { $sum: 1 } } },
  ]);
  ```

##### **Common Aggregation Operators**

- **$match**: Filters the documents.
- **$group**: Groups documents by a specified field.
- **$sum**: Sums values.
- **$avg**: Averages values.
- **$sort**: Sorts the documents.

---

#### **6. Data Types**

- **String**:

  ```javascript
  { "name": "John" }
  ```

- **Number**:

  ```javascript
  { "age": 30 }
  ```

- **Boolean**:

  ```javascript
  { "isActive": true }
  ```

- **Array**:

  ```javascript
  { "colors": ["red", "green", "blue"] }
  ```

- **Object**:

  ```javascript
  { "address": { "city": "NY", "zip": "10001" } }
  ```

- **Date**:
  ```javascript
  { "created_at": ISODate("2023-05-16T00:00:00Z") }
  ```

---

#### **7. Import/Export Data**

- **Export a Collection**:

  ```bash
  mongoexport --db=database_name --collection=collection_name --out=collection.json
  ```

- **Import Data**:
  ```bash
  mongoimport --db=database_name --collection=collection_name --file=collection.json
  ```

---

#### **8. User Management**

- **Create a User**:

  ```javascript
  db.createUser({
    user: "username",
    pwd: "password",
    roles: [{ role: "readWrite", db: "database_name" }],
  });
  ```

- **Show Users**:

  ```javascript
  show users
  ```

- **Delete a User**:
  ```javascript
  db.dropUser("username");
  ```

---

#### **9. Backup and Restore**

- **Backup a Database**:

  ```bash
  mongodump --db=database_name --out=/backup_directory
  ```

- **Restore a Database**:
  ```bash
  mongorestore --db=database_name /backup_directory/database_name
  ```

---
