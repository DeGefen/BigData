> A method of **continuous data processing**, enabling real-time insights and reactions to events as they happen.

> **Data Streaming** enables **real-time processing** of fast, continuous data flows using scalable tools like **[[Apache Kafka|Kafka]]**, solving problems like **parallelism**, **event ordering**, and **durability** in modern distributed systems.
#### **The need for data streaming**
- **Internet** became central component of applications.
- Data is constantly collected as **events** from the internet 
  (e.g., user actions, logs, transactions).
- **Data volume is exploding** – processing must keep up.
- We need **Complex Event Processing (CEP)** for pattern detection.
- **Parallelism** is required to handle high-throughput data.

#### **Use Cases**

| **Use Case**             | **Description**                      | **Example**                              |
| ------------------------ | ------------------------------------ | ---------------------------------------- |
| Real-time dashboard      | Shows events happening **now**       | Monitoring incoming network issues       |
| Recent-history dashboard | Shows recent event history           | Live stock market feed                   |
| Event generation         | Create new events from existing data | Fraud alerts from transactions           |
| Corrective actions       | Automated response to anomalies      | Rollback of failed financial transaction |
#### **Common data streaming architecture**
![[Screenshot 2025-07-24 at 18.37.03.png]]
- Data flows **from source apps** into **message queues**.
- Then processed by **CEP engines** (e.g., Apache Flink).
- Results go to **data lakes** or **real-time DBs** (e.g., Redis).
- Final output is consumed by **users or dashboards**.
#### **Message Queues (MQ)**
Used for **asynchronous communication** between services:
- Producer sends messages.
- Broker (middleware) manages [[Queues and Topics|queues/topics]].
- Consumer processes messages.

- Examples of Message Queues solutions
	- IBM MQ, RabbitMQ, Apache ActiveMQ, [[Apache Kafka]]
- Cloud Managed Queues
	- Amazon SQS, Google Cloud Pub/Sub, Azure Service Bus
###### Work Queue (Load Balancing)
- Messages are split among consumers.
- Each consumer gets a different subset.
![[Screenshot 2025-07-24 at 18.51.40.png|400]]
##### Publish-Subscribe ([[Queues and Topics|Topic]])
- All consumers receive **copies** of the same message.
![[Screenshot 2025-07-24 at 18.52.19.png|400]]
##### [[Apache Kafka]] 
