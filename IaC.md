Infrastructure as Code (IaC) :

\- **Configure/Managing and provisioning** computing infrastructure (servers, networks, databases) through machine-readable definition files (code), rather than manual, physical configuration.



\- **Write code that describes exactly what infrastructure you need**.



\- This code can then be executed to **automatically create, modify, or destroy that infrastructure.**



IaC solves :

▪ Automates provisioning by using script/code

▪ Version controls your infrastructure

▪ Ensures consistency across environments

▪ Enables repeatability and idempotency

▪ Enables faster deployments and self-service provisioning



Key Benefits: **Increased speed of deployment, consistency across environments, reduction of configuration errors, and improved cost-efficiency.**





**Types :** 

1. **Provisioning :** create infrastructure from scratch : Terraform, Pulumi
2. **Configuration :** Manage state of existing infra : Ansible, Puppet, Chef
3. **Container Orchestration :** Describes App Infra using YAML : Kubernetes, Helm-charts
4. **Policy as Code (PaC) :** Enforces rules \& governance : Sentinel, OPA





**Cons**

▪ Learning curve

▪ State file management (Terraform)

▪ Misconfigurations can be automated (blast radius)

▪ Sensitive variable handling required

▪ Debugging can sometimes be difficult

