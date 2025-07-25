>  A ***"near-real-time"*** processing framework built on top of **[[Apache Spark]]**.
### **Key Features:**
- Processes data in **micro-batches** (small time-based chunks), not continuous streams.
- Uses **DStreams (Discretized Streams)** instead of traditional [[RDD]]s.
- Good for processing real-time events such as logs, sensor data, or user activity.

### Architecture
##### **End-to-End Architecture**
![[Screenshot 2025-07-24 at 19.48.47.png]]
1. **Data Sources (Input):** 
	- From sources like [[Apache Kafka|Kafka]], [[HDFS]], [[Amazon S3|S3]], TCP sockets, etc.
	
2.  **Processing**:
	- Spark Streaming takes input data from these sources, converts it into micro-batches, and processes it.
	
3. **Output**: 
	- Results are pushed to external systems (like dashboards, databases).
##### **Internal Processing Flow**
![[Screenshot 2025-07-24 at 19.57.02.png]]
1. **Input data stream:**
	- Real-time data enters the system continuously.
	
2. **Spark Streaming:** 
	- Groups the data into micro-batches (e.g. every 10 seconds).
	
3. **Spark Engine**:
	- Executes a job on each batch using Spark’s RDD APIs.
	
4. **Output**:
	- Emits **batches of processed data**.

##### DStream
> DStream = Sequence of [[RDD]]s
![[Screenshot 2025-07-24 at 20.08.15.png]]
- A **DStream** is a high-level abstraction in Spark Streaming.
- Each **DStream** is made up of a **sequence of [[RDD]]s**, where each [[RDD]] holds data from a specific time range.
- Example here:
    - RDD at time 1 = data from time 0 to 1
    - RDD at time 2 = data from time 1 to 2
    - …

##### Transformation on DStream
![[Screenshot 2025-07-24 at 20.10.59.png]]
1. Start with lines DStream (e.g. lines from a Kafka stream).
    
2. Apply flatMap to split each line into words.
    
3. Result is words DStream, with each RDD containing the words extracted from lines in the same time window.
	
- Every transformation is applied **per RDD** in each time unit.
- i.e., lines from 0–1 → words from 0–1; lines from 1–2 → words from 1–2, and so on.

### Spark Streaming Example:
```python
sc = SparkContext(appName="PythonStreamingKafkaWordCount") 
ssc = StreamingContext(sc, 10)  # microbatch interval = 10 seconds
topic = "mytopic"

# Connects to Kafka topic
kvs = KafkaUtils.createStream(ssc, topic, "consumer-group-1", {topic: 1}) 

lines = kvs.map(lambda x: x[1]) 

counts = lines.flatMap(lambda line: line.split(" ")) \
              .map(lambda word: (word, 1)) \
              .reduceByKey(lambda a, b: a + b) 

counts.pprint() 

ssc.start() 
ssc.awaitTermination()
```
Explanation
1. Connects to Kafka topic “mytopic”.
2. Every **10 seconds**, splits incoming lines into words.
3. Counts occurrences of each word in the last 10 seconds.
4. Prints the result in the console.

### Window Operations
> Analyze **more than the last batch**
- for example, the last **30 seconds** of data, even though we process data every **10 seconds**.
![[Screenshot 2025-07-24 at 20.18.34.png]]
