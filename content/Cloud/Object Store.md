---
aliases:
  - Object Storage
---

> A data storage architecture for storing unstructured data, which sections data into units—objects—and stores them in a structurally flat data environment

##### Distributed File System vs. Object Store
> e.g., [[Hadoop]] [[HDFS]] (Distributed File System), [[Amazon S3]] (Object Store)

| **Feature**           | **Distributed File System**    | **Object Store**                                             |
| --------------------- | ------------------------------ | ------------------------------------------------------------ |
| **Structure**         | Files organized in directories | Objects in a flat bucket (folders = visual)                  |
| **Update capability** | Files can be updated           | Objects are **immutable**                                    |
| **Consistency model** | Strong consistency             | [[CAP Theorem#Eventually Consistent\|Eventually Consistent]] |
##### Benefits
- Fast access to objects
- No limit on the number of stored objects.
- Folders are just **abstractions** (visual groupings).
- You can attach **metadata** to each object (tags, descriptions, etc.).
> [[Amazon S3#Key Advantages|Benefits of Amazon S3]]
##### Limitations
- Listing all files in a “directory” is **slow**.
- File System operations like **delete** and **rename** are **not atomic** (no guarantees they succeed completely or not at all).
- Files (objects) must be **transferred over the network** to be read/written.