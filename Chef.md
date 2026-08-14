Chef is an open-source configuration management and DevOps automation tool developed by Opscode. It follows the Infrastructure as Code approach and is used to automate server configuration, software installation, application deployment, and other administrative tasks across physical or virtual infrastructure. Chef follows a client-server and primarily pull-based architecture. The main components are the Chef Workstation, Chef Server, and Chef Client running on managed nodes. We create configuration using Ruby-based recipes and organize them into cookbooks. The cookbooks are uploaded from the workstation to the Chef Server, and the Chef Client running on each managed node periodically connects to the Chef Server, pulls the required configuration, and applies it to bring the system into the desired state.



**# Chef:**

* **open-source DevOps configuration management tool**
* developed by **Opscode** that treats **infrastructure as code (IaC)**
* Allowing **automated management of physical or virtual servers**.
* It enables scalable, consistent configuration through **Ruby-based "recipes" and "cookbooks",** managing environments from on-premise to public clouds like AWS, Azure, GCP, etc.
* **Pull-Based Architecture which contains Agent to manage changes or pull changes from server to client.**





**# Architecture Components :**

Chef operates using ***a client-server model***



1. **Workstation :** used to interact with Chef-server.

&#x09;- is the machine where administrators/developers interact with Chef, create and manage cookbooks, recipes, roles, and environments, and communicate with the Chef Server.

&#x09;- It is basically the administrator's working environment.



**2. Chef Server**:

&#x09;- central component that stores and distributes configuration information to Chef-managed nodes.

&#x09;- It stores things such as: Cookbooks, Recipes, Roles, Environments, Node information, Policies/configuration data



**3. Nodes/client**: It is an agent that runs locally on every node that's management by Chef Infra Server.





**# Workflow:**

&#x20;             ADMIN

&#x20;               │

&#x20;               ▼

&#x20;       Chef Workstation

&#x20;               │

&#x20;       Create Cookbook

&#x20;               │

&#x20;       Write Recipes

&#x20;               │

&#x20;               ▼

&#x20;         Chef Server

&#x20;               │

&#x20;       Configuration

&#x20;               │

&#x20;       ┌───────┼────────┐

&#x20;       ▼       ▼        ▼

&#x20;     Node 1  Node 2   Node 3

&#x20;       │       │        │

&#x20;  Chef Client Chef Client

&#x20;       └───────┼────────┘

&#x20;               │

&#x20;         Pull Configuration

&#x20;               │

&#x20;               ▼

&#x20;       Apply Desired State



**# Cookbook:**

* collection of configuration files and related resources or collection of recipes that define how a particular part of the system should be configured.
* For example: nginx cookbook could contain everything required to: Install Nginx, Configure Nginx, Deploy configuration files, Start Nginx
* Cookbook = Collection/package of configuration instructions or collection of recipes



**# Recipe:**

a Ruby-based configuration file inside a Cookbook that defines the resources and configuration steps required to achieve the desired state.



Example concept:

Recipe

&#x20;  ├── Install nginx

&#x20;  ├── Copy configuration

&#x20;  └── Start nginx



**# Easy difference:**

Cookbook: Contains recipes and supporting files

Recipe: Defines the actual configuration steps



**# Knife:**

a command-line tool used from the Chef Workstation to ***interact with the Chef Server and manage Chef infrastructure***.

It can be used for tasks such as: Managing nodes, Uploading cookbooks, Managing roles, Interacting with the Chef Server



Chef Workstation

&#x20;      │

&#x20;    Knife

&#x20;      ▼

Chef Server / Nodes

