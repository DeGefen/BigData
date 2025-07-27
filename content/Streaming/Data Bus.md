> Part of [[Apache Kafka|Kafka]]'s architecture

- Serves as a **centralized communication channel** for data streams.
- Allows different systems to publish and subscribe to data streams.
- Enables real-time data processing and integration across various applications.

#### Benefits of Data BUS
1. **Decoupling**:
	- Producers and consumers can operate independently.
	
2. **Scalability**:
	- Easily add more producers or consumers without affecting existing systems.
	
3. **Common Data Structure**:
	- All data flows through Kafka topics, ensuring a consistent data format.

### Central  Data Bus in Kafka
- Kafka acts as a **Central Data Bus** for real-time data pipelines.
- Producers send data to [[Kafka]] topics, which are like channels.
- Consumers read from these topics, allowing multiple applications to access the same data stream.
- Supports high throughput and low latency for real-time data processing.
![[Screenshot 2025-07-24 at 19.04.08.png|central data bus|500]]