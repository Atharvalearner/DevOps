* **Open-source infrastructure as code (IaC) tool**
* **enables users to define, provision, and manage cloud and on-premises resources** (like VMs, networks, and SaaS) **using a declarative configuration language (HCL).**
* It manages **infrastructure lifecycle** by creating execution plans and using "**providers**" to interact with various cloud platforms (AWS, Azure, GCP).
* Manage low-level components like compute / EC2, storage, and networking resources, as well as high-level components like DNS entries and SaaS features.



Key Aspects :

1. **IaC** : Human-readable files, allowing for versioning, reuse, and sharing.
2. **Declarative language** : Use to handle creation, update or delete resources state.
3. **Providers** : uses plugins / providers to interact with cloud providers (AWS, Azure, Google Cloud), SaaS, and other APIs.

4\. **Execution Plans**: Before making changes, Terraform generates a plan showing what actions will be taken, which helps avoid surprises.

5\. **State Management** : Terraform maintains a state file (terraform.tfstate) that records the current status of your infrastructure, ensuring accurate updates and management.





**Working :**

* Terraform creates and manages resources on cloud platforms and other services through providers(AWS, Azure, GCP) APIs.
* HashiCorp and the Terraform community have different types of resources and services.
* You can find all publicly available providers on the Terraform Registry.





The core **Terraform workflow consists of three stages** :

1. **Write** : create tf. file

&#x09;- You define resources, which may be across multiple cloud providers and services.

&#x09;- eg. You might create a configuration to deploy an application on virtual machines in a Virtual Private Cloud (VPC) network with security groups and a load balancer.



2\. **Plan** : dry run

&#x09;- Terraform creates an execution plan describing the infrastructure it will create, update, or destroy based on the existing infrastructure and your configuration.



3\. **Apply** : apply changes or perform script action

&#x09;- On approval, Terraform performs the proposed operations in the correct order, respecting any resource dependencies.

&#x09;- eg. if you update the properties of a VPC and change the number of virtual machines in that VPC, Terraform will recreate the VPC before scaling the virtual machines.





**State file :**

▪ It is a JSON file that stores information about the resources.

▪ Terraform utilizes the state file to determine the changes that need to be made to the infrastructure when a new configuration is applied.

▪ It is crucial to safeguard the state file and maintain frequent backups since it contains sensitive information about the infrastructure being managed.



**Commands :**

1. **terraform init**
2. **terraform validate**
3. **terraform plan**
4. **terraform apply**
5. **terraform destroy**

