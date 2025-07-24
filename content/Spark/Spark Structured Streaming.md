> **Structured Streaming** simplifies stream processing with **SQL-style syntax** and is built on the **[[SparkSQL]] engine**.
### [[Spark Streaming ]]vs Spark Structured Streaming
| **Feature**      | **Spark Streaming**        | **Spark Structured Streaming**    |
| ---------------- | -------------------------- | --------------------------------- |
| API              | [[RDD]]                    | DataFrame / SQL                   |
| Processing Model | Micro-batching (low-level) | Declarative (high-level SQL-like) |
| Syntax           | Functional                 | SQL, DataFrame, Datasets          |
### Core Concepts
- **Input Stream → Input Table**: Every incoming record is treated as a new row.
    ![[Screenshot 2025-07-24 at 20.26.21.png|400]]
    
- **Query on Input → Result Table**: Stream query returns an evolving table (updated over time).
    ![[Screenshot 2025-07-24 at 20.30.24.png|400]]
    
- **Sink**: Only the **changed rows** (according to mode) are written to the output.

### Output Modes
1. **Complete Mode:** 
	- Entire updated table written to external output
	- As seen in the example above
	
2. **Append Mode:**
	- Only new rows of table are written to output
	
3. **Upgrade Mode:** 
	- Only updated rows are written to output

### Streaming Data Sources
- **File Source**: E.g., CSVs in a directory.
- **Kafka Source**: Stream from a [[Apache Kafka#Kafka Architecture|Kafka topic]].
- **Socket Source**: Reads from host:port.

### Basic Examples

```
from pyspark.sql import SparkSession, functions as F

spark = SparkSession.builder.appName("StructuredNetworkWordCount").getOrCreate()
```

**Streaming with Socket input**
```
# Reads input from socket at port 9999
socketDF = spark.readStream\
		.format("socket")\ 
		.option("host", "localhost")\
		.option("port",9999)\
		.load()
```

**Streaming with File Input**
```
# Read all the csv files written atomically in a directory
userSchema = StructType().add("name", "string").add("age", "integer")

csvDF = spark\
		.readStream\
		.option("sep", ";")\
		.schema(userSchema)\
		.csv("/path/to/directory")
```

### Window Operations
> Windows allow grouping data by time intervals.
![[Screenshot 2025-07-24 at 20.47.17.png|600]]

WIP