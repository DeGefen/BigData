## Data MetaStore
> Stores **schema** and **discovery mapping** (metadata).

[![Data Store vs MetaStore. In the world of Big Data Analytics… | by Satadru |  Medium](https://miro.medium.com/v2/resize:fit:1400/0*EP_hBGqpsS3U6NMJ)
##### ***Data Schema***:
> Defines how data is organized within a relational database
[![Database schema design 101 for relational databases — PlanetScale|500](https://planetscale.com/assets/blog/content/schema-design-101-relational-databases/db72cc3ac506bec544588454972113c4dc3abe50-1953x1576.png)
##### **Data Store**:
> Stores the actual data (e.g., [[Amazon S3|S3]], [[HDFS]]).

##### **Why Use a MetaStore?**
1. **Data Abstraction**: Users can query abstract tables without worrying about the underlying file system.
	
2. **Data Discovery**: Helps find and manage data through metadata (locations, partitions, schema).
#### Hive's Data MetaStore (Legacy Standard)
- [[Hive MetaStore]]

#### Apache Iceberg (Modern Metastore)
##### **Improvements over [[Hive MetaStore]]:**
- File-level indexing, not just directory-level.
- More efficient handling of metadata.
- Better suited for large-scale [[Data Lake]]s.

## Data Catalog
> A **centralized metadata system** for viewing and understanding all organizational data. View all DB’s in one place!

##### **Use Cases:**
- **Analysts**: Discover relevant data.
- **Developers**: Find tables/fields, track usage.
- **DBAs**: (DataBase Administrator) Governance, access control, change logs.
##### Benefits:
- Avoids “data swamp” – undocumented, messy data.
- Documents schemas, fields, and relationships. 
- Tracks data usage and freshness.
- Helps reduce storage & processing costs.

#### Data Lineage
> Shows **how data flows and transforms** throughout its lifecycle.
> - Tracks how data moves in the organization
> - How it was changed
> - When was it changed
> - Who utilizes the data
##### Types:
- Table-Level Lineage: 
	- Flow of full datasets.
- Column-Level Lineage: 
	- Flow of individual fields or attributes.
##### Benefits:
- Better Data Governance
- Improved data compliance and risk management
- Fast root-cause analysis of data flow
- Understand downstream impacts
- Auditing
- Documentation.

#### Data Governance
> “Specify decision rights and accountability to ensure appropriate behavior as organizations seek to value, create, consume, and control their data, analytics, and information assets.” — Gartner
##### Purpose:
- Define policies and controls over data usage.
- Ensure **security, compliance, and quality**.
- Establish **roles, responsibilities, and ownership**.
