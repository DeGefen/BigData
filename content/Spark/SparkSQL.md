#####  Reminder - [[Spark Core]]
- **[[RDD]] (Resilient Distributed Dataset)**: 
	- the base abstraction of [[Apache Spark|Spark]].
	
- **SparkContext**: 
	- the entry point to Spark functionality.
    
- **Operations**:
    - **Transformations**: lazy operations that return new [[RDD]]s (e.g., map, filter)
    - **Actions**: trigger execution and return values (e.g., count, collect)

## SparkSQL
> - Allows you to use **SQL queries** to interact with data that’s being processed using [[Apache Spark|Spark]]
> - Treats DataFrames as logical tables. These tables can come from JSON, [[Apache Hive|Hive]], CSV, etc.
##### Building Blocks
- A **Distributed SQL** engine that optimizes and executes queries efficiently on large-scale data across clusters.
- **SQLContext / SparkSession**: main entry point for SQL operations.
- **DataFrame**: a distributed collection of data organized into named columns, similar to a table.

##### DataFrame
> New API : DataFrame

| **Aspect**     | **RDD**                    | **DataFrame**                            |
| -------------- | -------------------------- | ---------------------------------------- |
| Structure      | Structured or unstructured | Structured (like a SQL table)            |
| Representation | As objects                 | As table with named columns              |
| Schema         | No explicit schema         | Schema discovered from source or defined |
| Usage          | Functional programming     | SQL-style operations                     |

###### **Create Spark Session**
```
# SparkSQL Context
spark = SparkSession.builder().appName("My App").getOrCreate()
```

 ###### **Create DataFrames**
```
# Create Dataframe from RDD
rdd = sc.parallelize([1,2,3])
df = spark.createDataFrame(rdd)
```

```
# Create Dataframe from JSON
df = spark.read.json("hdfs://usr/tmp/people.json")
df.show()
```

###### **DataFrame Operations**
```
# Schema Inspection
df.printSchema()

# Example output:
# root
# |-- age: long (nullable = true)
# |-- name: string (nullable = true)
# |-- college: string (nullable = true)
```

```
# Select Columns
df.select("name").show()
```

```
# Filter Rows
df.filter(df['age'] > 21).show()
```

```
# Sort Data
df.orderBy(df['age'].desc()).show()
```

```
# Group and Aggregate
df.groupBy("age").count().show()
```

```
# Aggregate Functions
import pyspark.sql.functions as func
df.groupBy("college").agg(func.max("age")).show()
```
###### Column Manipulation
```
# Cast Data Types
df.withColumn("age", col("age").cast(IntegerType()))
```

```
# Add Column from Existing Data
df.withColumn("age_next_year", col("age") + 1).show()
```

```
# Add Constant Column
df.withColumn("nationality", lit("Israel")).show()
```

```
# Drop a Column
df.drop("college").show()
```

###### Writing SQL Directly in Spark
```
# Register the DataFrame as a temporary view
df.createOrReplaceTempView("people")

# Then query with SQL:
spark.sql("SELECT * FROM people").show()
spark.sql("SELECT * FROM people WHERE age > 21").show()
spark.sql("SELECT age, COUNT(age) FROM people GROUP BY age").show()
```

##### DataFrame API vs SQL API
| **Feature**  | **DataFrame API** | **SQL API**   |
| ------------ | ----------------- | ------------- |
| Syntax Check | At compile-time   | At runtime    |
| Language     | Spark-specific    | Standard SQL  |
| Best for     | Programmers       | Data Analysts |
##### Hierarchical JSON Mapping
```
# Sample JSON
[
  {
    "name": "John",
    "address": { "city": "Columbus", "state": "Ohio" }
  },
  {
    "name": "Michael",
    "address": { "city": null, "state": "California" }
  }
]

# Flattened Output via SQL
df = spark.read.json("/tmp/json/people.json")
df.createOrReplaceTempView("people")
spark.sql("SELECT * FROM people").show()

# Output:
# |  name  |  city  |  state   |
# |--------+--------+----------|
# |John    |Columbus|Ohio      |
# |Michael |None    |California|

```

**Schema Preserves Structure**
```
df =spark.read.json("/tmp/json/people.json")

df.printSchema()

# root
# |-- address: struct (nullable = true)
# | |-- city: string (nullable = true)
# | |-- state: string (nullable = true)
# |-- name: string (nullable = true)
```
Spark SQL flattens the structure during queries but keeps the hierarchical schema internally.