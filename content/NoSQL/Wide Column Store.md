> **Goal:** Have relational tables that can scale horizontally
- Like RDBMS but columns can vary between rows
- Rows identified by keys
- Column families allow partial denormalization
	e.g., Cassandra, HBase, Druid

![[Screenshot 2025-07-24 at 11.59.41.png|400]]
 
 ###### **Classic Partitioning with SPOF**
![[Screenshot 2025-07-24 at 12.07.19.png|400]]
- The dataset is **partitioned** (split) across multiple machines.
- **Each partition is stored on a specific node.**
- There is a **master (or coordinator) node** that:
    - Knows where each partition is
    - Handles routing queries and writes
    
- The **master node is a single point of failure** (SPOF)

 ###### **Fully Distributed, No SPOF**
![[Screenshot 2025-07-24 at 12.10.50.png|400]]
- **No central master node**
- **Every node** knows how to route requests or participate in distributed consensus
- **Data is automatically partitioned and replicated** across multiple nodes
- **Clients can connect to any node** to read/write data

> Part of [[NoSQL#**NoSQL Families (Types)** |NoSQL Families]]