---
aliases:
  - Spark
---
> [[Hadoop Ecosystem#Systems that replace MapReduce|Systems that replace MapReduce]]
## Apache Spark
> Apache Spark is a **fast**, **general-purpose**, **open-source** cluster computing system designed for large-scale data processing.

##### Key Characteristics:
- **Unified analytics engine** – supports batch, streaming, SQL, machine learning, and graph processing.
- **In-memory computation** – stores intermediate results in RAM (vs. Hadoop which writes to disk).
- **Fault tolerant** and scalable.

##### Benefits of Spark Over [[Hadoop]] [[MapReduce]]

| **Feature**         | **Spark**                                                                 | **Hadoop MapReduce**                   |
| ------------------- | ------------------------------------------------------------------------- | -------------------------------------- |
| **Performance**     | Up to **100x faster** (in-memory operations)                              | Disk-based, slower                     |
| **Ease of use**     | High-level APIs in Python, Java, Scala, R                                 | Java-based, verbose programming        |
| **Generality**      | Unified engine for batch, stream, ML, graph                               | Focused on batch processing            |
| **Fault tolerance** | Efficient recovery via lineage                                            | Slower fault recovery via re-execution |
| **Runs Everywhere** | Runs on [[Hadoop]], Apache Mesos, Kubernetes, Standalone or in the cloud. |                                        |

##### Data Sharing 
**In [[Hadoop]] [[MapReduce]]**
![[Screenshot 2025-07-23 at 19.11.44.png|500]]
>Every iteration or query **reads input from [[HDFS]]**, processes it, and **writes the result back to [[HDFS]]**.

**In Spark**
![[Screenshot 2025-07-23 at 19.12.57.png|500]]
>Spark uses Resilient Distributed Datasets ([[RDD]]s), on RAM across cluster nodes.
>
>Once input data is **loaded and processed into memory**, it can be reused multiple times by different queries or iterations **without re-reading from disk**.
>
>10-100x faster than network and disk!

##### How is Spark Fault Tolerant?
> Resilient Distributed Datasets ([[RDD]]s)

- Restricted form of distributed shared memory
- Immutable, partitioned collections of records
- Recompute lost partitions on failure
- No cost if nothing fails

![[Screenshot 2025-07-23 at 19.17.31.png|500]]

- **Lineage Graph**
	- Each [[RDD]] keeps track of how it was derived. If a node fails, Spark **recomputes only the lost partition** from the original transformations.
	
##### Writing Spark Code in Python
```python
# Spark Context Initialization
from pyspark import SparkConf, SparkContext

conf = SparkConf().setAppName("MyApp").setMaster("local")
sc = SparkContext(conf=conf)

# Create RDDs:
# 1. From a Python list
data = [1, 2, 3, 4, 5]
distData = sc.parallelize(data)

# 2. From a file
distFile = sc.textFile("data.txt")
distFile = sc.textFile("folder/*.txt")
```

##### **RDD Transformations **
These create a new RDD from an existing one.

| [[spark.map(func).png\|map(func)]]                 | Apply function to each element               |
| -------------------------------------------------- | -------------------------------------------- |
| [[spark.filter(func).png\|filter(func)]]           | Keep elements where func returns True        |
| [[spark.flatMap(func).png\|flatMap(func)]]         | Like map, but flattens results               |
| union(otherRDD)                                    | Union of two RDDs                            |
| distinct()                                         | Remove duplicates                            |
| [[spark.reduceByKey(func).png\|reduceByKey(func)]] | Combine values for each key (key-value RDDs) |
| sortByKey()                                        | Sort by keys                                 |
| [[spark.join(otherRDD).png\|join(otherRDD)]]       | Join two key-value RDDs                      |
| repartition(n)                                     | Re-distribute RDD to n partitions            |

Transformations are **[[Lazy Evaluation|Lazy]]** – they only execute when an action is triggered.
![[Screenshot 2025-07-24 at 14.00.35.png|500]]

> Related: [[Spark Core]]

