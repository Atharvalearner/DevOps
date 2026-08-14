Puppet is an open-source configuration management and automation tool used to automate the provisioning, configuration, and maintenance of servers. It follows a declarative and generally pull-based model. We define the desired system configuration using Puppet manifests, the Puppet Server compiles that configuration into a catalog, and Puppet Agents apply it to managed nodes. Puppet helps maintain consistent configurations across large numbers of servers and supports software installation, service management, user management, file configuration, and compliance.



**# Why Puppet?**

Puppet is used to automate and maintain consistent server configurations across multiple systems. Instead of manually configuring every server, we define the desired state once and Puppet continuously helps ensure that the servers remain in that state.



**# Important Puppet Terms:**

**Puppet Server:** Central server that manages Puppet configuration and compiles catalogs.

**Puppet Agent:** Installed on managed machines and applies configuration.

**Manifest:** Puppet code that defines desired configuration.

**Resource:** A system component managed by Puppet.

**Module:** Reusable collection of Puppet code and related files.

**Catalog:** Compiled representation of the desired state for a node.

**Puppet DSL:** Language used to write Puppet manifests.

**Pull-based:** Agent periodically contacts the Puppet Server.

**Idempotent:** Repeated execution produces the same desired state without unnecessary changes.





**# Puppet Workflow:**

*1. Puppet Agent starts*

&#x20;         *↓*

*2. Agent contacts Puppet Server*

&#x20;         *↓*

*3. Server identifies the node*

&#x20;         *↓*

*4. Server compiles Puppet code*

&#x20;         *↓*

*5. Catalog is generated*

&#x20;         *↓*

*6. Catalog sent to Agent*

&#x20;         *↓*

*7. Agent compares current state*

&#x20;         *↓*

*8. Required changes are applied*

&#x20;         *↓*

*9. System reaches desired state*



**# Puppet:**

* leading **open-source configuration management tool**
* used in DevOps to automate the provisioning, configuration, and management of server infrastructure.
* It allows teams to define the "desired state" of their IT infrastructure as code, ensuring consistency across development, testing, and production environments.
* **Pull-based architecture used and Agent based** in which client's Agent pulls changes from Master/server.



&#x20;            Puppet Server

&#x20;                 │

&#x20;            Puppet Code

&#x20;                 ↓

&#x20;       ┌─────────────────┐

&#x20;       ↓                 ↓

&#x20;  Puppet Agent       Puppet Agent

&#x20;   Server 1           Server 2

&#x20;       ↓                 ↓

&#x20;  Configuration      Configuration



***Architecture :***

**Master-Agent (Client-Server) architecture. *Refer Sir Diagram page no. 11***

1. **Puppet Master** : A central server

&#x09;	- stores configuration data and compiles instructions for managed/client nodes

&#x09;	- Server is a **Java Virtual Machine (JVM)**

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

