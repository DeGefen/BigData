![[Database Overview#**The Need for Horizontal Scaling**]]

## NoSQL
>“NoSQL” isn't one technology, and it doesn’t solve everything.
##### **General Characteristics:**
- **Non-relational**: no strict schema or table joins
- **Horizontally scalable**
- **Simple design**
- **Distributed**
- Provide **SQL-like API**

### **NoSQL Families (Types)**
1. [[Key-Value Store]]
2. [[Document Stores]]
3. [[Wide Column Store]]
4. [[Graph Database]]

### Characteristics of Distributed Databases
> General traits of any distributed DB system, not just NoSQL
- **Advantages**:
	- Horizontal scalability
	- Simpler to design for scale
	- High availability (resilience to failure)
	
- **Challenges**:
	- Lack of [[RDBMS#Relational model - Transactional|ACID transactions]]
	- Harder to monitor/administer
	- [[CAP Theorem]] limitations

### Benefits of NoSQL
- Scales horizontally well
- Designed for specific use-cases
- Suitable where [[RDBMS]] is limited
- Many are [[Open Source]]
### **Drawbacks of NoSQL**
- No “one size fits all” solution
- Maturity varies between tools
- Management tools may be lacking
- Trade-offs in consistency ([[CAP Theorem]])

### Best Of Both Worlds
- [[NewSQL]]

> Next [[Data Lake]]
