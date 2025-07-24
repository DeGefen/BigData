---
aliases:
  - Kafka
---
### Key Concepts
- A **distributed, partitioned, replicated log**.
- Used as a [[Screenshot 2025-07-24 at 19.04.08.png|central data bus]] for real-time pipelines.
- High performance for both **write and read**.
- Producers write to **[[Queues and Topics|topics]]**.
- [[Queues and Topics|Topics]] are **partitioned** for scalability.
- Consumers manage their **own offsets**.
- Supports **many producers and consumers**.
- **Retains data** for configurable period.
##### Apache Kafka Vs. RabbitMQ

| **Feature**    | **Kafka**              | **RabbitMQ**      |
| -------------- | ---------------------- | ----------------- |
| Pattern        | Publish-Subscribe only | Queues and Topics |
| Scalability    | Very high              | Limited           |
| Offset Control | Client-managed         | Broker-managed    |
| Use Case       | Big data pipelines     | Lightweight comms |
### Kafka Architecture
1. **Producer API**
	- Publish a stream of records a one or more Kafka topics.
	- Can assign a key for ordering.

2. **Consumer API**
	- Subscribes to one or more topics and processes the streams.
	- Maintains its own read offset.

3. **Kafka Brokers/Service**
	- Kafka cluster that stores data logs.
	- Handles replication, partitioning, durability.
	![[Screenshot 2025-07-24 at 19.05.54.png|300]]

4. **Partitioning and Scalability in Kafka (Topics)** 
	- Topics are split into partitions.
		![[Screenshot 2025-07-24 at 19.09.45.png|300]]
	- Partitions enable parallel processing.
	- Multiple consumers can read from partitions.
		![[Screenshot 2025-07-24 at 19.11.28.png|300]]
	- Consumer groups allow each consumer to read a unique partition (scaling read operations).

5. **Kafka Data Retention & Replay**
	- Kafka retains data (topic is like a rolling file).
	- Consumers can rewind to reprocess older data.
	- Ideal for fault tolerance and debugging.
	![[Screenshot 2025-07-24 at 19.22.29.png|300]]

### The Order Problem
- Events are ordered **within** each partition.
- But order is **not guaranteed across partitions**.

**Example:** HTTP Session “Statefull” order of events:
	1. Get form
	2. Submit form
	3. Send update
	4. Send Second Update
	5. Finish session
- Order Of session is important to analyze it If split across partitions, order may be wrong → session state will be invalid.

##### Solution:
- Use a **message key** (e.g., session ID).
- Kafka routes all messages with same key to **same partition** → order is preserved per key.

### Kafka Durability and Consistency
##### Producer-side Durability:
- Controlled by ***"acks"*** parameter:
	- '[[Screenshot 2025-07-24 at 19.31.15.png|0]]': No durability (fire and forget).
	- '[[Screenshot 2025-07-24 at 19.31.57.png|1]]': Wait for leader node acknowledgment.
	- '[[Screenshot 2025-07-24 at 19.32.19.png|all]]': Wait for all in-sync replicas (highest durability).
	
- Trade-off: Higher durability → slower performance.

##### Consumer-side Consistency:
- Consumers commit offset after processing.
	- Reads from previously committed offset until:
	   new offset -> process messages -> commit
	- Process fails, read again from the previous offset committed

> [[Data Streaming]]
