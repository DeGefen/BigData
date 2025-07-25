---
aliases:
  - Google Dremel
---
> [[Hadoop Ecosystem#Systems that replace MapReduce|Systems that replace MapReduce]]

##### **Key Ideas**
• Leverages columnar file format
• Optimized for SQL performance

##### **Concepts**
- Tree-based **query execution**. 
- Efficient scanning and aggregation of **nested columnar data**.
##### Format
> Illustration of what columnar storage is all about:
> given a 3 columns:
![[Screenshot 2025-07-23 at 18.42.46.png|170]]
> In a row-oriented storage, the data is laid out one row at a time as follows:
![[Screenshot 2025-07-23 at 18.45.25.png|500]]
> Whereas in a column-oriented storage, it is laid out one column at a time:
![[Screenshot 2025-07-23 at 18.46.55.png|500]]

##### **Nested data in columnar format**
![[Screenshot 2025-07-23 at 18.50.10.png]]![[Screenshot 2025-07-23 at 18.50.16.png]]

### Benefits of Columnar Data Format
- **Faster Queries**: Optimized for analytical queries that read large amounts of data.
- **Reduced I/O**: Only relevant columns are read, minimizing disk access.
- **Better Compression**: Similar data types in columns lead to higher compression ratios.
- **Scalability**: Efficiently handles large datasets by reducing storage requirements.

### Disadvantages of Columnar Data Format
- **Write Performance**: Slower for write-heavy workloads due to the need to write entire columns.
- Accessing many columns in columnar storage is **inefficient** because it requires reading and combining data from multiple separate files/blocks, while in row-based storage all the data is already together.

## Google Dremel
> Dremel is a **highly scalable, interactive query service** for large datasets that uses a columnar storage format.
> 
> First of its kind to use a **columnar data format** for storing and processing data.
#### Frameworks inspired by Google Dremel
• Apache Dril (MapR)
• Apache Impala (Cloudera)
• Apache Tez (Hortonworks)
• [[Intro to Data Science#**Presto**|Presto]] (Facebook)

