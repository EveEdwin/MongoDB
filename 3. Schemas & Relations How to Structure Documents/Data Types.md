MongoDB supports various data types that are used to store different kinds of information within documents. These data types are based on the BSON (Binary JSON) format, which extends the JSON format to include additional data types and optimize data storage and retrieval.

### Common MongoDB Data Types

1. **String**
   - Used to store textual data.
   - Example:
     ```json
     { "name": "Alice" }
     ```

2. **Integer**
   - Used to store numeric data.
   - Can be either 32-bit or 64-bit.
   - Example:
     ```json
     { "age": 30 }
     ```

3. **Boolean**
   - Used to store true/false values.
   - Example:
     ```json
     { "isActive": true }
     ```

4. **Double**
   - Used to store floating-point numbers.
   - Example:
     ```json
     { "price": 19.99 }
     ```

5. **Date**
   - Used to store date and time in UTC.
   - Example:
     ```json
     { "createdAt": ISODate("2023-06-21T15:00:00Z") }
     ```

6. **Array**
   - Used to store lists of values.
   - Example:
     ```json
     { "tags": ["mongodb", "database", "NoSQL"] }
     ```

7. **Embedded Document (Object)**
   - Used to store nested documents within a document.
   - Example:
     ```json
     {
         "address": {
             "street": "123 Main St",
             "city": "Springfield",
             "state": "IL",
             "zip": "62701"
         }
     }
     ```

8. **ObjectId**
   - Used to store a unique identifier for each document.
   - Example:
     ```json
     { "_id": ObjectId("60c72b2f9fd1c0a5b2f4d72e") }
     ```

9. **Binary Data**
   - Used to store binary data.
   - Example:
     ```json
     { "profilePicture": BinData(0, "binary data here") }
     ```

10. **Null**
    - Used to store a null value.
    - Example:
      ```json
      { "middleName": null }
      ```

11. **Regular Expression**
    - Used to store regular expressions.
    - Example:
      ```json
      { "pattern": /mongodb/i }
      ```

12. **JavaScript Code**
    - Used to store JavaScript code.
    - Example:
      ```json
      { "code": function() { return "Hello, world!"; } }
      ```

13. **JavaScript Code with Scope**
    - Used to store JavaScript code with a scope (variables available within the code).
    - Example:
      ```json
      { "codeWithScope": { "$code": "function() { return x; }", "$scope": { "x": 1 } } }
      ```

14. **32-bit Integer**
    - Specifically used to store 32-bit integers.
    - Example:
      ```json
      { "age": NumberInt(30) }
      ```

15. **64-bit Integer**
    - Specifically used to store 64-bit integers.
    - Example:
      ```json
      { "bigNumber": NumberLong(9223372036854775807) }
      ```

16. **Decimal128**
    - Used to store high-precision decimal values.
    - Example:
      ```json
      { "highPrecisionValue": NumberDecimal("12345.6789") }
      ```

### Examples

Let's look at an example document that uses various data types:

```json
{
    "_id": ObjectId("60c72b2f9fd1c0a5b2f4d72e"),
    "name": "Alice",
    "age": 30,
    "isActive": true,
    "balance": NumberDecimal("12345.67"),
    "joinedAt": ISODate("2023-06-21T15:00:00Z"),
    "profilePicture": BinData(0, "binary data here"),
    "address": {
        "street": "123 Main St",
        "city": "Springfield",
        "state": "IL",
        "zip": "62701"
    },
    "tags": ["mongodb", "database", "NoSQL"],
    "pattern": /mongodb/i,
    "code": function() { return "Hello, world!"; },
    "codeWithScope": { "$code": "function() { return x; }", "$scope": { "x": 1 } },
    "middleName": null
}
```

In this example:
- The `_id` field is an `ObjectId`.
- The `name` field is a `String`.
- The `age` field is an `Integer`.
- The `isActive` field is a `Boolean`.
- The `balance` field is a `Decimal128`.
- The `joinedAt` field is a `Date`.
- The `profilePicture` field is `Binary Data`.
- The `address` field is an `Embedded Document`.
- The `tags` field is an `Array`.
- The `pattern` field is a `Regular Expression`.
- The `code` field is `JavaScript Code`.
- The `codeWithScope` field is `JavaScript Code with Scope`.
- The `middleName` field is `Null`.

Understanding these data types and how to use them allows you to effectively model and store your data in MongoDB, taking advantage of its flexible schema and powerful querying capabilities.