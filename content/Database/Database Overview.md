#### [[Database History]]

#### Relational Models
- [[RDBMS]]

---
#### **Big Data Challenges**
- [[Hadoop]] 
Examples of tasks that are hard with large datasets:
1. Count the **most frequent words** in Wikipedia.
2. Find the **hottest November** per country from weather data.
3. Find the **day with most critical errors** in company logs.

These problems require:
- **Huge data**
- **Efficient distributed computing**
#### [[RDBMS]] vs. [[Hadoop]]

| **Feature**    | **RDBMS**           | **Hadoop**                    |
| -------------- | ------------------- | ----------------------------- |
| Data structure | Structured (tables) | Any (structured/unstructured) |
| Scalability    | Limited             | Highly scalable               |
| Speed          | Fast (small data)   | Designed for huge data        |
| Access         | SQL                 | Code (e.g., Java, Python)     |

---
#### **The Need for Horizontal Scaling**
![[RDBMS#The problem of RDBMS]]


[[RDBMS]] fails to:
- Handle **very large-scale data**
- Maintain **high throughput** under load
- Provide a **cost-effective** scalable solution

So: we need **an alternative approach** → [[NoSQL]].

---
#### [[Data Lake]]
##### [[NoSQL]] vs. [[Data Lake]]

| **Feature**  | **NoSQL**                  | **Data Lake**                            |
| ------------ | -------------------------- | ---------------------------------------- |
| Storage      | In a database              | Flat files (text/binary)                 |
| Query engine | Internal (database engine) | External (e.g., [[Apache Spark\|Spark]]) |
| Performance  | High                       | Lower                                    |
| Scalability  | Moderate–High              | High                                     |

