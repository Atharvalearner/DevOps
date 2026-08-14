Docker Swarm is Docker's native container orchestration technology. It allows multiple Docker hosts to form a cluster and provides features such as service deployment, scaling, service discovery, load balancing, rolling updates, and self-healing. A Swarm cluster consists of manager and worker nodes. The manager maintains the desired state of services and schedules tasks, while worker nodes execute those tasks as containers. For example, if I create an Nginx service with three replicas, the manager schedules three tasks across the available nodes. If one container fails, Swarm detects that the actual state no longer matches the desired state and creates a replacement. Swarm also provides overlay networking for communication between services across nodes





**# Docker Swarm provides:**

1. Orchestration
2. Container scheduling
3. Scaling
4. High availability
5. Service discovery
6. Load balancing
7. Rolling updates
8. Desired-state management
9. Overlay networking
10. Secret management





**# Docker Swarm Architecture:**



&#x20;                Swarm Cluster

&#x20;         ┌───────────┴───────────┐

&#x20;     Manager Nodes           Worker Nodes

&#x20;         │                       │

&#x20;    Manage cluster          Run tasks





**# Service:**

A Service defines the desired state of an application running in the Swarm.

For example: Service: nginx, Replicas: 3, Image: nginx

means: I want 3 instances of Nginx running in the Swarm.



**# Task:**

A task is the unit of scheduling in Swarm, and a task runs a container.



**# Docker Swarm:**

* Lightweight Container **orchestration tool.**
* It allows you to **manage a cluster of Docker hosts (nodes) as a single virtual system to deploy and scale containerized applications on-demand.**



* It takes multiple Docker Engines running on different hosts and lets you use them together as a cluster.
* Swarm consists of multiple Docker hosts which run in **swarm mode**.
* **Docker host can be a manager, a worker, or both** roles.
* When you create a service, you define its **Desired state** which maintain by docker.
* It assures that our application is available even if one of the nodes fails by maintaining container in another node (**High Availability**).
* Based on traffic we can **scale up or down** containers.
* Swarm manage **load balancing** itself.





***Service:***

&#x09;- Higher-level abstraction Defines how containers should deployed, managed, scale across a swarm.

&#x09;- Applications are deployed in the form of services.

&#x09;- Collection of tasks to be executed by workers. eg. HTTP server running as docker container on multiple nodes.

&#x09;- Handles orchestration, load balancing, \& scaling.



***Task***:

&#x09;- representing a single running instance of a container that is created and managed by service.





***Nodes:***

Individual machines in the cluster.

Nodes can be either a manager or worker.

Manager Nodes that handle cluster management and Worker Nodes that run tasks.

To **deploy your application to a swarm**, you submit a **service definition to manager node**

1. **Manager Node** :

&#x09;▪ It **allocates the work** called tasks **to worker nodes.**

&#x09;▪ It also perform the orchestration and cluster management to maintain the desired state of the swarm.

&#x09;▪ Manager nodes elect a single leader using **Raft census algorithm**.

**2. Worker nodes :**

&#x09;▪ It **receive and execute tasks** allocated **by manager node.**

&#x09;▪ An agent runs on each worker node and reports on the tasks assigned to it.

&#x09;▪ The worker node notifies the manager node of the current state of its assigned tasks so that the manager can maintain the desired state of each worker.





**Implementation :**

1\. initialize the docker engines of swarm mode.

2\. After initializing the swarm mode know add the nodes into the docker swarm cluster. When you initialize the swarm mode it will generates two tokens one is for the manger node and another is for the worker node by using following command you can join the nodes according to the requirement.

***docker swarm init <Token>***

3\. start deploying the you application in the form of containers in docker swarm. Docker swarm will take care of deployment of application an scaling of the application across the worker nodes.

4\. With the help of docker swarm cli you can manage the swarm like adding or removing the worker nodes scaling the services and inspecting the swarm state.





**# What happens if a worker node fails?**

The manager detects that tasks running on W2 are no longer available and can schedule replacement tasks on healthy nodes, assuming sufficient capacity exists.



**# What happens if all worker nodes are full and you need another container?**

The Swarm scheduler looks for a node with sufficient available resources and suitable constraints. If no node can satisfy the task requirements, the task remains pending until resources become available or another node is added to the cluster.

