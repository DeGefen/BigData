> **Goal:** Store “documents” or semi-structured data that do not have constant schema
- Stores semi-structured data like **JSON/BSON**
- No strict schema – each document can differ
- Ideal for use cases where schema is flexible
	e.g., Couchbase, MongoDB, Elasticsearch (optimized for search)

- **Rows and Tables become**
	- Database → Database
	- Table → Bunch of documents
	- Row → Document
	- Column → Field
	- Primary key → \_id

[![Document Database - Data Engineering Wiki](https://publish-01.obsidian.md/access/e5408ef24c9251b993f742b19645ad44/Assets/document_database_example.png)!

> Part of [[NoSQL#**NoSQL Families (Types)** |NoSQL Families]]