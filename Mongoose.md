### **Mongoose ODM Cheatsheet**

#### **1. Setup and Connection**

- **Install Mongoose**:

  ```bash
  npm install mongoose
  ```

- **Connect to MongoDB**:

  ```javascript
  const mongoose = require("mongoose");

  mongoose
    .connect("mongodb://localhost:27017/database_name", {
      useNewUrlParser: true,
      useUnifiedTopology: true,
    })
    .then(() => console.log("MongoDB connected"))
    .catch((err) => console.log(err));
  ```

---

#### **2. Define a Schema**

- **Creating a Schema**:

  ```javascript
  const mongoose = require("mongoose");
  const Schema = mongoose.Schema;

  const userSchema = new Schema({
    name: {
      type: String,
      required: true,
    },
    age: Number,
    email: {
      type: String,
      unique: true,
    },
    createdAt: {
      type: Date,
      default: Date.now,
    },
  });
  ```

---

#### **3. Create a Model**

- **Creating a Model**:

  ```javascript
  const User = mongoose.model("User", userSchema);
  ```

- **Using the Model**:
  The model represents the collection in the database and provides methods to interact with the data.

---

#### **4. CRUD Operations**

##### **Create Documents**

- **Insert One Document**:

  ```javascript
  const newUser = new User({
    name: "John Doe",
    age: 30,
    email: "john@example.com",
  });

  newUser
    .save()
    .then((user) => console.log(user))
    .catch((err) => console.log(err));
  ```

- **Insert Many Documents**:
  ```javascript
  User.insertMany([
    { name: "Alice", age: 25, email: "alice@example.com" },
    { name: "Bob", age: 28, email: "bob@example.com" },
  ])
    .then((users) => console.log(users))
    .catch((err) => console.log(err));
  ```

---

##### **Read Documents**

- **Find All Documents**:

  ```javascript
  User.find()
    .then((users) => console.log(users))
    .catch((err) => console.log(err));
  ```

- **Find One Document**:

  ```javascript
  User.findOne({ email: "john@example.com" })
    .then((user) => console.log(user))
    .catch((err) => console.log(err));
  ```

- **Find by ID**:
  ```javascript
  User.findById("60a76df8fbd82b1d44564753")
    .then((user) => console.log(user))
    .catch((err) => console.log(err));
  ```

---

##### **Update Documents**

- **Update One Document**:

  ```javascript
  User.updateOne({ name: "John Doe" }, { $set: { age: 31 } })
    .then((result) => console.log(result))
    .catch((err) => console.log(err));
  ```

- **Find and Update** (returns updated document):

  ```javascript
  User.findOneAndUpdate(
    { name: "John Doe" },
    { $set: { age: 32 } },
    { new: true }
  )
    .then((user) => console.log(user))
    .catch((err) => console.log(err));
  ```

- **Update Many Documents**:
  ```javascript
  User.updateMany({ age: { $gte: 30 } }, { $set: { status: "senior" } })
    .then((result) => console.log(result))
    .catch((err) => console.log(err));
  ```

---

##### **Delete Documents**

- **Delete One Document**:

  ```javascript
  User.deleteOne({ name: "John Doe" })
    .then((result) => console.log(result))
    .catch((err) => console.log(err));
  ```

- **Find and Delete** (returns deleted document):

  ```javascript
  User.findOneAndDelete({ email: "john@example.com" })
    .then((user) => console.log(user))
    .catch((err) => console.log(err));
  ```

- **Delete Many Documents**:
  ```javascript
  User.deleteMany({ age: { $lt: 25 } })
    .then((result) => console.log(result))
    .catch((err) => console.log(err));
  ```

---

#### **5. Schema Options & Validation**

- **Required Field**:

  ```javascript
  name: { type: String, required: true }
  ```

- **Default Value**:

  ```javascript
  createdAt: { type: Date, default: Date.now }
  ```

- **Unique Value**:

  ```javascript
  email: { type: String, unique: true }
  ```

- **Custom Validation**:
  ```javascript
  age: {
    type: Number,
    validate: {
      validator: function(value) {
        return value >= 18;
      },
      message: 'Age must be 18 or older'
    }
  }
  ```

---

#### **6. Querying and Filtering**

- **Select Specific Fields**:

  ```javascript
  User.find({}, "name email")
    .then((users) => console.log(users))
    .catch((err) => console.log(err));
  ```

- **Limit Results**:

  ```javascript
  User.find()
    .limit(5)
    .then((users) => console.log(users))
    .catch((err) => console.log(err));
  ```

- **Sort Results**:
  ```javascript
  User.find()
    .sort({ age: -1 }) // Descending by age
    .then((users) => console.log(users))
    .catch((err) => console.log(err));
  ```

---

#### **7. Population (References)**

- **Defining References**:

  ```javascript
  const postSchema = new Schema({
    title: String,
    content: String,
    author: { type: Schema.Types.ObjectId, ref: "User" },
  });

  const Post = mongoose.model("Post", postSchema);
  ```

- **Populating References**:
  ```javascript
  Post.find()
    .populate("author", "name email")
    .then((posts) => console.log(posts))
    .catch((err) => console.log(err));
  ```

---

#### **8. Middleware**

- **Pre-save Middleware**:

  ```javascript
  userSchema.pre("save", function (next) {
    this.name = this.name.toUpperCase();
    next();
  });
  ```

- **Post-save Middleware**:
  ```javascript
  userSchema.post("save", function (doc, next) {
    console.log(`User ${doc.name} was saved.`);
    next();
  });
  ```

---

#### **9. Virtuals**

- **Define Virtual Property**:

  ```javascript
  userSchema.virtual("fullName").get(function () {
    return `${this.firstName} ${this.lastName}`;
  });
  ```

- **Use Virtual Property**:
  ```javascript
  const user = new User({ firstName: "John", lastName: "Doe" });
  console.log(user.fullName); // "John Doe"
  ```

---

#### **10. Aggregation**

- **Basic Aggregation Example**:
  ```javascript
  User.aggregate([
    { $match: { age: { $gte: 30 } } },
    { $group: { _id: "$status", total: { $sum: 1 } } },
  ])
    .then((result) => console.log(result))
    .catch((err) => console.log(err));
  ```

---
