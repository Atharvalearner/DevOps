\- Open-source container orchestration platform.

\- Orchestrates containerized applications deploys, manages, and scales them across a cluster.

\- Groups containers into pods and manages their full lifecycle.

\- Keeps desired state: auto-restarts, replaces failed containers, and reschedules on healthy nodes.





**# Architecture:**

&#x20;                        Kubernetes Cluster

&#x20;                ┌──────────────┴──────────────┐

&#x20;                │                             │

&#x20;         CONTROL PLANE                    WORKER NODES

&#x20;    ┌───────────┼───────────┐          ┌──────┼──────┐

&#x20;    │           │           │          │      │      │

&#x20;API Server     etcd      Scheduler   kubelet kube-proxy

&#x20;    │                                  │

&#x20;    │                           Container Runtime

&#x20;    │                                  │

&#x20;    │                                  ▼

&#x20;    │                                 Pods

&#x20;Controller Manager







**Cluster :**

\- Set of machines (nodes), that run containerized applications managed by Kubernetes

\- It has at least one worker node and at least one master node.

\- Master node manages the worker nodes and pods.

\- Worker node host the pods.

\- Multiple master nodes are used to provide a cluster with failover and high availability.



**Kubernetes Architecture :**

1\. **Master Components** / Control Plane (Cluster Management):

&#x09;- Responsible for managing the overall state and behavior of the cluster.

&#x09;i) API Server:

&#x09;	- Entry point for all REST commands which is used by all components, kubectl, external clients.

&#x09;	- It validates request and updates cluster state in etcd.

&#x09;	- Acts as communication hub between users, components and the cluster.

&#x09;	- It's Stateless service.

&#x09;ii) etcd:

&#x09;	- Distributed key-value store.

&#x09;	- Store and manage all cluster data, configs, Pod states, Secrets, Node info.

&#x09;iii) Scheduler: Assigns Pods to nodes based on resource needs and constraints.

&#x09;iv) Controller Manager:

&#x09;	- Ensures actual state of cluster matches desired state defined in manifest.

&#x09;	- Runs set of controller loops : Node, Replication, Endpoint controllers.

2\. **Node or Worker Components** / Data Plane (Workload Execution) :

&#x09;- Runs actual application workloads on worker nodes.

&#x09;i) Kubelet:

&#x09;	- It's an primary agent runs on every node.

&#x09;	- Reports node and pod status to the master.

&#x09;	- Ensures containers defined in Pods are running and healthy.

&#x09;ii) Kube-proxy:

&#x09;	- Manages network rules for Pod communication.

&#x09;	- Enabling communication between different Pods and Services.

&#x09;	- Supports load balancing between pods.

&#x09;iii) Container Runtime:

&#x09;	- Executes containers.

&#x09;	- Kubelet interacts with runtime through Container Runtime Interface(CRI).

&#x09;	- Runtimes : containerd, CRI-O.





**Kubernetes Objects:**

▪ ***Pod:***

&#x09;- Basic execution unit of Kubernetes application.

&#x09;- Pod Represents processes running on your cluster \& unit of deployment.

&#x09;- It Encapsulates : Application containers, storage resources, unique network IP, Constraints to run container.

&#x09;- Every POD have an IP Address.

&#x09;- Every POD should be able to communicate with every other POD in the same node, and with other POD on other nodes without NAT.

***▪ Service*** :

&#x09;- Used to provide stable network access to Pods.

&#x09;- Pods are temporary: They can restart, Their IP addresses can change

&#x09;- Service solves this issue by : Giving a fixed IP/DNS name

&#x09;				 Load balancing traffic between Pods

***▪ Volume*** :

&#x09;- Used to provide persistent or shared storage to containers inside Pods.

&#x09;- Used as Sharing data between containers.

&#x09;- Even if Pod restarts the Data remains available.

***▪ Namespace:***

&#x09;- It's group of objects, or a way to divide cluster resources between multiple users.

&#x09;- a logical partition within a single physical cluster, acting as a "virtual cluster".

&#x09;- Allows you to group and isolate resources (like Pods, Services, and Deployments) from one another namespaces or group of nodes.

&#x09;- Example: dev namespace, prod namespace, testing namespace

&#x09;	Each environment stays separated.





***# Deployment***: It manages ReplicaSets and provides features like scaling, rolling updates, self-healing, and rollback capabilities for containerized applications.



***# ReplicaSet***: Ensures the specified number of Pods are running. created and managed by the Deployment.

&#x09;	- Maintains desired replica count, and provide High Availability.



***# ConfigMaps***: Stores non-sensitive config. data as key-val pairs. Mainly used for environment variables, cmd args or config. files.

***# Secrets***: Stores sensitive data like passwords, tokens, ssh-keys. Data is not encrypted(default base64-encoded).



***# Sidecar-container:***

&#x09;- container runs alongside a primary application container within the same Pod.

&#x09;- These containers share the same network namespace and storage volumes.

&#x09;- Used for: Logging and Monitoring, Traffic Management, Secret \& Configuration Synchronization, Data Synchronization

