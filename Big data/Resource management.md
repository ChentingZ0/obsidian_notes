### Mesos
Mesos is a common resource sharing layer, over which diverse frameworks can run.
![[Pasted image 20231002153427.png]]
A **framework**(e.g., Hadoop, Spark) manages and runs one or more jobs. A **job** consists of one or more tasks. 

1. Master sends resource offers to frameworks
2. Frameworks select which offers to accept and which tasks to run
Resource allocation strategy: 
Max-Min fairness: DRF

### Yarn
[youtube video](https://www.youtube.com/watch?v=KqaPMCMHH4g&ab_channel=Simplilearn)
![[Pasted image 20231002171814 1.png]]
Three important elements:
![[Pasted image 20231002171847 1.png]]
***ResourceManager****(RM)
- run several services, including **resource scheduler**, and ApplicationMaster.
- Mediate the available resources in the cluster among competing applications, with the goal of maximum cluster utilization.
- One per cluster. 
***ApplicationMaster***
- framework-specific process, negotiate resources for a single application. 
- Each ApplicationMaster requests resources from the resource manager and works with the containers provided by node managers. 
- One per node
***NodeManager***
Can be many in one cluster. They are the slaves of the infrastr ucture. Each node manager offers resources to the cluster

A container is a fraction of the NodeManager capacity and is used by the client for running a program. 

How YARN Runs an Application:
1. The client submits an application to the ResourceManager
2. The ResourceManager allocates a container
3. The ApplicationMaster contacts the related NodeManager
4. The NodeManager launches the container
5. The container executes the ApplicationMaster


### Borg
Cluster management system at Google


### Docker
脑子疼,改天再研究...