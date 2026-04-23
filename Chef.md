* **open-source DevOps configuration management tool** 
* developed by **Opscode** that treats **infrastructure as code (IaC)**
* Allowing **automated management of physical or virtual servers**. 
* It enables scalable, consistent configuration through **Ruby-based "recipes" and "cookbooks",** managing environments from on-premise to public clouds like AWS, Azure, GCP, etc.
* **Pull-Based Architecture which contains Agent to manage changes or pull changes from server to client.**





**Architecture Components :**

Chef operates using ***a client-server model***

1. **Workstation :** used to interact with Chef-server and Chef-nodes.

&#x09;- also used to create Cookbooks. 

&#x09;- place where all the interaction takes place, where Cookbooks are created, tested and deployed. 

&#x09;- also used for defining roles and environments based on the development and production environment. 

&#x09;- **Knife is used for interacting with Chef Nodes**.

**2. Nodes/client**: It is an agent that runs locally on every node that's management by Chef Infra Server.

**3. Cookbooks/Recipes**: Code files that define the desired configuration or set of instructions.

&#x09;-  Recipes specify the resources to use and the order in which they are to be applied

&#x09;- chef infra client will run a recipe only when asked.

**4. Chef Server**: The central hub that holds configuration data.

