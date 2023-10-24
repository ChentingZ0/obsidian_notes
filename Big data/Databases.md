**Database Management System(DBMS)**: a software to capture and analyze data

## Relational SQL Databases
- Storing structured data
- They promise: ACID
1. **ACID**
Short for 
- Atomicity: 
   All included statements in a transaction are either executed or the whole transaction is aborted without affecting the database.
- Consistency: 
   A database is in a consistent state before and after a transaction.
- Isolation: 
  Transactions can not see uncommitted changes in the database.
- Durability:
  Changes are written to a disk before a database commits a transaction so that committed data cannot be lost through a power failure

2. Challenges
- Cannot handle Internet-scale data size, and high read-write rates as well as frequent schema changes
- RDBMS were not designed to be distributed.

## NoSQL
Provides scalability and Large data volumes.
(Achieving ACID properties on large-scale applications is challenging)
The large-scale applications have to be reliable: consistency, availability, partition tolerance(**CAP**)

- **Availability**
Clients can always read and write data.
Replicating data to improve the availability of data. Replicate to many nodes.

- **Consistency**
Consistent state of data after the execution of an operation.
(Strong consistency:
After an update completes, any subsequent access will return the updated value.
Eventual consistency:
Does not guarantee that subsequent accesses will return the updated value.
Inconsistency window)

- **Partition Tolerance**
Continue the operation in the presence of network partitions.

*CAP theorem*: Can only choose two out of three

#### NoSQL Data Models
- **Key-Value Data Model**
Collection of Key/value pairs
Example: Dynamo

- **Column-Oriented Data Model**
![[Pasted image 20231023174919.png]]
Example: [[BigTable]], [[Hbase]], [[Cassandra]]

- **Document Data Model**
Similar to column-oriented store, but values can have complex documents.
Flexible schema: JSON, XML etc.
Example: MongoDB
```json
{ 
	FirstName: "Bob",
	Address: "5 Oak St.", 
	Hobby: "sailing" 
} 
{
	FirstName: "Jonathan", 
	Address: "15 Wanamassa Point Road", 
	Children: [ 
		{Name: "Michael", Age: 10}, 
		{Name: "Jennifer", Age: 8}, 
		] 
}
```

- **Graph Data Model**
Use graph datastructure: Nodes, edges, properties
Example: Neo4J

### Row vs Column oriented Databases
[blog](https://dataschool.com/data-modeling-101/row-vs-column-oriented-databases/)
![[Pasted image 20231023190549.png]]
- Row oriented(Traditional)
Organize data by record, keeping all of the data associated with a record next to each other in memory.
Example: Postgres, MySQL
![[Pasted image 20231023190614.png]]
- Column oriented
Organize data by field, keeping all of the data associated with a field next to each other in memory. Better for querying operations like ordering aggregate, etc(faster)
Example: BigQuery, Snowflake
![[Pasted image 20231023190758.png]]

### Example of CP achieved but not A provided:
![[Pasted image 20231024154800.png]]
