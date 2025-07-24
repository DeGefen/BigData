> A distributed system can only guarantee **2 out of 3**:
- **C**: Consistency – all nodes see the same data
- **A**: Availability – every request gets a (non-error) response
- **P**: Partition tolerance – system still works despite network issues
[![NoSQL — CAP Theorem. Let's see what is CAP Theorem... | by Kavini  Welarathne | Medium](https://miro.medium.com/v2/resize:fit:406/1*hesm6wzPQHQY5w_hb2U33A.png)
In practice: Partition **tolerance is a must** → must trade between Consistency or Availability
##### Eventually Consistent
> Consistency is achieved at some latency.
-  Writes are fast
- Reads might lag until all replicas are updated
- System becomes consistent ***eventually***
