##### Word Count Example
**Spark **
```
conf = SparkConf().setAppName(appName).setMaster(master)
sc = SparkContext(conf=conf)

# Load file from HDFS into an RDD, each line is a string.
text_file = sc.textFile("hdfs://user/hadoop/gutenberg")

# Split each line into words. Outputs multiple words per line.
# map(...): Create key-value pairs: each word becomes (word, 1).
# reduceByKey(...): Aggregates counts for each word by summing values with the same key.
counts = text_file.flatMap(lambda line: line.split(" ")) \
	.map(lambda word: (word, 1)) \
	.reduceByKey(lambda a, b: a + b)

# Output final word counts to a file in HDFS.
counts.saveAsTextFile("hdfs://user/hadoop/gutenberg-out")
```

**Word Count in [[MapReduce]]**
![[MapReduce#Example]]

**Word Count [[Apache Spark|Spark]]**
![[Screenshot 2025-07-24 at 10.42.26.png]]

**Comparison: MapReduce vs Spark (Word Count)**

| **Phase** | **MapReduce**       | **Spark**                            |
| --------- | ------------------- | ------------------------------------ |
| Input     | Split into blocks   | Same                                 |
| Mapper    | Emit (word, 1)      | map(lambda word: (word, 1))          |
| Shuffle   | Group by word       | Automatically handled by reduceByKey |
| Reducer   | Sum counts per word | reduceByKey(lambda a, b: a + b)      |
| Output    | Write to disk       | saveAsTextFile(...)                  |

##### **Shuffle in Spark**
**What is Shuffle?**
> A **costly** operation that redistributes data across the cluster during certain transformations.

**Why it’s expensive:**
- Breaks **parallelism**.
- Involves **disk and network I/O**.
- Creates **new stages** in the DAG.

**Transformations that may cause shuffling:**
- reduceByKey
- groupByKey
- join
- repartition

##### **Spark Caching**
>Because transformers are lazy, operations may be repeated
>Used when the same [[RDD]] is reused multiple times.
```
# Without Caching
lines = sc.textFile("data.txt")
lineLengths = lines.map(lambda s: len(s))
totalLength = lineLengths.reduce(lambda a, b: a + b)

# This line will result reading "data.txt" twice 
average = totalLength / lines.count()
```

```
# With Caching
lines = sc.textFile("data.txt")

# Caching lines to be used later
lines.cache()

lineLengths = lines.map(lambda s: len(s))
totalLength = lineLengths.reduce(lambda a, b: a + b)

# This line will now use the cached lines
average = totalLength / lines.count()
```

- **Transformations**
	- Transformations like [[spark.map(func).png|map]], [[spark.filter(func).png|filter]], and [[spark.flatMap(func).png|flatMap]] define data processing steps.
	
- **Transformations on Key-Value tuples**
	- Transformations like [[spark.reduceByKey(func).png|reduceByKey]], [[spark.groupByKey().png|groupByKey]] and [[spark.join(otherRDD).png|join]] **requires shuffle**
	
- **Actions**
	- Actions like [[spark.collect().png|collect]], [[spark.count().png|count]] and [[spark.reduce(func).png|reduce]] **Output returns to Driver program .**
	- [[spark.saveAsTextFile(path).png|saveAsTextFile]]'s output **divides into multiple files**, one for **each partition** of the [[RDD]].


