Creating a database and collections in MongoDB is straightforward.

### Using MongoDB Shell (`mongosh`)

#### 1. **Open the MongoDB Shell:**
   First, ensure you have MongoDB installed and running on your system. Then, open the MongoDB shell by running the following command in your terminal or command prompt:
   ```sh
   mongosh
   ```

#### 2. **Create or Switch to a Database:**
   MongoDB creates a database when you first store data in it. To switch to a database (or create it if it doesn't exist), use the `use` command:
   ```sh
   use myLibraryDB
   ```
   This command switches to `myLibraryDB`. If it doesn't exist, it will be created once you insert data.

#### 3. **Create a Collection and Insert a Document:**
   Collections are created implicitly when you insert a document into them. Here’s how you can create a `books` collection by inserting a document:
   ```javascript
   db.books.insertOne({ title: "Moby Dick", author: "Herman Melville", isbn: "1234567890", availableCopies: 3 })
   ```
   This command creates the `books` collection and adds a document to it.
`

### Summary
- **Using MongoDB Shell:** Use `use <databaseName>` to switch to/create a database, and `db.<collectionName>.insertOne(<document>)` to create a collection and insert a document.

These steps allow you to create databases and collections in MongoDB efficiently.