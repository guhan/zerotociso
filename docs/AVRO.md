# Avro
Avro is a data serialization format commonly used in the world of big data and distributed computing. It was developed by the Apache Software Foundation as part of the Apache Hadoop project and is now a top-level Apache project in its own right. Avro is designed to provide a compact, efficient, and language-independent way to serialize structured data, making it suitable for use in distributed systems and data storage.

## Schema Based
Avro data is always accompanied by a schema that defines the structure and data types of the serialized data. This schema can be used for data validation and interpretation.
## Binary and JSON Encoding
Avro data can be serialized in either a binary format, which is space-efficient and efficient for data processing, or in JSON format for human-readable data exchange.
## Dynamic Typing
Avro supports a rich set of primitive data types (e.g., int, long, string, boolean, float, double) and complex data types (e.g., records, arrays, maps, unions) while allowing schema evolution over time. This means you can add, remove, or modify fields in the schema without breaking backward compatibility.
## Data Compression
Avro supports data compression, which further reduces storage and transmission overhead.
## Language-Independent
Avro has libraries and support for multiple programming languages, making it possible to serialize and deserialize Avro data across different languages.
## Schema Registry
In distributed systems, Avro can benefit from a schema registry that stores and manages schemas. This ensures that producers and consumers of Avro data can use compatible schemas, facilitating data compatibility and evolution.
## Schema Evolution
Avro's schema evolution capabilities make it well-suited for scenarios where data schemas may change over time. New fields can be added, and old fields can be deprecated or made optional without causing data compatibility issues.
## Compatibility with Hadoop Ecosystem
Avro is often used within the Apache Hadoop ecosystem, including tools like Apache Kafka, Apache Spark, and Apache Hive. It's a popular choice for storing data in Hadoop Distributed File System (HDFS).
## Compact and Efficient
Avro's binary encoding is designed to be compact and efficient for both storage and transmission, making it suitable for big data processing.

## How to setup an Avro schema?
Setting up an Avro schema involves defining the structure of your data in a schema file, which specifies the data types and layout of your Avro records. Avro schemas are typically written in JSON format. 

- **Define the Schema**: Determine the structure of your data and create a JSON schema that represents it. Avro schemas consist of three main components:
  - Type: The overall data type, which can be a record, enum, array, map, union, fixed, or a primitive type (e.g., int, long, string, boolean).
  - Name: The name of the data type, which is typically a string.
  - Fields (for records): If you are defining a record, specify an array of fields, each with a name and a type.
Here's an example of a simple Avro schema for a user record:

```
{
  "type": "record",
  "name": "User",
  "fields": [
    { "name": "id", "type": "int" },
    { "name": "name", "type": "string" },
    { "name": "email", "type": "string" },
    { "name": "age", "type": "int" }
  ]
```
In this example, we've defined a record named "User" with four fields: id, name, email, and age.

- **Save the Schema**: Save the JSON schema to a file with a .avsc extension. For example, you can save the schema as user.avsc.

- **Use the Schema**: Once you've defined the Avro schema, you can use it to serialize and deserialize data in Avro format. You can use Avro libraries or tools specific to your programming language for this purpose.
  - For example, in Java, you can use the Avro library to work with Avro data and schemas.
  - In Python, you can use libraries like fastavro or avro-python3 to work with Avro data and schemas.
  - In other languages, there are Avro libraries available that provide similar functionality.
Here's an example of how you might use the Avro schema in Python to serialize and deserialize data:

```
import avro.schema
from avro.datafile import DataFileWriter, DataFileReader
from avro.io import DatumWriter, DatumReader

# Load the Avro schema from a file
schema = avro.schema.parse(open("user.avsc").read())

# Serialize data to Avro format
writer = DataFileWriter(open("users.avro", "wb"), DatumWriter(), schema)
writer.append({"id": 1, "name": "Alice", "email": "alice@example.com", "age": 30})
writer.close()

# Deserialize data from Avro format
reader = DataFileReader(open("users.avro", "rb"), DatumReader())
for user in reader:
    print(user)
reader.close()
```
In this example, we load the Avro schema from the user.avsc file, use it to serialize a user record to an Avro data file, and then deserialize it back into a Python data structure.

## How do you modify fields in an Avro schema without breaking backward compatibility?
Modifying fields in an Avro schema without breaking backward compatibility can be achieved by following Avro's schema evolution rules. Avro is designed to support schema evolution, allowing you to make changes to schemas while ensuring that existing data can still be read with the updated schema.

- **Add New Fields**:
You can safely add new fields to an Avro schema without breaking compatibility. Existing data records can be read with the new schema, and the new fields will be set to their default values (if specified).
Example:
```
{
  "type": "record",
  "name": "User",
  "fields": [
    { "name": "id", "type": "int" },
    { "name": "name", "type": "string" },
    { "name": "email", "type": "string" },
    { "name": "age", "type": "int", "default": 25 },
    { "name": "newField", "type": "string", "default": "default_value" }
  ]
}
```
- **Remove Fields (with Care)**:
If you want to remove a field from an Avro schema, you should do so with caution. While Avro itself allows for the removal of fields, it can result in data loss if the removed field contains valuable information. Consider the impact on existing data and consumers of that data.

- **Rename Fields (with Care)**:
Renaming fields should also be approached carefully. Renaming a field in the schema will require that you provide a default value for the new field name to avoid breaking compatibility.
Example:
```
{
  "type": "record",
  "name": "User",
  "fields": [
    { "name": "id", "type": "int" },
    { "name": "newName", "type": "string", "default": "" }
  ]
}
```
- **Change Field Types (with Care)**:
Changing the data type of a field should be done cautiously, as it can cause data compatibility issues. If you must change a field's data type, ensure that it's a compatible change, meaning that the new type can safely represent the data of the old type. For example, changing an int field to a long is generally safe.
Be aware that changing from a nullable type (e.g., union of null and another type) to a non-nullable type or vice versa can be problematic for existing data.

- **Use Unions for Optional Fields**:
To make fields optional without breaking backward compatibility, consider using unions with the null type. This allows you to represent fields that may or may not be present.
Example:

```
{
  "type": "record",
  "name": "User",
  "fields": [
    { "name": "id", "type": ["null", "int"] },
    { "name": "name", "type": ["null", "string"] }
  ]
}
```
- **Documentation**: Always document changes to your schema, especially if they are not immediately obvious. Clear documentation can help consumers of the data understand the changes and adapt their processing logic accordingly.
