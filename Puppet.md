* leading **open-source configuration management tool**
* used in DevOps to automate the provisioning, configuration, and management of server infrastructure.
* It allows teams to define the "desired state" of their IT infrastructure as code, ensuring consistency across development, testing, and production environments.
* **Pull-based architecture used and Agent based** in which client's Agent pulls changes from Master/server.





***Architecture :***

**Master-Agent (Client-Server) architecture. *Refer Sir Diagram page no. 11***

1. **Puppet Master** : A central server

&#x09;	- stores configuration data and compiles instructions for managed/client nodes

&#x09;	- Server is a **Java Virtual MAchine (JVM)**

&#x09;	- certificate authority provides certificates so that master ang agents can communicate safely

2\. **Puppet Agent** : Software/**application** installed on client nodes

&#x09;- agent runs as a background service and **periodically queries/ping for compiled code from server**.

&#x09;- communicates with the Master via secure SSL, pulls the catalog, and applies the necessary changes.

&#x09;- Agent also **contains factor.**

3\. **Facter** : A tool on the agent that **gathers system information (facts)** like **IP addresses or OS versions** and sends them to the Master to help customize the catalog.





***Resource Abstraction Layer (RAL) :***

* Where it separates out the resources from their implementations
* It provides way to interact with the base OS
* The platform specific (macOs, Windows, Linux) configurations exist from providers(Apache, Nginx).

