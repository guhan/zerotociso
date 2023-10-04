# Parquet
Parquet is an open-source columnar storage format that is designed for efficient data storage and processing in big data and data analytics platforms. It is optimized for use in distributed data processing frameworks like Apache Hadoop, Apache Spark, and Apache Hive. Parquet is well-suited for handling large volumes of structured and semi-structured data and is known for its performance, compression efficiency, and compatibility with various data processing tools.

## Columnar Storage
Parquet stores data in a columnar format, which means that values from the same column are stored together. This columnar layout is highly efficient for analytical queries because it allows for column-level compression and data skipping.
## Compression
Parquet uses compression techniques to reduce storage space and improve query performance. Since data is grouped by columns, it is often possible to achieve better compression ratios compared to row-based storage formats.
## Schema Evolution
Parquet supports schema evolution, allowing you to add, remove, or modify columns in the schema without breaking backward compatibility. This is crucial for evolving data structures over time.
## Cross-Platform Compatibility
Parquet is designed to be language-agnostic and is supported by a wide range of programming languages and data processing tools. This makes it easy to exchange data between different systems.
## Performance
Due to its columnar storage and compression, Parquet is highly performant for analytical workloads. It allows for efficient predicate pushdown, meaning that query engines can skip reading irrelevant data columns during query execution.
## Predicates and Projections
Parquet allows for predicate pushdown and projection pushdown, which means that query engines can optimize queries by only reading the necessary columns and data blocks, reducing I/O and query execution time.
## Nested Data
Parquet supports nested data structures, making it suitable for handling complex data hierarchies, such as JSON and XML data. This makes it a good fit for data with hierarchical or semi-structured formats.
## Splitting and Merging
Parquet files can be split into smaller files or merged together without the need for extensive data rewriting, which is useful for data partitioning and optimization.
## Compression Codecs
Parquet supports various compression codecs, including Snappy, Gzip, and LZO, allowing users to choose the compression method that best suits their needs.
## Wide Adoption
Parquet is widely adopted in the Hadoop ecosystem and other big data processing frameworks. Many popular tools and systems, such as Apache Spark, Apache Hive, Apache Impala, and Amazon Athena, support Parquet as a native storage format.


## What does a Parquet file look like?
Parquet is a binary file format, so it's not human-readable like a text-based format such as JSON or CSV. Parquet files consist of binary data organized in a columnar format. While you can't read Parquet files directly with a text editor, you can inspect their structure and data using specialized tools or libraries that support the Parquet format.

- **File Header** Every Parquet file begins with a file header, which contains metadata about the file, such as the Parquet format version, compression codec used, and other file-level information.
- **Schema** Parquet files store the schema of the data inside the file. This schema includes the data types and structure of the columns in the file. Parquet uses a schema tree structure to represent complex data types like nested records.
- **Columnar Data** The main body of a Parquet file contains the actual columnar data. Each column is stored separately, with its own metadata. The column data is often stored in a highly compressed binary format, such as a run-length encoding or dictionary encoding, to minimize storage space.
- **Metadata** Parquet files contain metadata for each column, including statistics (min, max, null count), encoding information, and compression details. This metadata is used by query engines to optimize query execution.
- **Row Groups** Parquet files are divided into row groups, which are roughly equal-sized chunks of data. Row groups help with parallel processing and data skipping during queries. Each row group contains a subset of the column data.
- **Data Pages** Within each column of a row group, the data is further divided into data pages. Data pages are units of data that are read and processed together. Each data page includes the actual values of the column and metadata about that page.

- ```
  Parquet File:
|-- File Header
|-- Schema
|   |-- Column 1: Data Type
|   |-- Column 2: Data Type
|   |-- ...
|-- Columnar Data
|   |-- Row Group 1
|   |   |-- Column 1 Data Pages
|   |   |-- Column 2 Data Pages
|   |   |-- ...
|   |-- Row Group 2
|   |   |-- Column 1 Data Pages
|   |   |-- Column 2 Data Pages
|   |   |-- ...
|   |-- ...
|-- Metadata
|   |-- Column 1 Metadata
|   |-- Column 2 Metadata
|   |-- ...
```
