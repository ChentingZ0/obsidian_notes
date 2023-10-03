### Data Warehouses
Use **ETL**  (Extract, Transform, Load) data directly from operational database systems.(on structured data)
![[Pasted image 20231003191654.png]]
But 
1. it couldn't support unstructured and semi-structured data: time series, logs, images, documents, etc.
2. No support for data science and ML.

### Data lakes
Use **ELT** (Transform after Loading) process.
can handle unstructured and semi-unstructured data
Data Lake defines the schema(transform) after data is stored(load), Data Warehouse defines the schema before data is stored.
![[Pasted image 20231003191715.png]]
### Lakehouse
A lakehouse is **a new, open architecture that combines the best elements of data lakes and data warehouses**. Lakehouses are enabled by a new system design: implementing similar data structures and data management features to those in a data warehouse directly on top of low cost cloud storage in open formats.
![[Pasted image 20231003193149.png]]
- Metadata layers for Data Lakes 
- New query engine designs

**Delta Lake Table**: A directory that holds data objects and a log of transaction operations.
**DeltaLog**: A transaction log that tracks all changes that users make to the table. A number of JSON file.
![[Pasted image 20231003194943.png]]
Any changes to that table are recorded as ordered, atomic commits in the DeltaLog.
Each commit is written out as a JSON file, starting with 00000.json
![[Pasted image 20231003195835.png]]


### Schema Enforcement and Evolution
Data is always evolving and accumulating
Schema enforcement: prevents users from accidentally polluting their tables with mistakes or garbage data.



### In conclusion:
### What Is the Different Between a Data Warehouse, a Data Lake, and a Data Lakehouse?

**Data Structure**: Data Warehouses hold structured data, whereas data lakes and lakehouses store both structured and unstructured data.

**Processing**: For data analysis, data warehouses employ SQL-based processing, whereas data lakes and data lakehouses use a variety of processing engines, such as Spark and Databricks.

**Storage**: Data warehouses store structured data, whilst data lakes and lakehouses store raw data.

**Schema**: Data warehouses feature a predefined schema, whereas data lakes and lakehouses employ a schema-on-read method, where the schema is built during analysis.

**Use case**: Data warehouses are often used for business intelligence and reporting, whereas data lakes and lakehouses are used for advanced analytics such as machine learning and data science.
![[Pasted image 20231003203045.png]]
