> A data lake is a system or repository of data stored in its natural/raw format, usually object blobs or files

![[Database Overview#** NoSQL vs. Data Lake **]]
##### Key Attributes:
- Stores **raw, unprocessed data** (images, logs, videos, CSVs, JSON, etc.).
- Uses [[Object Store|Object Storage]] (like [[Amazon S3|S3]]).
- Allows flexible, **schema-on-read** access (define structure later).
    
- Ideal for **data scientists** and ML pipelines.

##### Data Lake vs Data Warehouse

|**Feature**|**Data Lake**|**Data Warehouse**|
|---|---|---|
|**Data Structure**|Raw / Unprocessed|Cleaned / Processed|
|**Purpose**|Open-ended; defined during analysis|Predefined reports, BI|
|**Users**|Data Scientists, ML/AI applications|Business Analysts, Managers|
|**Storage Type**|Simple Files (e.g., on S3)|Databases / Tables|
> A **data warehouse** is a system used for **reporting and data analysis**, storing **cleaned, organized, and integrated** data from multiple sources in a **structured** format (tables, schemas).