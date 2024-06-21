Accessing structured data in MongoDB involves querying and manipulating documents that adhere to a consistent format or schema within a collection. Here’s a guide on how to effectively access and work with structured data in MongoDB:

### Understanding Structured Data

Structured data in MongoDB typically means that the documents within a collection follow a predictable and consistent format. For instance, in a collection of `users`, each document might have fields like `name`, `age`, `email`, and `addresses`.

**Example Document Structure:**
```json
{
    "_id": ObjectId("60c72b2f9fd1c0a5b2f4d72e"),
    "name": "Alice",
    "age": 30,
    "email": "alice@example.com",
    "addresses": [
        {
            "street": "123 Main St",
            "city": "Springfield",
            "state": "IL",
            "zip": "62701"
        },
        {
            "street": "456 Elm St",
            "city": "Chicago",
            "state": "IL",
            "zip": "60601"
        }
    ]
}
```

### Accessing Structured Data

1. **Connecting to MongoDB:**

   First, ensure you have connected to your MongoDB instance. In the MongoDB shell, you can connect to a database using:
   ```javascript
   use myDatabase
   ```

2. **Querying Data:**

   The `find()` method is used to retrieve documents from a collection. You can specify query criteria to filter the results.
   
   **Find All Documents:**
   ```javascript
   db.users.find()
   ```

   **Find Specific Documents:**
   ```javascript
   db.users.find({ age: { $gte: 25 } })
   ```

   **Find Documents with Specific Fields (Projection):**
   ```javascript
   db.users.find({}, { name: 1, email: 1, _id: 0 })
   ```

3. **Inserting Data:**

   Use the `insertOne()` or `insertMany()` methods to add new documents to a collection.

   **Insert a Single Document:**
   ```javascript
   db.users.insertOne({
       name: "Bob",
       age: 35,
       email: "bob@example.com",
       addresses: [
           {
               street: "789 Maple St",
               city: "Naperville",
               state: "IL",
               zip: "60540"
           }
       ]
   })
   ```

   **Insert Multiple Documents:**
   ```javascript
   db.users.insertMany([
       {
           name: "Charlie",
           age: 25,
           email: "charlie@example.com",
           addresses: [
               {
                   street: "321 Oak St",
                   city: "Springfield",
                   state: "IL",
                   zip: "62701"
               }
           ]
       },
       {
           name: "David",
           age: 28,
           email: "david@example.com",
           addresses: [
               {
                   street: "654 Pine St",
                   city: "Chicago",
                   state: "IL",
                   zip: "60601"
               }
           ]
       }
   ])
   ```

4. **Updating Data:**

   Use the `updateOne()`, `updateMany()`, or `replaceOne()` methods to modify existing documents.

   **Update a Single Document:**
   ```javascript
   db.users.updateOne(
       { name: "Alice" },
       { $set: { age: 31 } }
   )
   ```

   **Update Multiple Documents:**
   ```javascript
   db.users.updateMany(
       { "addresses.city": "Springfield" },
       { $set: { "addresses.$.state": "Illinois" } }
   )
   ```

5. **Deleting Data:**

   Use the `deleteOne()` or `deleteMany()` methods to remove documents from a collection.

   **Delete a Single Document:**
   ```javascript
   db.users.deleteOne({ name: "Charlie" })
   ```

   **Delete Multiple Documents:**
   ```javascript
   db.users.deleteMany({ age: { $lt: 30 } })
   ```

### Working with Embedded Documents

When dealing with structured data that includes embedded documents, you can query and update nested fields using dot notation.

**Querying Embedded Documents:**
```javascript
db.users.find({ "addresses.city": "Chicago" })
```

**Updating Embedded Documents:**
```javascript
db.users.updateOne(
    { "addresses.street": "123 Main St" },
    { $set: { "addresses.$.zip": "62702" } }
)
```

### Indexing for Efficient Data Access

Indexes improve the performance of queries on structured data. Create indexes on fields that are frequently queried.

**Creating an Index:**
```javascript
db.users.createIndex({ email: 1 })
```

### Summary

- **Connecting:** Use the `use` command to connect to the desired database.
- **Querying:** Use `find()` with optional query criteria and projection to retrieve documents.
- **Inserting:** Use `insertOne()` and `insertMany()` to add documents.
- **Updating:** Use `updateOne()`, `updateMany()`, and `replaceOne()` to modify documents.
- **Deleting:** Use `deleteOne()` and `deleteMany()` to remove documents.
- **Embedded Documents:** Access and manipulate nested fields using dot notation.
- **Indexing:** Create indexes to enhance query performance.

By understanding these basic operations and how to work with structured data in MongoDB, you can efficiently manage and retrieve data stored in your MongoDB collections.