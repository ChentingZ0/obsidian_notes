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
