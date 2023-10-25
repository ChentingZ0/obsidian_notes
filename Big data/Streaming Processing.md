#### Database Management System(DBMS)
- data-at-rest analytics
- Process data only when explicitly asked by the users

#### Stream Processing Systems(SPS)
- data-in-motion analytics
- Processing information as it flows, without storing them persistently.

#### Streaming data
Data stream is unbound data, which is broken into a sequence of individual tuples.
A data tuple is the atomic data item in a data stream.

- Structured data: tables, relational database
- Semi-structured data: Json file, XML file ...
- Unstructured data: 


#### Event Time, Processing Time
- Event time: 
	The time at which events actually occurred and events come into the system with a timestamp
- Processing time: 
	Time at which events are observed in the system
	Timestamp assigned when the event is being processed
	Can be different from where the event actually happend
	-> Delayed data
	-> Out of order data
	-> Backfilling data
	 
- **Watermarking** helps a stream processing system to deal with lateness. It is a threshold to specify how long the system waits for late events.
  For example, after you receive watermark 11, then it means we expect you have already receives all tuples with timestamp less than 11. If not
  

#### Messaging system -> Kafka
- **Direct Messaging**
A producer sends a message containing the event, which is pushed to consumers.
Challenges: what happened if a consumer crashes or temporarily goes offline.(not durable)

- **Message Brokers**
It decouples the producer-consumer interaction.
Log-based message brokers durably store all events in a sequential log.
![[Pasted image 20230922170523.png]]

**Kafka**: A log-based Message Broker
Distributed, topic-oriented, partitioned, replicated commit log serivice.
![[Pasted image 20230922170504.png]]

#### Spark Streaming
**DStream**: sequence of RDDs representing a stream of data.
![[Pasted image 20230925153240.png]]

*Review questions*:
![[Pasted image 20231024204813.png]]
![[Pasted image 20231024204854.png]]
![[Pasted image 20231024205556.png]]
![[Pasted image 20231024205651.png]]
![[Pasted image 20231025192006.png]]
### States
- Need to check the previous state of the RDD in order to do something with the current RDD.
- Spark supports stateful streams
- It is mandatory that you provide a checkpointing directory for stateful streams.

Stateful Stream Operations:
`mapWithState`: It is executed only on set of keys that are available in the last micro batch.