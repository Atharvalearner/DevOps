* Lightweight **orchestration for Docker users.**
* It allows you to **manage a cluster of Docker hosts (nodes) as a single virtual system to deploy and scale containerized applications on-demand.**



* It takes multiple Docker Engines running on different hosts and lets you use them together as a cluster.
* Swarm consists of multiple Docker hosts which run in **swarm mode**.
* **Docker host can be a manager, a worker, or both** roles.
* When you create a service, you define its **Desired state.**
* Docker works to maintain that desired state.



***Nodes:*** 

Individual machines or container (physical or virtual) in the cluster. 

Manager Nodes that handle cluster management and Worker Nodes that run tasks.

To **deploy your application to a swarm**, you submit a **service definition to manager node**

1. **Manager Node** :

&#x09;▪ It **allocates the work** called tasks **to worker nodes.**

&#x09;▪ It also perform the orchestration and cluster management to maintain the desired state of the swarm.

&#x09;▪ Manager nodes elect a single leader using **Raft census algorithm**.

**2. Worker nodes :**

&#x09;▪ It **receive and execute tasks** allocated **from manager nodes**

&#x09;▪ An agent runs on each worker node and reports on the tasks assigned to it.

&#x09;▪ The worker node notifies the manager node of the current state of its assigned tasks so that the manager can maintain the desired state of each worker.





***Services:*** Definitions of how containers should run (e.g., image, port, number of replicas).



***Tasks***: The atomic unit of a service, representing a single running container instance.

