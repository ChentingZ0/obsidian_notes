- Lots of semi-structured data
- CP: strong consistency and partition tolerance

*Timestamp*: each column value may contain multiple versions.
![[Pasted image 20231023175649.png]]
*Tablet*: contiguous ranges of rows stored together. Each tablet is served by one tablet server.
![[Pasted image 20231023180310.png]]

### System Architecture
- *Master*
Assign tablets to tablet server
Balance tablet server load
Handle schema changes
- *Tablet server*
- *Client library*
![[Pasted image 20231023180110.png]]


