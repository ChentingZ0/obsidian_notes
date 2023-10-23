- Column-oriented database
- AP: availability and partition tolerance
- Key/value: values are stored as objects

**Data partition**:
[Consistent hashing] for partitioning
```
partition = hash(data) mode size(id space)
id space = [0, 15], n = 16 
hash("Fatemeh") = 12 
hash("Ahmad") = 2 
hash("Seif") = 9 
hash("Jim") = 14 
hash("Sverker") = 4
```
**Replication**:
To achieve high availability and durability, data should be replicated on multiple nodes.
![[Pasted image 20231023183029.png]]
Adding and removing nodes:
Gossip-based mechanism: periodically, each node contacts another randomly selected node.
