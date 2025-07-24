![[Screenshot 2025-07-24 at 16.06.13.png]]
##### Structure & Usage:
###### **Data Abstraction**
```
# A Hive table maps schema to real data locations:

CREATE TABLE users (
  id BIGINT,
  name STRING,
  startdate TIMESTAMP,
  email STRING
)
```
###### **Data Discovery**
```
# Loading data example:

LOAD DATA INPATH 's3://my-bucket/jb_users/2025' OVERWRITE INTO TABLE users;
```
###### **Partition Management:**
```
# Adding a partition:

ALTER TABLE users ADD PARTITION (dt='2025-03-05') 
LOCATION 's3://my-bucket/jb_users/2025/03/05';
```

```
# Updating partitions:

MSCK REPAIR TABLE users;
```

Limitations of Hive Metastore with [[Amazon S3|S3]]
- Slow when many files exist in S3.
- S3 partitions are not real folders, only object prefixes 

```
# e.g., An object in my-bucket folder
's3://my-bucket/jb_users/2025/03/05/part-0001’ 
```

> Part of: [[Intro to Data Analytics#Data Metastore - Apache Hive Hive|Intro to Data Analytics]]
> Related: [[Apache Hive]]