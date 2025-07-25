## RDD (Resilient Distributed Dataset)
>RDD is an immutable (read only) distributed collection of objects.
>It is the **core API** in [[Apache Spark]] that represents a **distributed collection of data**, allowing for **fault-tolerant**, **parallel computations** across a cluster.

>Dataset in RDD is divided into logical partitions, which may be computed on different nodes of the cluster
![[Screenshot 2025-07-23 at 19.08.40.png|600]]
##### **Key Properties:**
- **API Component**  
	- RDD is an API that wraps data and serves as a central structure in Spark applications.
	
- **Immutable**  
	- Once created, RDDs cannot be changed. Transformations always return a new RDD.
	
- **[[Lazy Evaluation]]**  
	- Operations are only executed when an action (like `collect()` or `count()`) is called.
	
- **Fault-Tolerant (Resilient)**  
	- Spark can recompute lost partitions using **lineage information** (a record of how the RDD was built).
	
- **Distributed**  
	- Data is automatically split across multiple nodes in the cluster for parallel processing.
	
- **In-Memory Storage**  
	- Frequently accessed data can be cached in memory for performance boosts.
