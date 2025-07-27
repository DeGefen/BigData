
#flashcards

#### Big Data Quiz

Question: Which of the following is NOT a design principle for Big Data systems?
- A) Horizontal Growth (add more machines instead of stronger ones)
- B) Distributed Processing (split work across machines)
- C) Process where Data is (move code to data, not data to code)
- D) Centralized Processing (process all data on a single powerful machine)
?
- Amswer: D) Centralized Processing (process all data on a single powerful machine)
Explanation: Big Data systems are designed to scale out and process data in a distributed way; centralizing processing on a single machine is not scalable or fault-tolerant. See: [[Big Data Intro]]

Question: Which of the following is a key characteristic of NoSQL databases?
- A) Strict schema enforcement
- B) Only supports SQL queries
- C) Horizontal scalability
- D) Only supports structured data
?
- Amswer: C) Horizontal scalability
Explanation: NoSQL databases are designed to scale horizontally across many machines, making them suitable for big data workloads. See: [[NoSQL]]

Question: What does ACID stand for in the context of RDBMS?
- A) Atomicity, Consistency, Isolation, Durability
- B) Accuracy, Consistency, Integrity, Durability
- C) Atomicity, Concurrency, Isolation, Distribution
- D) Availability, Consistency, Isolation, Durability
?
- Amswer: A) Atomicity, Consistency, Isolation, Durability
Explanation: ACID properties ensure reliable transactions in relational databases. See: [[RDBMS]]
<!--SR:!2025-07-28,1,150-->

Question: Which of the following is NOT a type of NoSQL database?
- A) Key-Value Store
- B) Document Store
- C) Wide Column Store
- D) Relational Store
?
- Amswer: D) Relational Store
Explanation: Relational stores are traditional RDBMS, not NoSQL. NoSQL types include key-value, document, wide column, and graph databases. See: [[NoSQL]]
<!--SR:!2025-07-28,1,156-->

Question: Which of the following is a benefit of using a Data Lake?
- A) Only stores structured data
- B) Schema-on-read flexibility
- C) Requires data to be cleaned before storage
- D) Only accessible to business analysts
?
- Amswer: B) Schema-on-read flexibility
Explanation: Data lakes allow you to define the schema when you read the data, making them flexible for storing raw, unprocessed data. See: [[Data Lake]]

Question: Which operation is NOT part of CRUD in databases?
- A) Create
- B) Read
- C) Update
- D) Distribute
?
- Amswer: D) Distribute
Explanation: CRUD stands for Create, Read, Update, and Delete—the four basic operations of persistent storage. 'Distribute' is not one of them. See: [[RDBMS]]
<!--SR:!2025-07-28,1,162-->

Question: Which of the following is a drawback of NoSQL databases?
- A) No horizontal scalability
- B) Lack of ACID transactions
- C) Only supports SQL
- D) Only for small data
?
- Amswer: B) Lack of ACID transactions
Explanation: Many NoSQL databases sacrifice ACID properties for scalability and flexibility, which can be a drawback for some applications. See: [[NoSQL]]
<!--SR:!2025-07-28,1,160-->

Question: Which technology is designed for real-time processing of continuous data flows?
- A) Data Warehouse
- B) Data Lake
- C) Data Streaming
- D) RDBMS
?
- Amswer: C) Data Streaming
Explanation: Data streaming enables real-time processing of fast, continuous data flows, often using tools like Apache Kafka. See: [[Data Streaming]]

Question: Which of the following is NOT a benefit of Apache Spark over Hadoop MapReduce?
- A) In-memory computation
- B) Unified analytics engine
- C) Only supports batch processing
- D) Fault tolerance
?
- Amswer: C) Only supports batch processing
Explanation: Spark supports both batch and streaming analytics, while Hadoop MapReduce is limited to batch. See: [[Apache Spark]]
<!--SR:!2025-07-28,1,130-->

Question: Which of the following is an example of a message queue solution?
- A) MySQL
- B) IBM MQ
- C) Apache Hive
- D) Amazon Redshift
?
- Amswer: B) IBM MQ
Explanation: IBM MQ is a message queue solution used for asynchronous communication between services. See: [[Data Streaming]]
<!--SR:!2025-07-28,1,142-->

Question: What is the main storage type used in Data Lakes?
- A) Tables
- B) Object Storage
- C) Indexes
- D) Graphs
?
- Amswer: B) Object Storage
Explanation: Data lakes use object storage (like Amazon S3) to store raw, unprocessed data in its native format. See: [[Data Lake]]
<!--SR:!2025-07-28,1,162-->

Question: Which of the following is NOT a use case for data streaming?
- A) Real-time dashboard
- B) Event generation
- C) Corrective actions
- D) Batch reporting only
?
- Amswer: D) Batch reporting only
Explanation: Data streaming is used for real-time and event-driven use cases, not for traditional batch reporting. See: [[Data Streaming]]
<!--SR:!2025-07-28,1,162-->

Question: Which of the following is a feature of RDBMS?
- A) No schema
- B) ACID transactions
- C) Only unstructured data
- D) No support for SQL
?
- Amswer: B) ACID transactions
Explanation: RDBMSs provide ACID-compliant transactions for reliable data management. See: [[RDBMS]]
<!--SR:!2025-07-28,1,150-->

Question: Which of the following is a type of NoSQL database?
- A) Graph Database
- B) Table Database
- C) Index Database
- D) File Database
?
- Amswer: A) Graph Database
Explanation: Graph databases are a type of NoSQL database, along with key-value, document, and wide column stores. See: [[NoSQL]]
<!--SR:!2025-07-28,1,168-->

Question: Which of the following is a challenge of distributed databases?
- A) High availability
- B) Lack of ACID transactions
- C) Simpler to design for scale
- D) Horizontal scalability
?
- Amswer: B) Lack of ACID transactions
Explanation: Distributed databases often sacrifice ACID guarantees for scalability and availability. See: [[NoSQL]]

Question: Which of the following is NOT a benefit of NoSQL?
- A) Scales horizontally well
- B) Designed for specific use-cases
- C) Suitable where RDBMS is limited
- D) One size fits all solution
?
- Amswer: D) One size fits all solution
Explanation: NoSQL databases are not a one-size-fits-all solution; each type is designed for specific use cases. See: [[NoSQL]]

Question: Which of the following is a key attribute of a Data Lake?
- A) Only stores processed data
- B) Uses object storage
- C) Requires predefined schema
- D) Only for business analysts
?
- Amswer: B) Uses object storage
Explanation: Data lakes use object storage to store large volumes of raw data. See: [[Data Lake]]

Question: Which of the following is NOT a feature of Apache Spark?
- A) In-memory computation
- B) Unified analytics engine
- C) Only supports SQL
- D) Fault tolerance
?
- Amswer: C) Only supports SQL
Explanation: Spark supports SQL, streaming, machine learning, and graph processing, not just SQL. See: [[Apache Spark]]
<!--SR:!2025-07-28,1,162-->

Question: Which of the following is a common action in Spark?
- A) collect()
- B) joinTable()
- C) insertRow()
- D) createIndex()
?
- Amswer: A) collect()
Explanation: collect() is a Spark action that returns all elements of an RDD as a list. See: [[Apache Spark]]
<!--SR:!2025-07-28,1,160-->

Question: Which of the following is a transformation in Spark?
- A) map(func)
- B) saveAsTextFile(path)
- C) count()
- D) first()
?
- Amswer: A) map(func)
Explanation: map(func) is a transformation that applies a function to each element of an RDD. See: [[Apache Spark]]
<!--SR:!2025-07-28,1,162-->

Question: Which of the following is NOT a benefit of Spark over Hadoop MapReduce?
- A) Up to 100x faster
- B) In-memory operations
- C) Only supports Java
- D) Unified engine for batch, stream, ML, graph
?
- Amswer: C) Only supports Java
Explanation: Spark supports multiple languages (Python, Scala, Java, R), not just Java. See: [[Apache Spark]]
<!--SR:!2025-07-28,1,156-->

Question: Which of the following is a benefit of using message queues?
- A) Synchronous communication
- B) Asynchronous communication
- C) Only for batch jobs
- D) No support for scaling
?
- Amswer: B) Asynchronous communication
Explanation: Message queues enable asynchronous communication between distributed systems. See: [[Data Streaming]]
<!--SR:!2025-07-28,1,130-->

Question: Which of the following is a feature of Data Warehouses?
- A) Stores raw, unprocessed data
- B) Used for predefined reports and BI
- C) Only for data scientists
- D) Uses object storage
?
- Amswer: B) Used for predefined reports and BI
Explanation: Data warehouses are optimized for structured, cleaned data and business intelligence. See: [[Data Lake]]

Question: Which of the following is NOT a type of RDD transformation in Spark?
- A) map(func)
- B) filter(func)
- C) collect()
- D) flatMap(func)
?
- Amswer: C) collect()
Explanation: collect() is an action, not a transformation, in Spark. See: [[Apache Spark]]

Question: Which of the following is a key difference between Data Lake and Data Warehouse?
- A) Data Lake stores only processed data
- B) Data Warehouse uses object storage
- C) Data Lake allows schema-on-read
- D) Data Warehouse is for open-ended analysis
?
- Amswer: C) Data Lake allows schema-on-read
Explanation: Data lakes allow you to define the schema when you read the data, unlike data warehouses. See: [[Data Lake]]
<!--SR:!2025-07-28,1,148-->

Question: Which of the following is NOT a benefit of distributed databases?
- A) High availability
- B) Simpler to design for scale
- C) Horizontal scalability
- D) Guaranteed ACID transactions
?
- Amswer: D) Guaranteed ACID transactions
Explanation: Distributed databases often trade off ACID guarantees for scalability and availability. See: [[NoSQL]]

Question: Which of the following is a benefit of using Spark's in-memory computation?
- A) Slower performance
- B) Faster data processing
- C) More disk usage
- D) Only supports batch jobs
?
- Amswer: B) Faster data processing
Explanation: In-memory computation allows Spark to process data much faster than disk-based systems. See: [[Apache Spark]]
<!--SR:!2025-07-28,1,162-->

Question: Which of the following is a use case for real-time dashboards?
- A) Monitoring incoming network issues
- B) Generating monthly reports
- C) Data archiving
- D) Data cleaning
?
- Amswer: A) Monitoring incoming network issues
Explanation: Real-time dashboards are a common use case for data streaming and event-driven architectures. See: [[Data Streaming]]

Question: Which of the following is NOT a type of NoSQL database?
- A) Key-Value Store
- B) Document Store
- C) Wide Column Store
- D) Table Store
?
- Amswer: D) Table Store
Explanation: Table Store is not a standard NoSQL type; the main types are key-value, document, wide column, and graph. See: [[NoSQL]]

Question: Which of the following is a benefit of using Data Lakes for ML pipelines?
- A) Only stores processed data
- B) Allows flexible data access
- C) Requires predefined schema
- D) Only for business analysts
?
- Amswer: B) Allows flexible data access
Explanation: Data lakes are ideal for ML pipelines because they store raw data and allow flexible access. See: [[Data Lake]]

Question: Which of the following is a feature of Spark's RDDs?
- A) Mutable collections
- B) Immutable, partitioned collections
- C) Only stored on disk
- D) Only for SQL queries
?
- Amswer: B) Immutable, partitioned collections
Explanation: RDDs in Spark are immutable and partitioned, supporting distributed processing. See: [[Apache Spark]]
<!--SR:!2025-07-28,1,168-->

Question: Which of the following is NOT a benefit of using message queues?
- A) Load balancing
- B) Asynchronous communication
- C) All consumers receive the same message in work queue
- D) Decoupling of services
?
- Amswer: C) All consumers receive the same message in work queue
Explanation: In a work queue, each consumer gets a different message; only publish-subscribe delivers to all. See: [[Data Streaming]]
<!--SR:!2025-07-28,1,136-->

Question: Which of the following is a benefit of using Spark's lineage graph?
- A) No fault tolerance
- B) Efficient recovery from node failures
- C) Only for batch jobs
- D) Requires manual intervention
?
- Amswer: B) Efficient recovery from node failures
Explanation: Spark's lineage graph allows it to recompute lost data partitions automatically. See: [[Apache Spark]]
<!--SR:!2025-07-28,1,150-->

Question: Which of the following is NOT a feature of RDBMS?
- A) Structured data
- B) ACID transactions
- C) No support for SQL
- D) Indexes for fast searching
?
- Amswer: C) No support for SQL
Explanation: RDBMSs are defined by their support for SQL and structured data. See: [[RDBMS]]

Question: Which of the following is a benefit of using Data Lakes?
- A) Only for structured data
- B) Stores raw, unprocessed data
- C) Requires predefined schema
- D) Only for business analysts
?
- Amswer: B) Stores raw, unprocessed data
Explanation: Data lakes are designed to store raw, unprocessed data in its native format. See: [[Data Lake]]
<!--SR:!2025-07-28,1,168-->

Question: Which of the following is a feature of Spark's lazy evaluation?
- A) Actions execute immediately
- B) Transformations execute only when an action is triggered
- C) No support for transformations
- D) Only for SQL queries
?
- Amswer: B) Transformations execute only when an action is triggered
Explanation: Spark uses lazy evaluation, so transformations are only computed when an action is called. See: [[Apache Spark]]

Question: Which of the following is NOT a benefit of using NoSQL databases?
- A) Scales horizontally well
- B) Designed for specific use-cases
- C) Suitable where RDBMS is limited
- D) Guaranteed ACID transactions
?
- Amswer: D) Guaranteed ACID transactions
Explanation: NoSQL databases often trade off ACID guarantees for scalability and flexibility. See: [[NoSQL]]

Question: Which of the following is a feature of Data Warehouses?
- A) Stores cleaned, organized data
- B) Only for data scientists
- C) Uses object storage
- D) Only stores raw data
?
- Amswer: A) Stores cleaned, organized data
Explanation: Data warehouses store cleaned, structured data for analysis and reporting. See: [[Data Lake]]
<!--SR:!2025-07-28,1,142-->

Question: Which of the following is a benefit of using Spark over Hadoop MapReduce?
- A) In-memory computation
- B) Only supports batch processing
- C) No support for streaming
- D) Only for Java
?
- Amswer: A) In-memory computation
Explanation: Spark's in-memory computation makes it much faster than Hadoop MapReduce for many workloads. See: [[Apache Spark]]

Question: Which of the following is a feature of message queues?
- A) Synchronous communication
- B) Asynchronous communication
- C) Only for batch jobs
- D) No support for scaling
?
- Amswer: B) Asynchronous communication
Explanation: Message queues enable asynchronous, decoupled communication between distributed systems. See: [[Data Streaming]]

Question: Which of the following is NOT a type of Spark action?
- A) collect()
- B) count()
- C) map(func)
- D) saveAsTextFile(path)
?
- Amswer: C) map(func)
Explanation: map(func) is a transformation, not an action, in Spark. See: [[Apache Spark]]

Question: Which of the following is a benefit of using Data Lakes for data scientists?
- A) Only stores processed data
- B) Allows flexible, schema-on-read access
- C) Requires predefined schema
- D) Only for business analysts
?
- Amswer: B) Allows flexible, schema-on-read access
Explanation: Data lakes allow data scientists to define the schema at read time, supporting flexible analysis. See: [[Data Lake]]

Question: Which of the following is a feature of Spark's RDDs?
- A) Mutable collections
- B) Immutable, partitioned collections
- C) Only stored on disk
- D) Only for SQL queries
?
- Amswer: B) Immutable, partitioned collections
Explanation: Spark RDDs are immutable and partitioned, supporting distributed, fault-tolerant processing. See: [[Apache Spark]]

Question: Which of the following is NOT a benefit of using distributed databases?
- A) High availability
- B) Simpler to design for scale
- C) Horizontal scalability
- D) Guaranteed ACID transactions
?
- Amswer: D) Guaranteed ACID transactions
Explanation: Distributed databases often trade off ACID guarantees for scalability and availability. See: [[NoSQL]]
<!--SR:!2025-07-28,1,156-->

Question: Which of the following is a benefit of using Spark's in-memory computation?
- A) Slower performance
- B) Faster data processing
- C) More disk usage
- D) Only supports batch jobs
?
- Amswer: B) Faster data processing
Explanation: Spark's in-memory computation allows for much faster data processing than disk-based systems. See: [[Apache Spark]]

Question: Which of the following is a use case for real-time dashboards?
- A) Monitoring incoming network issues
- B) Generating monthly reports
- C) Data archiving
- D) Data cleaning
?
- Amswer: A) Monitoring incoming network issues
Explanation: Real-time dashboards are a key use case for data streaming and event-driven architectures. See: [[Data Streaming]]
<!--SR:!2025-07-28,1,168-->

Question: Which Hadoop component is responsible for storing metadata about the file system, such as block locations and permissions?
- A) DataNode
- B) NameNode
- C) ResourceManager
- D) NodeManager
?
- Amswer: B) NameNode
Explanation: The NameNode manages the metadata and namespace of the Hadoop Distributed File System (HDFS). See: [[HDFS]]
<!--SR:!2025-07-28,1,156-->

Question: In HDFS, what is the default replication factor for data blocks, and why is it important?
- A) 1, for performance
- B) 2, for cost savings
- C) 3, for fault tolerance
- D) 5, for high throughput
?
- Amswer: C) 3, for fault tolerance
Explanation: HDFS replicates each data block three times by default to ensure fault tolerance and data availability. See: [[HDFS]]
<!--SR:!2025-07-28,1,162-->

Question: Which of the following is NOT a design principle of HDFS?
- A) Write-once, read-many
- B) Unlimited file size
- C) Mutable files
- D) Prefer large files
?
- Amswer: C) Mutable files
Explanation: HDFS files are immutable after creation; you cannot modify them in place. See: [[HDFS]]

Question: Which file format in HDFS is optimized for columnar storage and compression?
- A) Text/CSV
- B) Avro
- C) ORC
- D) Sequence File
?
- Amswer: C) ORC
Explanation: ORC (Optimized Row Columnar) is a columnar storage format designed for efficient storage and compression in HDFS. See: [[HDFS]]
<!--SR:!2025-07-28,1,130-->

Question: What is the main function of Apache Hive in the Hadoop ecosystem?
- A) Real-time data streaming
- B) SQL-like querying of large datasets
- C) Distributed file storage
- D) In-memory computation
?
- Amswer: B) SQL-like querying of large datasets
Explanation: Apache Hive provides a SQL-like interface for querying data stored in Hadoop. See: [[Apache Hive]]

Question: Which of the following is a disadvantage of using Hive for analytics?
- A) Uses SQL syntax
- B) Integrates with HDFS
- C) Slow response time due to MapReduce
- D) Supports metadata management
?
- Amswer: C) Slow response time due to MapReduce
Explanation: Hive queries are translated into MapReduce jobs, which can be slow for interactive analytics. See: [[Apache Hive]]

Question: In Hive, what is the purpose of partitions?
- A) To store metadata
- B) To split data logically for faster queries
- C) To replicate data
- D) To compress data
?
- Amswer: B) To split data logically for faster queries
Explanation: Partitions in Hive allow for faster queries by logically splitting data based on column values. See: [[Apache Hive]]
<!--SR:!2025-07-28,1,140-->

Question: Which AWS service is designed for object storage and is used as the backbone for many data lake solutions?
- A) Amazon EC2
- B) Amazon S3
- C) Amazon RDS
- D) Amazon DynamoDB
?
- Amswer: B) Amazon S3
Explanation: Amazon S3 is a scalable object storage service commonly used for data lakes. See: [[Amazon S3]]

Question: What is an AWS Availability Zone (AZ)?
- A) A single data center
- B) A logical group of one or more physically isolated data centers
- C) A global network of edge locations
- D) A virtual private cloud
?
- Amswer: B) A logical group of one or more physically isolated data centers
Explanation: An AWS Availability Zone consists of one or more physically isolated data centers within a region. See: [[AWS Cloud Services]]

Question: Which AWS pricing model offers the lowest cost for long-term, predictable workloads?
- A) Pay-as-you-go
- B) Reserved pricing
- C) Free tier
- D) On-demand
?
- Amswer: B) Reserved pricing
Explanation: Reserved pricing offers discounts for long-term commitments, making it cost-effective for predictable workloads. See: [[AWS Cloud Services]]

Question: Which AWS service is best suited for running serverless code in response to events?
- A) Amazon EC2
- B) Amazon Lambda
- C) Amazon S3
- D) Amazon RDS
?
- Amswer: B) Amazon Lambda
Explanation: AWS Lambda is a serverless compute service that runs code in response to events. See: [[Amazon Lambda]]

Question: Which of the following best describes the CAP Theorem?
- A) A distributed system can guarantee all three: Consistency, Availability, Partition Tolerance
- B) A distributed system can only guarantee two out of three: Consistency, Availability, Partition Tolerance
- C) A distributed system must sacrifice partition tolerance
- D) A distributed system always guarantees consistency
?
- Amswer: B) A distributed system can only guarantee two out of three: Consistency, Availability, Partition Tolerance
Explanation: The CAP Theorem states that a distributed system can only guarantee two of the three: Consistency, Availability, and Partition Tolerance. See: [[CAP Theorem]]
<!--SR:!2025-07-28,1,160-->

Question: In the context of the CAP Theorem, what does "eventual consistency" mean?
- A) All nodes are always consistent
- B) Writes are slow, reads are fast
- C) The system becomes consistent after some time
- D) The system never becomes consistent
?
- Amswer: C) The system becomes consistent after some time
Explanation: Eventual consistency means that, given enough time, all updates will propagate and all nodes will become consistent. See: [[CAP Theorem]]

Question: Which of the following is a scenario where partition tolerance is a must in distributed systems?
- A) All nodes are on the same local network
- B) Network failures can occur between nodes
- C) The system is single-node only
- D) Data is never replicated
?
- Amswer: B) Network failures can occur between nodes
Explanation: Partition tolerance is essential when network failures can occur between distributed nodes. See: [[CAP Theorem]]

Question: Which command uploads a local file to HDFS?
- A) hadoop fs -ls
- B) hadoop fs -cat
- C) hadoop fs -copyFromLocal
- D) hadoop fs -get
?
- Amswer: C) hadoop fs -copyFromLocal
Explanation: The hadoop fs -copyFromLocal command uploads a local file to the Hadoop Distributed File System. See: [[HDFS]]

Question: What is the main role of DataNodes in HDFS?
- A) Store metadata
- B) Store actual data blocks
- C) Manage user permissions
- D) Schedule MapReduce jobs
?
- Amswer: B) Store actual data blocks
Explanation: DataNodes in HDFS are responsible for storing the actual data blocks of files. See: [[HDFS]]

Question: Which of the following is NOT a benefit of AWS global infrastructure?
- A) High performance
- B) Low latency
- C) Unlimited capacity
- D) Manual failover only
?
- Amswer: D) Manual failover only
Explanation: AWS global infrastructure is designed for high availability and automatic failover, not manual failover. See: [[AWS Cloud Services]]

Question: Which AWS service is a managed NoSQL database?
- A) Amazon RDS
- B) Amazon Redshift
- C) Amazon DynamoDB
- D) Amazon Aurora
?
- Amswer: C) Amazon DynamoDB
Explanation: Amazon DynamoDB is a fully managed NoSQL database service provided by AWS. See: [[Amazon DynamoDB]]
<!--SR:!2025-07-28,1,156-->

Question: Which of the following is a key difference between HDFS and a traditional file system?
- A) HDFS does not replicate data
- B) HDFS supports unlimited file size and block replication
- C) HDFS is only for small files
- D) HDFS does not support directories
?
- Amswer: B) HDFS supports unlimited file size and block replication
Explanation: HDFS is designed for large-scale storage with unlimited file size and block replication for fault tolerance. See: [[HDFS]]

Question: Which of the following is a limitation of HDFS?
- A) Cannot store files larger than 1GB
- B) Not suitable for small files
- C) Does not support replication
- D) Only works on Windows
?
- Amswer: B) Not suitable for small files
Explanation: HDFS is optimized for large files; storing many small files can degrade performance. See: [[HDFS]]

Question: Which of the following best describes the function of the Hive MetaStore?
- A) Stores actual data blocks
- B) Manages metadata for Hive tables
- C) Schedules MapReduce jobs
- D) Handles user authentication
?
- Amswer: B) Manages metadata for Hive tables
Explanation: The Hive MetaStore manages metadata and schema information for Hive tables. See: [[Hive MetaStore]]
<!--SR:!2025-07-28,1,168-->

Question: Which AWS service is best for running relational databases in the cloud?
- A) Amazon S3
- B) Amazon EC2
- C) Amazon RDS
- D) Amazon DynamoDB
?
- Amswer: C) Amazon RDS
Explanation: Amazon RDS is a managed relational database service in AWS. See: [[Amazon RDS]]

Question: Which of the following is a key advantage of using partitions in Hive tables?
- A) Increases data redundancy
- B) Speeds up query performance
- C) Reduces storage cost
- D) Eliminates the need for metadata
?
- Amswer: B) Speeds up query performance
Explanation: Partitioning in Hive allows for faster query performance by logically splitting data. See: [[Apache Hive]]
<!--SR:!2025-07-28,1,148-->

Question: Which of the following is NOT a core component of Hadoop?
- A) HDFS
- B) MapReduce
- C) Yarn
- D) Hive
?
- Amswer: D) Hive
Explanation: Hive is a data warehouse system built on top of Hadoop, not a core component. See: [[Hadoop]]
<!--SR:!2025-07-28,1,162-->

Question: Which AWS service is designed for high-performance, in-memory caching?
- A) Amazon S3
- B) Amazon ElastiCache
- C) Amazon RDS
- D) Amazon Redshift
?
- Amswer: B) Amazon ElastiCache
Explanation: Amazon ElastiCache is a managed in-memory caching service for high performance. See: [[AWS Cloud Services]]
<!--SR:!2025-07-28,1,140-->

Question: Which of the following is a key benefit of using edge locations in AWS?
- A) Increased storage capacity
- B) Reduced latency for end users
- C) Lower compute costs
- D) More database options
?
- Amswer: B) Reduced latency for end users
Explanation: Edge locations in AWS bring content closer to users, reducing latency. See: [[AWS Cloud Services]]

Question: Which of the following is a valid use case for Amazon Lambda?
- A) Running a persistent web server
- B) Processing events in a serverless architecture
- C) Hosting a relational database
- D) Storing large files
?
- Amswer: B) Processing events in a serverless architecture
Explanation: AWS Lambda is designed for event-driven, serverless computing. See: [[Amazon Lambda]]
<!--SR:!2025-07-28,1,162-->

Question: Which of the following is a key difference between Hive and traditional RDBMS?
- A) Hive does not support SQL
- B) Hive stores data in HDFS and translates queries to MapReduce
- C) Hive does not support metadata
- D) Hive is not open source
?
- Amswer: B) Hive stores data in HDFS and translates queries to MapReduce
Explanation: Hive translates SQL queries into MapReduce jobs to process data stored in HDFS. See: [[Apache Hive]]

Question: Which of the following is NOT a valid HDFS file format?
- A) Parquet
- B) ORC
- C) Avro
- D) JSON Table
?
- Amswer: D) JSON Table
Explanation: JSON Table is not a standard HDFS file format; common formats include Parquet, ORC, and Avro. See: [[HDFS]]
<!--SR:!2025-07-28,1,140-->

Question: Which AWS service is best for running containerized applications?
- A) Amazon EC2
- B) Amazon ECS
- C) Amazon S3
- D) Amazon RDS
?
- Amswer: B) Amazon ECS
Explanation: Amazon ECS (Elastic Container Service) is AWS's managed service for running containerized applications. See: [[AWS Cloud Services]]
<!--SR:!2025-07-28,1,130-->

