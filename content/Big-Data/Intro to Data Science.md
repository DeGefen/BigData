- **Data Science** - An inter-disciplinary field focused on:
	- Extracting **knowledge and insights** from **structured and unstructured** data.
	- Using **scientific methods**, **algorithms**, **data processing pipelines**, and **systems**.
	- Related fields: **data mining**, **machine learning**, **big data**.

**A Data Scientist**:
- Performs **statistical analysis**, **data mining**, and **retrieval** on large datasets.
- Identifies **trends**, **patterns**, and **valuable insights**.

## Data Transfer - ELT (Extract, Transfer, Load)
- Moves data between systems.
- **Extract**: From source (e.g., databases, APIs).
- **Transform**: Clean, restructure, enrich.
- **Load**: Into destination (e.g., [[Data Lake]], warehouse).
##### Streaming ETL
- Works with real-time data streams (e.g., [[Apache Kafka|Kafka]], [[Spark Streaming]]).
- Continuous transformation and ingestion.
## Data Sources in Data Science
![[Screenshot 2025-07-24 at 16.50.23.png|300]]
##### 1. DataBases
- **[[RDBMS]]**: Relational Databases (SQL-based).
	- e.g., MySQL, SQLite, ORACLE
- **[[NoSQL]]**: Non-relational, handles unstructured/semi-structured data.
	- e.g., mongoDB, Neo4j, Amazon DynamoDB, Amazon SimpleDB
##### 2. Available Datasets
- **Commercial data**: Purchased from providers.
- **Public data**: Free to access.
	- Examples
		- [Google Dataset Search](https://datasetsearch.research.google.com)
		- [Kaggle](https://www.kaggle.com/datasets)
		- [Data.gov](https://www.data.gov/)
		- [Data.gov.il](https://data.gov.il/dataset)
	
##### 3. APIs and Web Services
- Provide access to live or historical data.
- Examples:
    - [Twitter API](https://developer.twitter.com/en/docs/twitter-api)
    - [Meta (Facebook) API](https://developers.facebook.com/)
    - [Yahoo Finance via yFinance](https://github.com/ranaroussi/yfinance)

## Common Data Formats
##### Human Readable
•	CSV (Comma-Separated Values)
•	JSON (JavaScript Object Notation)

##### Binary / Optimized Formats
- **Avro**: 
    - Schema-based serialization.
    - Schema stored in file header.
    - Supports schema evolution.
    - [[Screenshot 2025-07-24 at 18.16.37.png|Avro Schema]]
    
- **ORC (Optimized Row Columnar)**:
    - Columnar storage.
    - Efficient for large data.
    - Organizes data in “stripes” with index and footer.
    - [[Screenshot 2025-07-24 at 18.18.07.png|ORC Stracture]]
    
- **Parquet**:
    - Columnar format, highly compressed.
    - Supports **nested fields**.
    - Designed for efficient querying in distributed environments.
    - [[14 - Data Science (dragged).pdf| Parquet file format]]

## Data Visualization
##### Common Chart Types:
-  Histogram, Scatterplot, Bar chart, Pie chart 
![[Screenshot 2025-07-24 at 17.02.31.png|150]]![[Screenshot 2025-07-24 at 17.02.16.png|150]]
![[Screenshot 2025-07-24 at 17.02.12.png|150]]![[Screenshot 2025-07-24 at 17.02.09.png|150]]
##### **BI Tools (Business Intelligence):**
- Help analysts and managers:
    - Gather information from data
    - Display tables and visuals
    - Drill into data
    - Display bottom lines to management
![[Screenshot 2025-07-24 at 17.54.00.png|300]]
## Data Science Tools
### Querying Big Data
>SQ-like access to distributed data systems.

We already saw: [[Apache Hive]], [[Apache Spark]]
##### **Presto**:
> [[Presto Architecture.png|Presto Architecture]]
- [[Open Source]], distributed SQL query engine.
- Connects to various data sources ([[HDFS]], [[Amazon S3|S3]], Kafka).
##### **Snowflake**:
> [[snowflake Architecture.png|snowflake Architecture]]
- [[LakeHouse]] - “Data Warehouse as a Service”.
- Scalable cloud-native platform.
- Supports semi-structured data (e.g., JSON, [[Intro to Data Science#Binary / Optimized Formats|Avro]], [[Intro to Data Science#Binary / Optimized Formats|Parquet]]).

### Notebooks
> Web UI for exploratory programming, combining code with visualizations
- Combine:
    - Code (Python, R, etc.)
    - Output
    - Visualizations
    - Documentation
- Popular platforms: [[Screenshot 2025-07-24 at 18.22.13.png|Jupyter]], **Google Colab**, **Databricks notebooks**.

### Extended Libraries
-  **pandas**
	- Powerful for **data manipulation**.
	- Think of DataFrames like Excel tables in Python.

- **matplotlib**
	- For plotting data.
	- Easily used with pandas.


