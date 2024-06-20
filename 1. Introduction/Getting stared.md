The MongoDB shell, `mongosh`, is an interactive JavaScript interface to MongoDB. Here are the steps to get started and some basic operations:

### Step 1: Open the MongoDB Shell
1. **Start MongoDB Server:**
   - Ensure the MongoDB server is running. If you installed MongoDB as a service, it should be running. You can start it manually with the command:
     ```sh
     net start MongoDB
     ```

2. **Open Command Prompt:**
   - Press `Win + R`, type `cmd`, and press Enter to open the Command Prompt.

3. **Start MongoDB Shell:**
   - In the Command Prompt, type `mongosh` and press Enter. This will start the MongoDB shell.

### Step 2: Basic MongoDB Shell Operations

#### 1. Show Databases
- **Command:**
  ```javascript
  show dbs
  ```
- **Description:** Lists all databases on the MongoDB server.

#### 2. Create or Switch to a Database
- **Command:**
  ```javascript
  use myDatabase
  ```
- **Description:** Switches to the specified database. If it doesn’t exist, MongoDB will create it when you insert data.

#### 3. Show Collections
- **Command:**
  ```javascript
  show collections
  ```
- **Description:** Lists all collections in the current database.

#### 4. Create a Collection
- **Command:**
  ```javascript
  db.createCollection("myCollection")
  ```
- **Description:** Creates a new collection named `myCollection`.

#### 5. Insert a Document
- **Command:**
  ```javascript
  db.myCollection.insertOne({ name: "Alice", age: 25, city: "New York" })
  ```
- **Description:** Inserts a single document into the `myCollection` collection.

#### 6. Insert Multiple Documents
- **Command:**
  ```javascript
  db.myCollection.insertMany([
    { name: "Bob", age: 30, city: "Chicago" },
    { name: "Charlie", age: 35, city: "San Francisco" }
  ])
  ```
- **Description:** Inserts multiple documents into the `myCollection` collection.

#### 7. Find Documents
- **Command:**
  ```javascript
  db.myCollection.find()
  ```
- **Description:** Retrieves all documents in the `myCollection` collection.

#### 8. Find Documents with a Query
- **Command:**
  ```javascript
  db.myCollection.find({ age: { $gt: 25 } })
  ```
- **Description:** Retrieves documents where the age is greater than 25.

#### 9. Update a Document
- **Command:**
  ```javascript
  db.myCollection.updateOne(
    { name: "Alice" },
    { $set: { age: 26 } }
  )
  ```
- **Description:** Updates the document where the name is "Alice", setting the age to 26.

#### 10. Delete a Document
- **Command:**
  ```javascript
  db.myCollection.deleteOne({ name: "Charlie" })
  ```
- **Description:** Deletes the document where the name is "Charlie".

### Example Session
Here's an example session that combines these operations:

1. **Show Databases:**
   ```javascript
   show dbs
   ```

2. **Switch to/Create Database:**
   ```javascript
   use testDatabase
   ```

3. **Show Collections:**
   ```javascript
   show collections
   ```

4. **Create a Collection:**
   ```javascript
   db.createCollection("users")
   ```

5. **Insert Documents:**
   ```javascript
   db.users.insertOne({ name: "Alice", age: 25, city: "New York" })
   db.users.insertMany([
     { name: "Bob", age: 30, city: "Chicago" },
     { name: "Charlie", age: 35, city: "San Francisco" }
   ])
   ```

6. **Find Documents:**
   ```javascript
   db.users.find()
   ```

7. **Find with Query:**
   ```javascript
   db.users.find({ age: { $gt: 25 } })
   ```

8. **Update Document:**
   ```javascript
   db.users.updateOne(
     { name: "Alice" },
     { $set: { age: 26 } }
   )
   ```

9. **Delete Document:**
   ```javascript
   db.users.deleteOne({ name: "Charlie" })
   ```

### Conclusion
These steps should help you get started with the MongoDB shell and perform basic operations. The MongoDB shell is a powerful tool for interacting with your database, and these commands form the foundation for working with MongoDB.