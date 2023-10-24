MapReduce is expensive(low), it always goes to disk and HDFS
Spark goes to RAM

Spark applications consist of 
- A driver process(*Spark Session*)
- A set of executor processes
```scala
SparkSession.builder.master(master).appName(appName).getOrCreate()
```

*SparkContext*
SparkSession internally has a SparkContext for actual computation.
```scala
val conf = new SparkConf().setMaster(master).setAppName(appName) 
new SparkContext(conf)
```

*Resilient Distributed Datasets(RDD)*
Virtually all Spark code you run, compiles down to an RDD.
To create RDDs, it uses the parallelize method on a SparkContext
This turns a single node collection into a parallel collection
In the console shell, `sc` = `spark.sparkContext`

- Transformations
Create a new RDD from an existing one.
Lineage: transformations used to build an RDD.
RDDs are stored as a chain of objects capturing the lineage of each RDD.
A DAG representing the computations done on the RDD is called **lineage graph**.
![[Pasted image 20231024200617.png]]


- Actions
Transformations allow us to build up our logical transformation plan.


### Spark and Spark SQL
Spark SQL is built on top of Spark. Spark is built on top of RDD
![[Pasted image 20231024193846.png]]

Spark has two notions of structured collections:
- **DataFrames**
*Schema*: Define the column names and types of a DataFrame.
```scala
{"name":"Michael", "age":15, "id":12} 
{"name":"Andy", "age":30, "id":15} 
{"name":"Justin", "age":19, "id":20} 
{"name":"Andy", "age":12, "id":15} 
{"name":"Jim", "age":19, "id":20} 
{"name":"Andy", "age":12, "id":10}
```

```scala
val people = spark.read.format("json").load("people.json") people.schema 
// returns: 
StructType(StructField(age, LongType, true), 
StructField(id, LongType, true), 
StructField(name, StringType, true))
```

There are two ways to create a DataFrame:
1. From an RDD
```scala
val tupleRDD = sc.parallelize(Array(("seif", 65, 0), ("amir", 40, 1)) val tupleDF = tupleRDD.toDF("name", "age", "id")
```
2. From raw data sources
```scala
val peopleJson = spark.read.format("json").load("people.json") 
val peopleCsv = spark.read.format("csv") 
				.option("sep", ";") 
				.option("inferSchema", "true") 
				.option("header", "true") 
				.load("people.csv")
```


- DataSets
DataFrames elements are Rows, which are generic untyped JVM objects.
Scala compiler cannot type check Spark SQL schemas in DataFrames.

DataSets can be thought of as typed distributed collections of data.
Dataset API unifies the DataFrame and RDD APls.

*Review question:*
![[Pasted image 20231024195826.png]]

![[Pasted image 20231024211517.png]]![[Pasted image 20231024211529.png]]
