MapReduce is a technique in which a huge program is subdivided into small tasks and run parallelly to make computation faster, save time, and mostly used in distributed systems.

Processing large data sets with a parallel/distributed algorithm on clusters of commodity hardware.
![[Pasted image 20231023200732.png]]
 Map, Shuffle, Reduce

**Map:**
- Each Map task operates on a single HDFS block
- Each Map task generates a set of intermediate *key/value pairs*

**Shuffle:**
Sort and consolidate intermediate data from all mappers.

**Reduce:**
Each Reduce task operates on all intermediate values associated with the same intermediate key.

### MapReduce Algorithm Design
Joins
*Reduce-side join*: 
- Repartition join
- When joining two or more large datasets together.
*Map-side join*: 
- Replication join
- When one of the datasets is small enough to cache
(one review question below)

*Review questions:*
![[Pasted image 20231024181343.png]]
![[Pasted image 20231024181533.png]]
![[Pasted image 20231024181616.png]]
![[Pasted image 20231024182037.png]]
