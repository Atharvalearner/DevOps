\- Open-source container orchestration platform.

\- Orchestrates containerized applications deploys, manages, and scales them across a cluster.

\- Groups containers into pods and manages their full lifecycle.

\- Keeps desired state: auto-restarts, replaces failed containers, and reschedules on healthy nodes.



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

▪ Pod:

&#x09;- Basic execution unit of Kubernetes application.

&#x09;- Pod Represents processes running on your cluster \& unit of deployment.

&#x09;- It Encapsulates : Application containers, storage resources, unique network IP, Constraints to run container

▪ Service

▪ Volume

▪ Namespace:  *(refer screenshot or drawn diagram)*

&#x09;- It's group of objects, or a way to divide cluster resources between multiple users.

&#x09;- a logical partition within a single physical cluster, acting as a "virtual cluster".

&#x09;- It allows you to group and isolate resources (like Pods, Services, and Deployments) from one another namespaces or group of nodes.





***Deployment***: Defines the desired state of an application (e.g., number of replicas, container image) and manages updates.

***ReplicaSet***: Ensures the specified number of Pods are running. created and managed by the Deployment.



***ConfigMaps***: Stores non-sensitive config. data as key-val pairs. Mainly used for environment variables, cmd args or config. files.

***Secrets***: Stores sensitive data like passwords, tokens, ssh-keys. Data is not encrypted(default base64-encoded).



***Sidecar-container:***

&#x09;- container runs alongside a primary application container within the same Pod. 

&#x09;- These containers share the same network namespace and storage volumes.

&#x09;- Used for: Logging and Monitoring, Traffic Management, Secret \& Configuration Synchronization, Data Synchronization

