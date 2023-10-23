Files are split into chunks
Chunk: single unit of storage, each chunk is stored as a plain Linux file


### GFS Architecture: ![[Pasted image 20231023194059.png]]
### Main components:
GFS master, GFS chunkserver, GFS client
**GFS master**:
- Maintain all file system metadata
- Namespace, mapping from files to chunks and current locations of chunks
- All kept in memory, mappings are stored in operation log
- Periodically communicate with each chunkserver

**GFS Chunkserver**:
- Manage chunks
- Tell master what chunks it has
- Maintain data consistency of chunks

**GFS Client:
- Issue control request to master server
- Issue data request to chunkservers
- Caches metadata

## Why Large Chunks

**Advantages:** 
- Reduce the size of the metadata stored in master
- Reduce clients' need to interact with master

**Disadvantages:**
- Wasted space due to internal fragmentation



- Google File system
- Large-scale distributed file system
- Store log and data files
- *SSTable* file format used to store BigTable data
SSTable consists of chunks of data plus a block index
![[Pasted image 20231023193403.png]]
![[Pasted image 20231023193308.png]]


